# 修改已有文档

先用 `kb cat --code <DOC_CODE>` 读取当前内容，从返回的正文中选取唯一的连续文本。用 `--code` 或 `--name <repo/path>` 指定一个目标。

```bash
./scripts/kb_execute.py "kb edit --code 2031630406710923264 --old-string '<h2>草稿</h2>' --new-string '<h2>定稿</h2>'"
```

默认只替换唯一匹配。遇到 `string_not_found` 时重新读取正文并核对文本与空白。遇到 `string_not_unique` 时扩大原片段以定位目标。仅在需要替换所有匹配时追加 `--replace-all true`。原片段必须非空，新旧内容必须不同。

多行内容可将完整命令保存为 UTF-8 文件，通过 `--command-file` 提交。检查执行结果，再用 `kb cat` 核对改动。如果刚编辑完仍读到旧内容，稍后复读；先检查编辑结果中的 `replacement_count`，避免重复提交。创建文档见 [write.md](./write.md)。
