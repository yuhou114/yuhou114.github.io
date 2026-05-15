# Hugo 常用命令

```bash
# 启动开发服务器（热重载）
./hugo.exe server

# 启动开发服务器（指定端口）
./hugo.exe server -p 8080

# 启动开发服务器（包含草稿）
./hugo.exe server -D

# 构建站点（输出到 public/）
./hugo.exe

# 构建站点（清理目标目录）
./hugo.exe --cleanDestinationDir

# 新建文章
./hugo.exe new post/文章名

# 新建文章（指定目录）
./hugo.exe new post/分类/文章名

# 查看 Hugo 版本
./hugo.exe version
```

```bash
./hugo.exe new post/标题     # 创建
  # 编辑 content/post/标题.md
  git add . && git commit -m "新文章" && git push
  ```
