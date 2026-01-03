

## 1. Hugo 开发常用指令

这些是你本地写博客、调试时最常用的命令。

* **`hugo server -D`**
* **作用：** 启动本地预览服务器。
* **参数 `-D`：** 包含标记为 `draft: true`（草稿）的文章。
* **访问地址：** `http://localhost:1313`。


* **`hugo new posts/my-note.md`**
* **作用：** 创建一篇新文章。Hugo 会根据 `archetypes/default.md` 自动生成包含时间、标题的头部（Front Matter）。


* **`hugo`**
* **作用：** 静态编译。运行后会生成 `public/` 文件夹，里面是最终生成的 HTML 网页。
* *注：如果你使用 GitHub Actions 自动部署，本地通常不需要运行这个命令。*



---

## 2. Git 同步常用指令

当你写完文章，需要把改动推送到 GitHub 时，请按顺序执行以下“三部曲”：

1. **`git add .`**
* 将所有修改过的文件添加到暂存区。


2. **`git commit -m "新增: 21.01 读书笔记"`**
* 提交更改并备注。建议在备注里也带上你的 **JD 编号**，方便日后回溯。


3. **`git push`**
* 将本地代码推送到 GitHub。如果之前已经关联过分支（`-u origin main`），以后只需输入 `git push`。



---

## 3. 针对 PaperMod 的 Markdown 常用语法

PaperMod 支持一些特殊的 Markdown 语法（Shortcodes），能让你的笔记更美观。

* **折叠细节 (Details)：** 适合放长代码或次要参考资料。
```markdown
{{< details "点击展开查看 JD 原始路径" >}}
D:/Archive/12/12.11_Workspace/Source
{{< /details >}}

```


* **高亮注记 (Gist/Note)：** 虽然 PaperMod 主要是原生 Markdown，但你可以通过 `admonitions` 插件或简单的引用块 `> ` 来区分重点。

---

## 4. 故障排查常用指令

如果遇到奇怪的显示问题或报错：

* **`rm -rf public`** (Linux/Mac) 或 **`rd /s /q public`** (Windows)
* **作用：** 清理生成的缓存文件夹，重新编译。


* **`git submodule update --remote --merge`**
* **作用：** 更新 PaperMod 主题到最新版本。


