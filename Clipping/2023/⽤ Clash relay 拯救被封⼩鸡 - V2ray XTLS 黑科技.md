---
created: 2023-02-12T22:56:21 (UTC +08:00)
tags: []
source: https://v2xtls.org/%E2%BD%A4clash-relay%E6%8B%AF%E6%95%91%E8%A2%AB%E5%B0%81%E2%BC%A9%E9%B8%A1/
author: v2xtls
---

# ⽤Clash relay拯救被封⼩鸡 - V2ray XTLS黑科技

> 其实已经看到很多人这样用了，但一直没有一个完整的体系化的教程，也没有把负载均衡和故障转移这些分组和 relay 结合起来，所以就写了这个帖子，希望能帮到你们 - ⽤ Clash relay 拯救被封⼩鸡 V......

> 原文链接：[https://hostloc.com/forum.php?mod=viewthread&tid=1097176](https://hostloc.com/forum.php?mod=viewthread&tid=1097176)
> 
> 作者：sakichenan

序言
--

关于代理，一直以来分成两派：自建 & 机场，但是各有优缺点：

自建：保护隐私、可以⾃⼰折腾，但⼀遇到被阻断，就得深夜焦头烂额地换新配置、换 ip 、换端口，或者某天路由变了速度就突然变很慢！

机场：看⽚记录被公开挂出来、访问某网站访问不了。

那么有没有一种可以⼜快⼜稳⼜保护隐私⽆审计的办法呢？

有的！答案就是 **Clash Relay Group + Prxoy Provider + LoadBlance/Fallback。**

![](https://pic.noco.eu.org/file/1353007b7d705aeeee17c.png)

Clash relay 拯救被封⼩鸡原理
--------------------

Clash 的 relay 分组会把组内节点串成一个代理链，只需要将机场节点作为前置节点，⾃建节点作为后置节点，相当于只把机场作为跨境隧道，最终落地解密出真实流量的还是我们的⾃建节点。

你的电脑 <-> 机场 <-> ⾃建节点 <-> 交友⽹站

这样⼀来，机场不知道我们实际访问的⽹站，⽽我们的⾃建节点通过机场过境，也不怕被封了！  
**还可以购买很便宜的落地机，因为不⽤关⼼线路了！**

这样就既能享受机场的便捷、⼜能保护⾃⼰的隐私了！

⾃建节点那边就算服务商有记录、也不知道我们的实际 ip 、只能看到机场的 ip ，

是不是和 iCloud Private Relay ⼀样厉害！那我们就把这种⽅法叫做 **iRimo Private Relay** 吧！

好！怎么实现呢？

Clash relay 拯救被封⼩鸡教程
--------------------

### 超级简洁版教程

我准备了⼀份写好的配置⽂件：[https://gist.github.com/miaomiaoclub/6947f7cb93846301f1658da0edcd61bf](https://gist.github.com/miaomiaoclub/6947f7cb93846301f1658da0edcd61bf)

下载下来、把机场节点塞进去、把⾃建节点塞进去就可以⽤了！

随便找⼀个订阅转换的⽹站，⽐如说 sublink.dev , 把订阅链接放进去，客户端选 Clash ，然后点**进阶选项，在左下⾓找到 “转换为 NodeList” 勾选上**，最后点⽣成订阅链接，复制粘贴到第 19 ⾏。

然后在第 7 ⾏的 proxies 下⾯填上你⾃建的节点（不要改 - name: “你的⾃建节点” 这⼀⾏！如果改了的话要把第 36 ⾏也改成新名字！）

最后把改好的配置⽂件导⼊ Clash 就可以⽤了！

### 完整版教程

⾸先了解⼀下 Clash 的配置⽂件，主要有这么些字段：

```
proxies:
proxy-providers:
proxy-groups:
rules:

```

我们主要关注这四个就可以，如果你不知道怎么写其余部分，完整的配置可以去 github 的 wiki ⾥边看，或者直接找⼀份来⾃⼰改，⽐如直接⽤机场的配置⽂件改！

#### 第⼀步，我们要把机场的节点放进去！

随便找⼀个订阅转换的⽹站，⽐如说 sublink.dev , 把订阅链接放进去，客户端选 Clash ，然后点进阶选项，在左下⾓找到 “转换为 NodeList” 勾选上，最后点⽣成订阅链接。

然后把链接复制出来这样填：

```
proxy-providers:
    jichang:
        type: http
        path: ./jichang.yaml
        url: # ⽣成的订阅链接填在这⾥！
        interval: 3600
        health-check:
            enable: true
            url: https://www.gstatic.com/generate_204
            # 使⽤https 防⽌⽆良⽼板伪造延迟！
            interval: 300

```

有些机场有好多地⽅的节点，为了我们⽅便写负载均衡和故障转移，可以把我们⾃建节点所在地区的节点单独过滤出来。

⽐如我⾃建的节点在美国，就像这样写（ Clash ⽂档⾥没写这个，独家的！）：

```
    美国的节点:
        type: file # 这⾥是 file了！因为不需要再从⽹络获取
        path: ./jichang.yaml #这⾥路径就填和上⾯⼀样的
        filter: "US|美国" #正则表达式
        health-check:
             enable: true
             url: https://www.gstatic.com/generate_204
             # 使⽤https 防⽌⽆良⽼板伪造延迟！
             interval: 300

```

最后还需要⽤⼀个分组来包含这些节点，在 groups 下⾯这样写：

```
proxy-groups:
  - name: 机场的分组
    type: select
    use: # provider 的节点要放在 use 下⾯
      - jichang
    proxies:
      - DIRECT # use 是可以和普通的节点混⽤的！

```

#### 第⼆步，把我们⾃建的节点放进去 <

接下来把⾃建节点的配置写到 proxies ⾥⾯，这个就不需要多说了吧。

```
proxies:
  - name: "⾃建的节点"
    type: ss
    server: server
    port: 443
    cipher: chacha20-ietf-poly1305
    password: "password"

```

⼩提⽰：因为跨境段是通过机场，所以⾃建节点可以不需要再搞什么 Vmess+websocket+tls 了, 什么混淆啊伪装啊统统丢掉，直接原版 SS 就够了！

#### 最后⼀步！写 Relay Group ！

终于来了！

其实铺垫了这么多，我们只需要把 group 的 type 写成 relay ，然后把机场分组和⾃建节点放进去就可以了！（注意有先后顺序的！）

```
  - name: Relay
    type: relay
    proxies:
      - 机场的分组 #写机场分组的名字
      - ⾃建的节点

```

（如果是第⼀次接触 Clash ，有同学可能想问：那我怎么样让流量⾛这⾥呢？这是 rule 控制的，例如在 rule ⾥写 DOMAIN,google.com,Relay ，google 就会⾛这个代理分组了。不过这个不是本篇的重点，看⽂档就好！ https://lancellc.gitbook.io/clash/clash-config-file/rules ）

当然可能还有同学想问，那我偶尔想直连⾃建节点，或者只⽤机场怎么办？

这个问题有两个解决办法：

1 、Clash 的 group 是可以嵌套的（除了 relay group ⾥⾯不能套 relay group ）。

2 、relay group 中 DIRECT 节点就相当于跳过这个节点。

#### 还要更稳定！

Clash 还有三种分组：负载均衡、故障转移、⾃动选择

负载均衡：随机使⽤组内的节点。

故障转移：定时测试节点的连通性，当当前节点不通的时候就会⾃动切到可⽤的节点。

⾃动选择：定时切换到延迟最低的节点。

众所周知，这种⾃动切换的功能都会带来⼀个问题：在⽹站看来你的 ip 在不断变化，于是让你重新登陆 / 怀疑你是机器⼈。

但！

我们现在使⽤的是链式代理，这个问题⾃动被解决了！我们随便换前置！⼀秒换⼀个都可以！

```
proxy-groups:
  - name: "最低延迟"
    type: url-test
    use:
      - 美国的节点 #我们前⾯过滤出来的！忘记了就滑上去看！
    url: 'https://www.gstatic.com/generate_204'
    interval: 300
    tolerance: 50 #延迟相差 50ms 以内就不⽤切换
  - name: Relay
    type: relay
    proxies:
      - 最低延迟
      - ⾃建的节点

```

或者负载均衡：

```
proxy-groups:
  - name: "随机选！"
    type: load-balance
    use:
      - 美国的节点
    url: 'http://www.gstatic.com/generate_204'
    interval: 300
   #lazy: true
   #disable-udp: true
    strategy: round-robin #作为前置节点⽤这个⽐较好
  - name: Relay
    type: relay
    proxies:
      - 随机选！
      - ⾃建的节点

```

还可以买好多个机场来做故障转移 balabala……，唔，再说下去就不好玩了，⼤家都是很厉害的⼈，肯定能想到的！

### 结尾

其实已经看到很多人这样用了，但一直没有一个完整的体系化的教程，也没有把负载均衡和故障转移这些分组和 relay 结合起来，所以就写了这个帖子，⼀共花了两个⼩时，但是因为⼀直被猫猫骚扰所以⽤了⼀天才写完！希望能帮到你们！

回复⾥⼤家提了很多问题！但 Knna 酱⼜在催我陪她了，所以今天先不写 QA 了！你们这么聪明⼀定可以⾃⼰想到答案!

疑问解答
----

请参考：  
[https://hostloc.com/forum.php?mod=viewthread&tid=1096161](https://hostloc.com/forum.php?mod=viewthread&tid=1096161)  
[https://hostloc.com/forum.php?mod=viewthread&tid=986143](https://hostloc.com/forum.php?mod=viewthread&tid=986143)

对！

> 2、机场太多人用了会造成运算拥堵，把它作为中转，流量的解密放在自己的小小鸡上，能大大提高效率

错！机场依然需要解密流量，但解密出来的流量还是是加密的，我们的⾃建节点会做第⼆次解密！  
这也是为什么这个⽅案可以保护隐私，因为机场看到的是 Shadowsocks/Vmess 的加密流量！

> 3、机场和小鸡都必须要稳定，两者缺一都会造成稳定性问题，好在机场能自动筛选最低延迟，小鸡的话尽可能买好的线路

**错！⽤了这个⽅案就不⽤关⼼服务器的线路了！三⽹优化什么的统统忘掉！**  
机场好坏也⽆所谓，因为做了故障转移和负载均衡！

> 5、能避免谷歌验证码  
> 6、能长期保持访问的 ip 是固定的，不会乱跳

对！因为⽹站看到的 ip 只有你⼀个⼈⽤！⾮常⼲净！

好啦！今天的问答环节就到这⾥！

其他
--

补充一个 v2ray 的同类方案：[https://hostloc.com/forum.php?mod=viewthread&tid=986143](https://hostloc.com/forum.php?mod=viewthread&tid=986143)
