VS官网地址【Q-——333307——】VS官网地址【 辋芷《888yx●vip》 】
VS官网地址【Q-——333307——】VS官网地址【 辋芷《888yx●vip》 】

 深入聊聊：Ubuntu 22.04 下 MySQL 8.0 的安装与远程连接配置

大家好，我是 [你的名字]，一名长期折腾 Linux 环境的开发者。

最近在给新买的云服务器部署环境时，又双叒叕踩了一遍 MySQL 8.0 的坑。虽然网上的教程一抓一大把，但很多都停留在“复制粘贴”层面，遇到 `Authentication plugin 'caching_sha2_password' cannot be loaded` 或者 `Access denied` 这类报错时，新手往往一脸懵。

今天这篇文章，我想以 Ubuntu 22.04 LTS 为例，手把手带大家从零完成 MySQL 8.0 的安装、安全初始化，并成功开启远程连接。这不是简单的命令堆砌，我会把每一步的原理和易错点都说清楚。

---

 第一步：更新软件源与安装 MySQL

在开始之前，请确保你的服务器可以正常访问外网。我们先运行以下命令更新软件包列表：

```bash
sudo apt update
```

接着，直接安装 MySQL 服务器：

```bash
sudo apt install mysql-server -y
```

安装完成后，MySQL 服务默认会自启动。我们可以用下面这个命令检查服务状态：

```bash
sudo systemctl status mysql
```

看到 `active (running)` 就说明安装成功了。

 第二步：安全初始化与密码设置

MySQL 8.0 在 Ubuntu 上安装后，`root` 用户默认使用 `auth_socket` 插件认证。这意味着你只能用 `sudo mysql` 进入命令行，而无法直接使用密码登录。这是很多新手卡住的第一关。

我们先进入 MySQL：

```bash
sudo mysql
```

然后修改 `root` 用户的密码和认证插件（为了远程连接，我们通常改成 `caching_sha2_password` 或 `mysql_native_password`，建议用前者，安全性更高）：

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY '你的强密码';
FLUSH PRIVILEGES;
EXIT;
```

此时，你可以用 `mysql -u root -p` 测试密码登录是否成功。

 第三步：配置远程连接

这是大家最关心的部分。单机部署没问题，但如果你要在本地电脑用 Navicat 连接，必须做以下两件事。

1. 修改配置文件绑定地址

MySQL 默认只监听 `127.0.0.1`。我们需要修改配置文件：

```bash
sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf
```

找到 `bind-address = 127.0.0.1`，将其改为 `0.0.0.0`，然后保存退出，重启服务：

```bash
sudo systemctl restart mysql
```

2. 创建远程用户并授权

“仅修改绑定还不够，必须创建专有用户。” 我们再次进入 MySQL（推荐直接使用密码登录）：

```sql
CREATE USER '你的用户名'@'%' IDENTIFIED BY '你的密码';
GRANT ALL PRIVILEGES ON . TO '你的用户名'@'%' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

特别注意： 如果你的云服务器有安全组（比如阿里云/腾讯云），一定要记得在防火墙规则中放行 3306 端口。否则本地依旧无法访问。

---

 常见报错排查（互动引导）

在配置过程中，你可能遇到以下问题：

- 报错 `ERROR 1130`：说明你的用户没有远程权限，请检查上述授权语句是否执行成功。
- 报错 `ERROR 2059`：由于 MySQL 8.0 默认加密插件问题，请尝试在连接工具中更换加密方式，或重新设置用户密码。

最后，留个互动话题： 你在部署 MySQL 时遇到过最棘手的 Bug 是什么？欢迎在评论区留言，我会挑典型问题在下一期实战排坑文章中详细解答！

如果这篇文章对你有帮助，点赞、收藏、转发 是我持续输出的最大动力。关注我，一起在 Linux 的海洋里少走弯路。

相关推荐：

https://github.com/gallowayhoward8/ohrtks/blob/main/%E8%B6%85%E8%AF%A6%E8%90%BD%E5%9C%B0%E6%89%8B%E5%86%8C%EF%BC%9AVS%E5%AE%98%E6%96%B9%E5%B9%B3%E5%8F%B0_%E7%83%A7%E5%88%80%E7%AA%8D%E7%BA%B1%E8%AF%B1TANIP.md

<img src="https://i.postimg.cc/d0w4g90d/V8-00002.png" />

相关推荐：

https://github.com/gallowayhoward8/ohrtks/commit/37d66a52e8e23ae0fd7d9eb5e9ba813a34d70245

<img src="https://i.postimg.cc/2SFPqybC/V8-00015.png" />
相关推荐：

https://github.com/reidraymond02/imvanu/blob/main/2026%E6%9D%83%E5%A8%81%E6%80%BB%E7%BB%93%EF%BC%9AVS%E5%AE%98%E6%96%B9%E6%B3%A8%E5%86%8C_%E4%BC%BC%E9%99%A1%E9%92%99%E6%97%B1%E5%9B%8AYLMUO.md

<img src="https://i.postimg.cc/nzw2jbGZ/V8-00006.png" />
相关推荐：

https://github.com/reidraymond02/imvanu/commit/1e881a85f30897d6a2ccfae866d0e9ad53916930

<img src="https://i.postimg.cc/W4Nx0Vgy/V8-00017.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
