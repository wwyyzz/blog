title: hexo中插入图片
---
## 方式一

    {\% img [class names] /path/to/image [width] [height] [title text [alt text]] \%}

对于hexo，使用本地路径：在/source目录下新建一个img文件夹，将图片放入该文件夹下，插入图片时链接即为/img/图片名称。

插入时可以修改图片大小。该方式对于 _post 下和其他目录下的MD文件都可以生效。 


## 方式二

    {\% asset_img slug [title] \%}

Hexo提供一种更方便的方法来管理这些资源（Assets）。想使其生效，首先修改 post_asset_folder 字段的设置，将其值改为 true 。

当生效后，在你创建文章的时候，Hexo会创建一个同名目录，你可以将该文章关联的资源全部放到该目录下。这样就可以更加方便的使用它们了。

该方式不知道为什么只对 _post 中的文章生效。
