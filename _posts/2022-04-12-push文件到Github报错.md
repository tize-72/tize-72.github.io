---
tags : Github
title : push文件到Github报错
date : 2022-04-12
layout : post
---
### 报错信息
```
Username for 'https://github.com': tize-72
Password for 'https://tize-72@github.com': 
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more information.
fatal: Authentication failed for 'https://github.com/tize-72/tize-72.github.io.git/'
```
### 网上的一个博客给的方法
https://blog.csdn.net/qq_41646249/article/details/119777084

需要生成自己的token

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
然后需要把token配置一下
```
git remote set-url origin https://<your_token>@github.com/<USERNAME>/<REPO>.git
```
例如
```
git remote set-url origin https://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@github.com/github的用户名/仓库名称
```
最后提交 直接输入： git push     

就不用输入账户和密码了。

最后成功的方案是：
```
git remote set-url origin https://<your_token>@github.com/<USERNAME>/<REPO>.git
```

先把repo克隆下来，然后设置url

---

### 更新：2022-04-12下午5点

这个方法可实现pull的操作，但是每次push的时候，都会出现这种问题

```
Password for 'https://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@github.com'
```

也就是让输入密码，但是输入了多个密码都不对。。。。

突然又发现问题所在了，博客最后说的是git push就行了，我还加上了origin master这样的后缀，所以会要求输入密码，现在改成

```
git push
```

试试

### 更新：2022-04-12-20:29

上边的方法还是不行，不过这次直接搜了怎么不使用账号密码进行push和pull

这次使用是直接账号和token进行登录，没有问题