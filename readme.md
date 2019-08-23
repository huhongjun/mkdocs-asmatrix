# mkdocs使用记录

## 关于本文档

本文档是mkdocs-asmatrix项目的开发文档,不是网站内容文件.

## 工作日志

2019.08.23  拿起来继续,app.asmatrix.com
  没有搜索引擎收录,如何解决?试下AWS S3
  不支持中文搜索

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
{中文文档](<http://markdown-docs-zh.readthedocs.io/zh_CN/latest/>)

## 常用命令

```!/bin/bash
mkdocs new 工程名
mkdocs serve    // 开发阶段本地服务器,可自动刷新 =>http://127.0.0.1:8000/
mkdocs build    // 生成site目录文件
gh-deploy，json，help
```

## 主题

默认包含大量美观的主题.
mkdocs
bootstrap
readthedocs
bootswatch,基于bootstrap:amelia, cerulean, cosmo, cyborg, flatly, journal, readable, simplex, slate, spacelab, united, yeti
可以自建主题

[Getting Started](https://squidfunk.github.io/mkdocs-material/getting-started/)
pip install mkdocs-material
theme:
  name: 'material'

## 发布流程

mkDocs 生成的文档只包含静态文件，因此你可以将文档部署到任意地方。
GitHub project pages 和Amazon S3 是不错的选择，只需上传 site 目录到你需要发布的位置即可。

### github发布

* 将site目录下的文件拷贝到huhongjun.github.io仓库根目录下；
* 删除原有的文件，保留CNAME，index.md改名为readme.md；
* 提交并同步，访问：huhongjun.github.io

* DNS provider 配置CNAME：app指向huhongjun.github.io
* huhongjun.github.io仓库设置自定义域名app.asmatrix.com
* 访问app.asmatrix.com

### Amazon S3发布

## 目录文件说明

\docs       md文件,用于生成静态网页
\docs-TBD   可用网站内容素材,用完即删
\site       生成静态网站目录
\word       word另存为html,同样用于提供素材或直接作为静态网站页面
mkdocs.yml  md生成网站时的菜单定义
readme.md  项目说明文档  
