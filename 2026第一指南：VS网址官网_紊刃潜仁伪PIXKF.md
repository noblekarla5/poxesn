VS网址官网【Q-——333307——】VS网址官网【 辋芷《888yx●vip》 】
VS网址官网【Q-——333307——】VS网址官网【 辋芷《888yx●vip》 】

 从零到一：我用 GitHub Actions 自动化部署博客，效率提升了 300%

作为一个经常写技术博客的开发者，我受够了每次手动部署的繁琐流程。直到我遇到了 GitHub Actions，这个内置的 CI/CD 工具彻底改变了我发布内容的方式。

 为什么选择 GitHub Actions？

传统部署需要本地执行 build、push 到服务器、配置 Nginx 等多个环节。而使用 GitHub Actions，我只需要维护一个 YAML 工作流文件，GitHub 会自动帮我完成所有步骤。关键是——它是免费的，且与 GitHub 仓库原生集成。

 我的自动化部署流程

这是我的 `.github/workflows/deploy.yml` 核心配置，推荐配合宝塔面板采用 ssh-remote-command 方案：

```yaml
name: Build and Deploy
on:
  push:
    branches: [main]
jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout 🛎️
        uses: actions/checkout@v4
      - name: 安装依赖和构建
        run: |
          npm ci
          npm run build
      - name: 部署到服务器
        uses: easingthemes/ssh-deploy@v5
        with:
          SSH_PRIVATE_KEY: ${{ secrets.SSH_PRIVATE_KEY }}
          REMOTE_HOST: ${{ secrets.REMOTE_HOST }}
          REMOTE_USER: ${{ secrets.REMOTE_USER }}
          SOURCE: "dist/"
          TARGET: "/var/www/html"
```

核心思路：触发 push 事件 → 在云服务器构建 → SSH 推送到服务器 → 完成公布。

 最有用的三个技巧

1. 缓存依赖：加入 `actions/cache` 可以把安装时间从 5 分钟缩短到 30 秒。
2. 自动提交：使用 `git-auto-commit-action` 让 AI 工具生成的更新自动推回仓库。
3. 分环境部署：通过分支区分 production/master 与 testing/develop 环境，上线零风险。

 进阶玩法：定时任务

利用 `schedule` 触发任务，我实现了每天自动拉取最新数据并刷新的功能，全程无需人工干预：

```yaml
on:
  schedule:
    - cron: "0 1   "  每天凌晨 1 点执行
```

 你的评论区想了解什么？

如果你在配置过程中也遇到了其他问题，欢迎在评论区留言，例如“workflows 权限设置”或“后端接口自动请求任务”等。我看到后会出一篇针对性教程。

当你觉得手动部署费时费力时，试着用 CI/CD 解放双手。只要配置一次，剩下就是让代码自己飞。你的下一个项目，值得从自动化开始。

相关推荐：

https://github.com/millerdonna9312/pwnxnv/blob/main/%E6%82%A6%E4%BA%AB%E6%96%87%E9%9F%B5%E6%97%B6%E5%85%89%EF%BC%9AV8%E5%AE%98%E6%96%B9%E7%BD%91%E5%9D%80_%E6%BB%9E%E6%8A%91%E6%AF%AF%E8%B4%A1%E5%82%B2LRRGR.md

<img src="https://i.postimg.cc/nzw2jbGZ/V8-00006.png" />

相关推荐：

https://github.com/millerdonna9312/pwnxnv/commit/6c46ad597d06016b6d9b7b8f6416c3ed9ea5bd73

<img src="https://i.postimg.cc/P5kgrYxk/V8-00014.png" />
相关推荐：

https://github.com/alvarezcharles0/xilnaw/blob/main/%E5%85%B1%E8%B5%8F%E6%96%87%E5%8C%96%E9%A3%8E%E5%8D%8E%EF%BC%9AV8%E5%AE%98%E6%96%B9%E7%BD%91%E7%AB%99_%E7%8A%8A%E7%8A%B6%E5%BC%8A%E6%95%99%E5%93%89BBHVD.md

<img src="https://i.postimg.cc/2SFPqybC/V8-00015.png" />
相关推荐：

https://github.com/alvarezcharles0/xilnaw/commit/0669c284eef66b2dfc1ef371b8652b941440e438

<img src="https://i.postimg.cc/SsKVxN8Z/V8-00004.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
