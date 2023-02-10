---
created: 2023-02-10T21:34:43 (UTC +08:00)
tags: []
source: https://www.mrhuangtalk.com/posts/CDN/
author: Huang Wei
---

# MrHuangTalk架构升级——腾讯云CDN与AWS CDN搭建

> 如何通过腾讯云和 AWS 搭建境内外 CDN？如何使用 AWS S3 和 Cloudfront？

今年 1 月份[建立了我的个人博客](https://www.mrhuangtalk.com/posts/PersonalWebsite/) , 最开始网站和图片都放在 Github Page 上。稳定运行了一段时间后，看到不少反馈 Github Page 境内访问较慢，从此 MrHuangTalk 就可以是访问速度优化之路，经过几次搬迁和优化，从 Github Page 搬到 Cloudflare Page，后来又搬到了 Vercel，再后来又把页面中使用的图片单独拆出来放到不同的 [CDN](https://zh.wikipedia.org/zh-cn/%E5%85%A7%E5%AE%B9%E5%82%B3%E9%81%9E%E7%B6%B2%E8%B7%AF)，现在整个架构是这样的。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614161601.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614161601.png)

整个过程不用写任何代码，仅通过在网页上配置就可实现。下面讲讲实现此架构的一些关键地方，各服务商的帮助文档关键节点写的比较简单，还得自己摸索。

网站 CDN 选择[](#网站cdn选择)
---------------------

通过[测速网站](https://www.boce.com/)，选了速度最快的 Vercel。但也看到有人说测速网站是 Vercel 快，实际使用感受是 Cloudflare 快。如果你访问速度较慢，也请告知我 (mrhuang@mrhuangtalk.com)。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614165700.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614165700.png)

使用国内 CDN 服务的前提[](#使用国内cdn服务的前提)
-------------------------------

需要有一个通过 ICP 备案的域名。很不幸，从 22 年 5 月 9 日后，腾讯云就不提供默认的 CDN 域名给用户，这就意味着如果需要使用国内的 CDN 服务，必须要有一个备案的域名。

不死心看了阿里云和华为云，都没有提供默认 CDN 域名，只能使用用户自定义域名。还好 ICP 备案相对简单，只要资料填写完整，审批通过还是很容易的。

所以不得已注册了 mrhuang.sapce 域名，为了备案，干脆又建了个[我的摄影照片分享网站](https://mrhuang.space/)。也是静态网站，用了 [hugo](https://gohugo.io/) 来搭建。

[![](https://blogimg.mrhuang.space/img/commons/mrHuangSpace.jpg)](https://blogimg.mrhuang.space/img/commons/mrHuangSpace.jpg)

使用 AWS S3 搭建境内 CDN 加速服务[](#使用aws-s3搭建境内cdn加速服务)
-----------------------------------------------

虽然腾讯云也有存储桶，可以直接使用腾讯云的 CDN 实现全球加速。一开始我也是这样部署的，结果发现放在境内存储桶和 CDN 的数据（阿里云也一样），Twitter 等无法访问，导致我的 Twitter 帖子中的 Twitter Card 无法显示 。没办法，只能通过境内外分开部署解决。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614173434.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614173434.png)

### 配置 AWS S3 访问账号[](#配置aws-s3访问账号)

通过 AWS IAM 新建用户，权限设置为 “AmazonBraketFullAccess”，记录好 ID 和密匙，以及用户 ARN。

修改 S3 存储桶的权限，使新建的用户具有只读权限。Princepal 下 AWS 中填写新建用户的 ARN，Action 下配置 “s3:GetObject” 代表只读，Resource 下填写存储桶的 ARN 名称。

```
{
    "Version": "2008-10-17",
    "Id": "PolicyForCloudFrontPrivateContent",
    "Statement": [
        {
            "Sid": "Stmt1655173479141",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::895535443196:user/mrhuangtalk"
            },
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::mrhuangtalk/*"
        }
    ]
}
```

### 腾讯云创建境内 CDN[](#腾讯云创建境内cdn)

新建域名，加速区域选择中国境内，加速域名填入已经完成备案的二级域名（如：img.mrhuang.space），源站配置选择第三方 AWS S3，源站地址按格式填写。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614220930.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614220930.png)

由于 S3 为了安全性关闭了公有读，所以还需设置 “回源鉴权”，访问 ID 和密匙填入之前在 AWS IAM 新建用户时保存好的信息。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614221333.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614221333.png)

在域名管理 DNS 设置里设置好 CNAME 后，境内 CDN 加速就配置好了。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614172327.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614172327.png)

境内境外分流[](#境内境外分流)
-----------------

腾讯域名管理免费版可以通过境内、境外不同线路进行解析，境外用户解析到 AWS Cloudfront，境内用户解析到腾讯云 CDN。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614171316.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614171316.png)

配置 SSL 证书[](#配置ssl证书)
---------------------

由于 AWS Certificate Manager 申请的证书只能导入无法导出，所以在腾讯云域名管理免费申请 SSL 证书，证书申请下来后可以很方便把证书应用到腾讯云新建的境内 CDN。

下载申请好的证书，使用 Nginx 格式。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614223517.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614223517.png)

进入 AWS Certificate Manager，导入证书。注意区域选择 “美国东部 (弗吉尼亚北部)(us-east-1)”，只有美国东部的证书能用于 AWS Cloudfront CDN。

用 vs code 打开 xxx.mrhuang.space_bundle.pem，把第一部分 BEGIN CERTIFICATE 与 END CERTIFICATE 之间的内容填入证书正文，xxx.mrhuang.space.key 的内容填入证书私钥。注意必须是 RSA 格式的私钥。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614224308.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614224308.png)

AWS Cloudfront 使用导入的证书[](#aws-cloudfront-使用导入的证书)
-------------------------------------------------

为 S3 配置好 Cloudfront CDN 后，增加与腾讯云一致的自定义域名，并使用刚刚导入的证书。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614225831.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614225831.png)

通过 dig 命令简单测试下，不同地址访问 img.mrhuang.space 相应的域名，境内返回腾讯云 CDN 地址，境外返回 AWS CDN 地址。

通过 [Twitter Card Validator](https://cards-dev.twitter.com/validator) 验证成功，至此所有配置完成。

[![](https://blogimg.mrhuang.space/img/2022-06-14/20220614231019.png)](https://blogimg.mrhuang.space/img/2022-06-14/20220614231019.png)
