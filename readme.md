# mkdocs使用记录

## 安装

```!/bin/bash
conda -create -n mkdocs python=3.6
pip install mkdocs
pip install mkdocs-bootstrap
pip install mkdocs-bootswatch

D:/miniconda3/scripts/activate mkdocs
```

## 参考

[官方文档](http://www.mkdocs.org/#mkdocs)
{中文文档](<http://markdown-docs-zh.readthedocs.io/zh_CN/latest/)>

## 常用命令

```!/bin/bash
mkdocs new 工程名
mkdocs serve
mkdocs build
gh-deploy，json，help
```

## 主题

默认包含大量美观的主题.
mkdocs
bootstrap
readthedocs
bootswatch,基于bootstrap:amelia, cerulean, cosmo, cyborg, flatly, journal, readable, simplex, slate, spacelab, united, yeti
可以自建主题

https://squidfunk.github.io/mkdocs-material/getting-started/
pip install mkdocs-material
theme:
  name: 'material'



## 发布

MkDocs 生成的文档只包含静态文件，因此你可以将文档部署到任意地方。GitHub project pages 和Amazon S3 是不错的选择，只需上传 site 目录到你需要发布的位置即可。

github发布
    * 将site目录下的文件拷贝到huhongjun.github.io仓库根目录下；
    * 删除原有的文件，保留CNAME，index.md改名为readme.md；
    * 提交并同步，访问：huhongjun.github.io

    * DNS provider 配置CNAME：app指向huhongjun.github.io
    * huhongjun.github.io仓库设置自定义域名app.asmatri.com
    * 访问app.asmatrix.com