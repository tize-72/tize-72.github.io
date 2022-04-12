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

```