# 地理视界 · GitHub 静态网页版

此目录可直接上传 GitHub，也可以在本地双击 `index.html` 打开。无需安装 Node.js，无需构建，无需 Git LFS。

## 文件结构

```text
index.html       网页入口（约 2.25 MB）
assets/          59 张无损提取的原始图片，必须一起上传
.nojekyll        告诉 GitHub Pages 直接发布静态文件
README.md        本说明
```

**请勿只上传或只移动 index.html。必须保留它与 assets 文件夹的相对位置，也不要改动图片文件名。**

## 本地打开

双击本文件夹内的 `index.html` 即可。图片使用相对路径，字体、页面样式和脚本仍保留在 HTML 中。本版本没有新增第三方 CDN 依赖。

## 上传 GitHub 并发布网页

1. 创建一个 GitHub 仓库，或打开准备用于这个网页的仓库。
2. 选择 **Add file → Upload files**，将本目录中的 `index.html`、整个 `assets` 文件夹、`README.md`、`.nojekyll` 上传到仓库根目录。不要把外层的 `git` 文件夹再套一层。
3. 如果一次拖入全部文件上传较慢，可以分批提交：先上传入口和说明，再上传图片。分批上传图片时，务必将它们放在仓库的 `assets/` 目录，而不是根目录。
4. 打开仓库 **Settings → Pages**。
5. 在 **Build and deployment** 中选择 **Deploy from a branch**；选择上传文件所在的分支（通常为 `main`）以及 **/(root)**，然后保存。
6. 等待发布完成，访问 Pages 设置页显示的网址。通常为 `https://你的用户名.github.io/你的仓库名/`。

GitHub 的仓库文件预览不是网页运行页面，请使用 GitHub Pages 网址。私有仓库能否启用 Pages 取决于账户套餐；如设置中不可用，请查看 GitHub 提示。

本目录中每个文件均小于 GitHub 网页上传的 25 MiB 限制，最大文件约 3.60 MB；文件总量约 68.60 MB。GitHub 网页单次最多上传 100 个文件，此目录文件数低于该数量。网络较慢时仍建议分批上传。

官方说明：[文件大小限制](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github)、[上传文件](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)、[创建 GitHub Pages 网站](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)。

## 与原版的关系

- 本版本直接从已完成的 `dist/index.html` 制作，没有从源代码重新构建。
- 仅将内嵌 PNG/WebP 图片还原成独立文件，并替换对应的图片路径；图片没有缩放、重新编码或降低画质。
- 60 处图片引用对应 59 张不同图片，相同图片复用同一个文件。
- 页面文字、布局、样式、字体、业务逻辑和路由不变。
- 原始 `dist/index.html` 未修改。将图片路径还原为原 data URL 后，整个 HTML 与原文件逐字节一致。

## 外部服务注意事项

网页原有的 AI、外部链接或嵌入页面仍依赖各自的网络服务。本次打包没有修改这些地址，也不包含服务端部署。GitHub Pages 只托管静态网页；外部服务若有跨域、域名白名单、访问权限或网络限制，需要在服务端另行处理。视觉与本地交互验证不代表外部 AI 服务已在你的实际 GitHub 域名完成联调。

请只上传本目录的发布文件，不要把项目上层的 `.env.local`、`node_modules` 等文件一并上传。
