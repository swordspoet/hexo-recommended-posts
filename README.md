[![npm version](https://badge.fury.io/js/hexo-recommended-posts.svg)](https://badge.fury.io/js/hexo-recommended-posts)
[![Join the chat at https://gitter.im/hexo-recommended-posts/Lobby](https://badges.gitter.im/hexo-recommended-posts/Lobby.svg)](https://gitter.im/hexo-recommended-posts/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

# Hexo跨博客文章推荐插件
此插件通过文章推荐的方式帮助大家推广博客，是借助人工智能，实现的友情链接的升级换代。它从推荐引擎里获取文章推荐列表，列表里既有您博客的内部文章链接，也有使用此服务的其他博主的外部链接，自动，精准，公平的实现文章互推。

在安装使用之前，您可以[实时预览](http://hui-wang.info/2017/12/02/%E5%AD%A6%E4%B9%A0%E5%A6%82%E4%BD%95%E5%AD%A6%E4%B9%A0/)该插件的效果。

# 如何使用
## 1. 安装文章推荐插件：

```
npm install hexo-recommended-posts --save
```

## 2. 下载推荐文章列表

在编辑完新的文章之后，使用如下命令获取推荐列表
```
hexo recommend
```

# 自定义

本插件可以在零配置的情况下直接使用。

如果默认配置不能满足您的需求，您可以在博客根目录的`_config.yml`里覆盖默认配置：
```
recommended_posts:
  server: https://api.truelaurel.com #后端推荐服务器地址
  timeoutInMillis: 10000 #服务时长，超过此时长，则使用离线推荐模式
  internalLinks: 3 #内部文章数量
  externalLinks: 1 #外部文章数量
  autoDisplay: true, #自动在文章底部显示推荐文章
  titleHtml: <h1>推荐文章<span style="font-size:0.45em; color:gray">（由<a href="https://github.com/huiwang/hexo-recommended-posts">hexo文章推荐插件</a>驱动）</span></h1> #自定义标题
```

## 如何自定义推荐文章的显示位置？

首先，您需要关闭推荐文章的自动显示 `autoDisplay: false`。
其次，您需要自定义您的博客主题，Hexo有两个比较流行的渲染器：
- EJS ：请参看[hexo-theme-freemind](https://github.com/wzpan/hexo-theme-freemind/pull/77/files)的配置
- SWIG：请参看[hexo-next-theme](https://github.com/iissnan/hexo-theme-next/pull/2054/files)的配置

## 当无法连接推荐服务器时，插件如何工作？

当服务器无法使用时，对旧文章，插件会使用原有的推荐列表；对新文章，将使用离线推荐算法推荐内部文章。

# 致谢

我想感谢朋友们对此插件的贡献，谢谢他们极具建设性的意见和快速的测试反馈
- [reuixiy](https://reuixiy.github.io/)
- [sd44](http://sd44.github.io/)
