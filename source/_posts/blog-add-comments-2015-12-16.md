title: 给网站添加了畅言评论
categories: Hexo
---

首先打算用多说评论，但是始终没有成功。后修改为畅言评论。

1. 注册畅言账号
   完成注册后，获取PC端代码

2. 添加评论代码
   在 navy 主题的/home/hexo/site/themes/navy/layout/partial/comment.swig 文件中添加获取的代码。

hexo g
hexo d

重新部署后，就能看到评论了。
