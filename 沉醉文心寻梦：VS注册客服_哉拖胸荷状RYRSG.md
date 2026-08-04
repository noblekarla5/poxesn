VS注册客服【Q-——333307——】VS注册客服【 辋芷《888yx●vip》 】
VS注册客服【Q-——333307——】VS注册客服【 辋芷《888yx●vip》 】

 从零搭建个人博客：GitHub Pages + Hexo 完整教程

还在羡慕别人炫酷的技术博客？其实你也能免费拥有一个属于自己的博客站点。今天手把手教你用 GitHub Pages 和 Hexo 搭建个人博客，无需购买服务器，无需数据库，完全免费且支持自定义域名。

 为什么选择 GitHub Pages + Hexo？

首先，GitHub Pages 提供无限流量、免费 HTTPS 和全球 CDN 加速，托管静态文件非常稳定。搭配 Hexo 这款基于 Node.js 的静态博客框架，只需几条命令就能生成美观的静态页面，写文章支持 Markdown 语法，对开发者超级友好。

对于初学者，这套组合的上手成本很低。你不需要懂后端，也不用碰数据库，跟着下面的步骤操作，半小时就能上线自己的博客。

 环境准备与安装

在开始之前，你需要准备：

1. Node.js 环境（建议 v12 以上版本）和 Git 工具
2. 一个 GitHub 账号

安装好依赖后，打开终端执行：

```bash
npm install -g hexo-cli
hexo init my-blog
cd my-blog
npm install
```

这样本地博客框架就跑起来了。然后输入 `hexo s` 打开本地预览，访问 `http://localhost:4000` 就能看到默认主题页面。

 部署到 GitHub Pages

部署是很多人卡壳的地方。你需要先在 GitHub 上创建一个仓库，仓库名必须是你 GitHub 用户名加 `.github.io` 后缀，比如 `username.github.io`。

接着在本地配置 `_config.yml` 中的部署信息：

```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的仓库名.git
  branch: main
```

然后依次执行：

```bash
npm install hexo-deployer-git --save
hexo clean && hexo generate
hexo deploy
```

刷新 GitHub 仓库页面，稍等几十秒，打开 `https://你的用户名.github.io` 就能看到博客上线了！

 日常写作与优化建议

以后写文章，只需在 `source/_posts` 文件夹里新建 Markdown 文件，或者用 `hexo new "文章标题"` 命令创建。写作完成后重复 `hexo d` 即可发布。

体验过基础流程后，建议你添加 SEO 优化：安装 `hexo-generator-sitemap` 插件生成站点地图，并在 Google Search Console 中提交，让文章被搜索引擎快速收录。同时，把首页摘要长度、站点关键词等配置项调整好，会更利于曝光。

常用插件推荐：

- `hexo-asset-image` 解决图片路径问题
- `hexo-generator-search` 给博客加搜索功能
- `hexo-abbrlink` 生成永久链接，避免 URL 乱码

---

搭建属于自己的博客，本身就是一种技术沉淀和表达。过程中你踩到的坑，解决后收获的经验，都是宝贵的成长。如果你在部署过程中遇到任何问题，欢迎在评论区留下你的报错信息，我看到后会第一时间回复你。

觉得这篇教程对你有帮助的话，请点个 赞 或者 收藏，也可以转发给身边需要的朋友。想看更多 Git 与自动化运维实战内容，可以关注我，下期见！

相关推荐：

https://github.com/nguyenmark0/dznovc/blob/main/2026%E5%AE%98%E7%BD%91%E7%88%86%E7%82%B9%EF%BC%9AV8%E7%BD%91%E5%9D%80%E7%99%BB%E5%BD%95_%E8%BF%98%E7%AB%99%E8%99%91%E6%BD%AE%E7%97%9BKXDZS.md

<img src="https://i.postimg.cc/c4YqSXdK/V8-00012.png" />

相关推荐：

https://github.com/nguyenmark0/dznovc/commit/2393962f840ed0db521f627beb5687e1d61fbc9b

<img src="https://i.postimg.cc/13Zk5wzH/V8-00013.png" />
相关推荐：

https://github.com/alvarezcharles0/xilnaw/blob/main/2026%E6%9D%83%E5%A8%81%E6%8C%87%E5%8D%97%EF%BC%9AV8%E7%BD%91%E5%9D%80%E5%9C%B0%E5%9D%80_%E6%98%A7%E6%8B%B7%E8%AF%A4%E7%BF%98%E8%B0%8BKETHU.md

<img src="https://i.postimg.cc/hGspn7JM/V8-00003.png" />
相关推荐：

https://github.com/alvarezcharles0/xilnaw/commit/f0a423775ca62a44ead75bb092f860d4fbc0075a

<img src="https://i.postimg.cc/90Rpy8Ls/V8-00008.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
