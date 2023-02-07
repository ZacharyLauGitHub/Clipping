> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [zhuanlan.zhihu.com](https://zhuanlan.zhihu.com/p/541214571)

> 具体部署过程会写在最后 成果 我可以每天只通过查看单个app就可以阅览我想关注的所有信息，不用挨个打开大佬的博客看他们有没有更新，可以很轻松的看到我关注的网站又有了什么好玩的帖子，而且多端同步，实现了抓…

具体部署过程会写在最后

成果
--

我可以每天只通过查看单个 app 就可以阅览我想关注的所有信息，不用挨个打开大佬的博客看他们有没有更新，可以很轻松的看到我关注的网站又有了什么好玩的帖子，而且多端同步，实现了抓取 rss→rss 自动订阅抓取→客户端多端同步阅览的流畅体验，告别信息茧房，最重要的，折腾的很舒服！

初见
--

两年前在我初次接触 telegram 的时候我就接触 [rss] 了，当时 [rsshub] 还没有被屏蔽，初次接触觉得非常有趣，但也仅此而已了。当时啥也不会，只是照葫芦画瓢的按 rsshub 上的链接在 tg 机器人上订阅了几个常用链接而已，像是大学消息通知啥的，中间还添加了~~ 好多~~ 一些博客和网站，比如少数派啥的。

问题
--

这么一说好像也没啥缺点了，真的吗？

事实上，问题很大，telegram 上的 rss 机器人并不能看到全文，只能做一个简单的提醒，特别值得提出的是，我订阅的内容中有不少服务器位于国外（其实很好理解，我订阅很多博客，但中文互联网上就没有很好的博客环境，爱折腾愿意写博客的肯定也优先选择国外 vps 了，国内一个域名就能烦死人，而且个人来说肯定是 github pages 之类的更加稳定），那么如果我直接点击链接不是也能看吗？

问题来了，如果是 pc 还好，但我看 rss 更多的使用场景肯定还是手机，我手机上是没有科学上网的环境的，他并不能让我直接接收到内容，当然，可以费点功夫把它转成 telegraph 直接看，但这中间终究是隔了一层，并且阅读体验也说不上多好

而且还有一个非常严重的问题，许多反爬严格的网站是不能通过 rsshub 直接订阅的，一定要个人信息，只能通过自建 rsshub 来解决（或者通过其他的订阅方式，但绕来绕去感觉一般，而且安全性隐私性没有保障，虽然我大概谈不上还有什么隐私）

契机与折腾过程
-------

### rsshub

最近我开始折腾 instgram，然而由于它反爬严格，rsshub 上的订阅只支持自建，于是我开始折腾 rsshub，事实上这部分并不算繁琐，花费了我大部分精力的事情在于将它和我服务器（位于国内）上的 clash 相联动，让他能够通过科学的环境来抓取信息，看了文档总算完成（但 instgram 的环境变量设置中的 proxy 选项一直设置不正确，直到我完成了 miniflux 的搭建才顺带解决）

还有一个问题就是 twitter 个人关注线，必须要申请令牌，而且令牌还要升级，升级过程中还要写二百字英语小作文

### miniflux

但当我准备好后，那天晚上，偶然打开了酷安，偶然瞟到 rss 讨论区，里面的人说什么阅读器，我尝试着下载了两个，其中的 fluent reader lite 果味十足，深得我心，但一定要四种服务才能进去，并没有本地功能，我一看，这 fever api 是啥啊，搜索了一下

```
Fever是一种API标准，并不是RSS服务。2016年年底，该服务开发者发布声明表示不再继续开发。但由于其实用性，现在有不少RSS服务还在继续使用该API标准公开对外接口。

适配该标准的RSS服务有TinyTinyRSS, FreshRSS等。

Fever通常的表现是能读不能写，添加分类，添加订阅源的操作您都需要在您部署的RSS服务中进行。

而且通过Fever回传的数据只包含未读内容，为了保证用户体验，应用会进行文章的本地缓存。但是对于初次请求，则无法获取以前的已读文章。

如果您在不同端阅读Fever的内容发现有些文章没有同步，就是这个原因（您已读过）。

Fever在初始化时会拉取服务器的未读文章，在加载完成前你的订阅源文章列表可能是空的。在用户卡片右上角有一个进度环用于指示当前是否还处于拉取文章的状态。

```

所以我开始打算建一个 rss 服务，这样的话也能够更好的控制，简单搜索了一下，发现主流的两种：tinytinyrss,miniflux

最后我还是选择了 miniflux，本来是打算用 tts 的，因为第一个看见的就是它，但四处看了一下，发现 tts 太过笨重，还是用 php 写的，最主要的原因，我用 docker-compose 部署总是失败，明明服务也成功运行了，但是就是访问不了，端口开放也没问题，不知道怎么回事，很长时间都解决不了，还尝试了使用 docker 部署之类，太过繁琐，问题百出，而 miniflux 一下成功，选择谁就不是一个问题了

当我使用一段时间后，我发现，或许 miniflux 才是更适合我的选择，理由如下

*   miniflux 非常轻量，而我的 2 核 4Gvps 正适合他
*   我开始使用正是想通过 fluent reader lite 使用，有客户端，并不过度依赖网页，所以美观性对我来说无足轻重
*   miniflux 虽不能使用插件，但是自定义程度同样非常高，我需要的要求同样可以完美满足

具体配置过程及踩坑心得
-----------

### rsshub

*   具体配置

按官方指导就好，[rsshub 配置指导]([[https://docs.rsshub.app/install/#docker-jing-xiang](https://link.zhihu.com/?target=https%3A//docs.rsshub.app/install/%23docker-jing-xiang)]([https://docs.rsshub.app/install/#docker-jing-xiang](https://link.zhihu.com/?target=https%3A//docs.rsshub.app/install/%23docker-jing-xiang)))，打不开的话科学上网，或者找国内镜像，B 站应该有

*   踩坑分享

*   代理相关

```
    PROXY_URI : 'socks://name:password@ip:port'
    PROXY_URL_REGEX: ".*(twitter|instgram|pixiv|matters|v2ex).*"

```

rsshub 支持各种代理，我使用了 socks 服务，所以在 proxy_url 后的字符串中加上 socks

```
    代理 URI 的格式为：
    {protocol}://{host}:{port}
    {protocol}://{username}:{password}@{host}:{port} （带身份凭证）
    一些示例：
    socks4://127.0.0.1:1080
    socks5h://user:pass@127.0.0.1:1080 （用户名为 user, 密码为 pass）
    socks://127.0.0.1:1080 （protocol 为 socks 时表示 socks5h）
http://127.0.0.1:8080
http://user:pass@127.0.0.1:8080
https://127.0.0.1:8443

```

**代理选项**

`PROXY_PROTOCOL`: 使用代理，支持 socks，http，https

`PROXY_HOST`: 代理服务器域名或 IP

`PROXY_PORT`: 代理服务器端口

`PROXY_AUTH`: 给代理服务器的身份验证凭证，`Proxy-Authorization: Basic ${process.env.PROXY_AUTH}`

`PROXY_URL_REGEX`: 启用代理的 URL 正则表达式，默认全部开启 `.*`

我启用了 proxy_url_regex，其中的 ".*(twitter|instgram|pixiv|matters|v2ex).*" 也非常好理解，“.”表示任意字符，“＊”表示多个，“|”是 “或”，“（）” 表示一整个字符串，所以这段话的意思就是只要是包含括号中字符串的字符串都能被匹配到，这样的话我们就能够通过它来控制哪些网站需要开启代理抓取了

如果我要加上一个 http://youtube.com，那么我只需要在括号中加上一个 “|youtube” 就能让所有带 youtube 的网址被匹配到，那么最后这个字符串就会变成

```
    .*(twitter|instgram|pixiv|matters|v2ex).*
    .*(twitter|instgram|pixiv|matters|v2ex|youtube).*

```

*   instgram

ins 代理部分花了我很长时间排查，它只支持 http 代理，如果我没记错的话。但问题是我的 http 代理一直不能使用，到最后才发现是我之前设置的 http 代理端口开启了 ip 来源限制，建议大家以后本服务器上尽量用内网 ip（ins 封号严格，建议固定 ip，别老换设备换 ip，我已经关了这个订阅了，哈哈）

ig_proxy 的参数格式和 rsshub 的一样，我的例子：

```
IG_PROXY: 'http://name:password@ip:port'

```

*   图片处理加简繁转换

因为我订阅了一些外网的网站，比如 matters，文字还好说，可以用代理抓取，但是到了我阅读用的 app 上，很自然的，它会返回网页上的图片链接，比如 <img …src=https://…>，那么问题来了，我的手机上是看不到外网的图片的，它不能加载，非常烦人（因为我手机开了 adguard，系统限制和其他代理软件不能共存），那么，我们就需要对图片进行处理，让他返回一个我们在国内环境下能够看到的图片，简单来说，需要进行图片加速

rsshub 非常人性化，连这种问题都考虑到了，首先，我们要找一个图片代理服务，我在 github issue 里找到了两个被提到的，的确不错

```
https://i3.wp.com/${host}${pathname}
https://images.weserv.nl?url=${href_ue}

```

文档中同样有提到一个基于 cf 的服务，有兴趣可以自己找

**下面我们需要在环境变量中加上开启的选项**

在环境变量中将 `ALLOW_USER_HOTLINK_TEMPLATE` 设置为 true

然后在我们自己的订阅地址中在结尾加上 `image_hotlink_template=[https://i3.wp.com/${host}$]([https://i3.wp.com/$%7Bhost%7D$](https://link.zhihu.com/?target=https%3A//i3.wp.com/%2524%257Bhost%257D%2524)){pathname}`

如果前面有其它参数，就在前面加上 &，如果没有，加上?

举例：

https:// 你的地址 / matters/latest/essence?opencc=t2s&image_hotlink_template=[https://i3.wp.com/](https://link.zhihu.com/?target=https%3A//i3.wp.com/)${host}${pathname}

例子中，本来的订阅是 https:// 你的地址 / matters/latest/essence

后面加上 ? 表示开始加参数了，加上一个 `opencc=t2s` 表示由繁体转为简体，再加上一个 & 表示我还有参数，加上我们刚刚的选项就完成了

*   miniflux

miniflux 搭建也非常简单，下载或者新建 docker-compose.yaml 文件再输入 docker-compose up -d 就可以了

我的 docker-compose 文件如下

```
version: '3'
services:
  miniflux:
    image: miniflux/miniflux:2.0.37  #可以看github relase页面填写最新版本
    ports:
      - "port:8080"  #port改为你自己的端口
    depends_on:
      - db
    environment:
      - DATABASE_URL=postgres://miniflux:secret@db/miniflux?sslmode=disable
      - RUN_MIGRATIONS=1
      - POLLING_FREQUENCY=90  #抓取的时间，可以自己设置
      - CREATE_ADMIN=1
      - ADMIN_USERNAME=123    #初始账号密码，自己设置
      - ADMIN_PASSWORD=123
      #http代理，需要的可以设置 name和pass是代理用户名和密码,没有的可以和后面的@一起删了
      #- HTTP_CLIENT_PROXY=http://name:pass@ip:port
    restart: unless-stopped
  db:
    image: postgres:10.1
    environment:
      - POSTGRES_USER=miniflux
      - POSTGRES_PASSWORD=secret
    volumes:
      - miniflux-db:/var/lib/postgresql/data
volumes:
  miniflux-db:

```

需要注意的点：

- 版本，可以看 github 上的最新版本

- 抓取时间，自己设置

- 账号密码，自己设置

- 代理，需要的按我注释里的设置

改完之后直接在终端（打开到文件所在的页面）输入 `docker-compose up -d` 就可以了，非常方便，需要停止的话输入 `docker-compose stop`

一切就绪后输入 `http:// 你的 ip: 你的端口 /` 开始访问，如果做了反代直接访问域名就行了

*   fever api 设置

点开设置，语言选择简体中文，时区选择 `Asia/shanghai` ，然后点击第二栏的 ** 集成 **

启用 fever 后设置 fever 的用户名和密码，端点就是 http:// 你的 ip: 你的端口 / fever/

如果做了反代，直接输入域名后面加上 / fever 就行

设置好后在最上方添加分类和源，不用多说

*   代理和过滤设置

- 代理 如果设置了代理可以单独选择用代理抓取

- 过滤

看到很多人说 miniflux 不能过滤，如果大家仔细看官方文档会发现是有过滤教学的，那么怎么过滤呢？

文档说的不详细，其实刚添加源的时候我们的确不能设置，但当我们添加以后每个源都有一个 “编辑” 选项，点击以后在最下方有一个阻止规则，只要在里面按正则填写我们需要过滤的规则，就可以阻止抓取，还有另外三个规则大家可以自己研究

![](https://pic2.zhimg.com/v2-88f19d838419aed1355e752627f4de61_r.jpg)

*   fluent reader lite 客户端设置

因为我手边暂时只有安卓设备，一台手机一台平板，只能基于安卓设备来说一些简单的体验

登陆后不用多说，按设置的 fever api 填写

完成以后在信息流部分右上角可以选择显示的文章，我选择了仅未读，还可以选择全部已读，文章标题左划右划分别是已读和加星（具体动作可以在设置－订阅源里选择）。

订阅源界面左划可以选择分类已读，右划可以编辑源，但编辑后的结果不能多端同步（已读未读情况可以），可以选择默认打开方式，是抓取全网，rss 全文还是加载网页，还可以自己更换图标

![](https://pic4.zhimg.com/v2-33617be1f99f490e531c1622dc632417_r.jpg)![](https://pic3.zhimg.com/v2-dc3ff4edf259b5f04d17e679115d3f0a_r.jpg)

缺点：自定义程度不足，比如我不能选择哪个订阅源不显示未读，之前尝试将 B 站动态加入后信息量太大，承受不住，只好将社交媒体选择不添加