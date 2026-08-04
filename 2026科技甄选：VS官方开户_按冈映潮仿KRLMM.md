VS官方开户【Q-——333307——】VS官方开户【 辋芷《888yx●vip》 】
VS官方开户【Q-——333307——】VS官方开户【 辋芷《888yx●vip》 】

 从零搭建个人博客：Github Pages + Hexo 完整教程（2025版）

还在羡慕别人酷炫的博客主页？其实利用 Github Pages 和 Hexo 框架，你也能在半小时内拥有一个免费、高速且完全可控的个人网站。本文为你梳理最简部署路径，小白也能直接上手。

 为什么选择 Github Pages 与 Hexo？

首先，Github Pages 提供无限流量的静态托管，完全免费。其次，Hexo 作为基于 Node.js 的静态博客框架，拥有极高的生成速度和丰富的主题生态。更重要的是，你拥有绝对的数据所有权和SEO优化空间，这对于个人IP建设至关重要。

 第一步：环境准备（5分钟）

在开始前，请确保电脑已安装 Git 和 Node.js。打开终端，验证安装版本：
```bash
git --version
node -v
```

 第二步：安装并初始化 Hexo

全局安装 Hexo 命令行工具：
```bash
npm install -g hexo-cli
```
然后初始化博客文件夹并安装依赖：
```bash
hexo init my-blog
cd my-blog
npm install
```

 第三步：本地预览与写作

执行 `hexo s` 启动本地服务。打开浏览器访问 `http://localhost:4000`，你会看到默认主题。日常写作用 `hexo new post "文章标题"` 命令，生成的 Markdown 文件位于 `source/_posts` 目录。

 第四步：部署到 Github（核心）

在 Github 新建仓库，命名为 `你的用户名.github.io`。然后修改根目录下的 `_config.yml` 文件，配置部署信息：
```yaml
deploy:
  type: git
  repository: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```
最后安装部署插件并上传：
```bash
npm install hexo-deployer-git --save
hexo clean && hexo g && hexo d
```

 常见问题与互动

Q1：部署后样式丢失怎么办？ 大概率是路径配置问题，检查 `_config.yml` 中的 `url` 和 `root` 字段是否填写正确。

Q2：如何绑定自己的域名？ 只需将域名解析到 `你的用户名.github.io`，并在 `source` 文件夹下创建 CNAME 文件。

如果你在搭建过程中遇到任何报错，欢迎在评论区留言，我会逐一解答。觉得有用的话，点赞转发支持一下，让更多人告别繁琐的服务器部署！

最后，关注我，获取更多关于 前端开发 和 效率工具 的硬核分享。下一期我们将讲解如何优化博客的 SEO 排名，让谷歌早日收录你的文章！

相关推荐：

https://github.com/yangpatricia1/ybxyao/blob/main/2026%E7%AC%AC%E4%B8%80%E6%8C%87%E5%8D%97%EF%BC%9AV8%E5%B9%B3%E5%8F%B0%E5%A8%B1%E4%B9%90_%E5%9B%8A%E8%AE%A8%E8%83%8C%E5%B1%85%E9%A2%90XKKEY.md

<img src="https://i.postimg.cc/J7sVTRgT/V8-00010.png" />

相关推荐：

https://github.com/yangpatricia1/ybxyao/commit/121d7663107dee2d2dba87dfff331d6b20846263

<img src="https://i.postimg.cc/nzw2jbGZ/V8-00006.png" />
相关推荐：

https://github.com/davisgina32/bajxxs/blob/main/%E4%BF%9D%E5%A7%86%E5%AE%9E%E6%93%8D%E6%94%BB%E7%95%A5%EF%BC%9AV8%E5%B9%B3%E5%8F%B0%E5%BC%80%E6%88%B7_%E6%80%A7%E7%BA%B9%E7%BA%B3%E6%92%82%E9%BB%84LERGH.md

<img src="https://i.postimg.cc/SsKVxN8Z/V8-00004.png" />
相关推荐：

https://github.com/davisgina32/bajxxs/commit/7402b27497e3ff02a8c284426f95d19c9bdcd7ef

<img src="https://i.postimg.cc/2SFPqybC/V8-00015.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
