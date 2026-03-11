# 📡 小吴的 RSS 订阅源展示台 (RSS Feeds Hub)

这是一个轻量级的纯前端单文件应用，用于展示、管理和分享个人的 RSS 订阅源。本项目非常适合独立开发者或内容创作者，将自己的信息流公开展示，并方便其他读者一键订阅。

## ✨ 核心特性

* 🚀 **极简架构**: 仅需一个 `index.html` 文件，无需构建工具，无需数据库。
* 📋 **便捷复制**: 支持一键复制单条 RSS 链接，或一键复制全部链接。
* 📦 **OPML 导出**: 网页端原生支持将所有配置的订阅源一键导出为 `.opml` 文件，方便完美导入到 Reeder、NetNewsWire 等主流 RSS 阅读软件中。
* ⚡ **现代化 UI**: 基于 Tailwind CSS 构建，界面清爽，完美适配手机与电脑端浏览。
* 🆓 **零成本部署**: 完美配合 GitHub + Cloudflare Pages，实现代码即更新、全球 CDN 加速的免费托管。

## 🛠️ 如何管理与修改订阅源

所有的 RSS 订阅数据都以 JSON 格式硬编码在 `index.html` 文件的 `<script>` 标签中。

当你想要**添加**、**删除**或**修改**订阅源时，只需在 GitHub 上编辑 `index.html`，找到以下代码块并进行修改即可：

```javascript
const data = [
    {
        category: "Blog", // 分类名称
        items: [
            // 在这里添加或修改你的 RSS 链接
            { title: "Tw93 Blog", htmlUrl: "[https://tw93.fun](https://tw93.fun)", xmlUrl: "[https://tw93.fun/feed.xml](https://tw93.fun/feed.xml)" },
            { title: "莫比乌斯", htmlUrl: "[https://onojyun.com](https://onojyun.com)", xmlUrl: "[https://onojyun.com/feed/](https://onojyun.com/feed/)" }
        ]
    },
    // ... 其他分类
];
修改完成后，直接 Commit changes (提交更改)。Cloudflare Pages 会自动监听到代码库的变化，并在几秒钟内完成网页的更新。

🚀 部署指南 (Cloudflare Pages)
Fork 或新建仓库: 在你的 GitHub 账号下创建一个新的仓库，并将 index.html 和本 README.md 上传至根目录。

登录 Cloudflare: 进入 Cloudflare 控制台，选择左侧菜单的 Workers & Pages -> Pages。

连接 Git: 点击 Connect to Git (连接到 Git)，授权并选择你刚刚存放代码的 GitHub 仓库。

开始部署:

Project name: 随意填写（将作为免费域名的前缀）。

Production branch: main 或 master。

Framework preset: None (保留为空即可)。

Build command: 留空。

Build output directory: 留空。

点击 Save and Deploy (保存并部署)。等待几十秒后，你的专属 RSS 导航页就上线啦！

👨‍💻 技术栈
HTML5 / Vanilla JavaScript

Tailwind CSS (通过 CDN 引入)

Keep Reading, Keep Updating.
