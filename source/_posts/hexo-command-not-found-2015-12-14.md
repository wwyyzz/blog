title: '解决运行hexo命令时提示hexo: command not found的问题'
---
hexo已经安装正常，重启系统后再执行hexo，出现"hexo: command not found"的提示
执行 node v 提示：
The program 'node' can be found in the following packages:
 * node
 * nodejs-legacy
Try: sudo apt-get install <selected package>


1、nvm ls 
   hexo@Hexo:~/site$ nvm ls
        v0.12.9
         v5.2.0

2、nvm use 5.2.0
hexo@Hexo:~/site$ nvm use 5.2.0
Now using node v5.2.0 (npm v3.3.12)

