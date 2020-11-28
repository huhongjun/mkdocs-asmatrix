# TDemo网站建设

## 工作日志

- 2019.12.29  远端github仓库demo改为私有，提交全部内容，以后可以生成产品和全集两个站
- 2019.12.22  整理完照片后回到这里继续=》图片都归入相册，url引用
- 2019.08.23  拿起来继续,app.asmatrix.com

## ToDo

- 没有搜索引擎收录,如何解决?试下AWS S3
- 不支持中文搜索

## 搭建环境

D:/miniconda3/scripts/activate mkdocs

pip install mkdocs-material
pip install pymdown-extensions

mkdocs serve

## 网站发布

### docker

https://registry.hub.docker.com/r/squidfunk/mkdocs-material

Start development server on http://localhost:8000

docker run --rm -it -p 8000:8000 -v ${PWD}:/docs squidfunk/mkdocs-material

Build documentation

docker run --rm -it -v ${PWD}:/docs squidfunk/mkdocs-material build

Deploy documentation to GitHub Pages

docker run --rm -it -v ~/.ssh:/root/.ssh -v ${PWD}:/docs squidfunk/mkdocs-material gh-deploy 

### github发布

1. 将ssh公钥加入github账号

2. 自动提交site

    ~~~ sh
    git add remote origin https://github.com/huhongjun/demo.git
    mkdocs gh-deploy -c
    curl https://huhongjun.github.io/demo
    ~~~

3. 手工提交site 

* 将site目录下的文件拷贝到huhongjun.github.io仓库根目录下；
* 删除原有的文件，保留CNAME，index.md改名为readme.md；
* 提交并同步，访问：huhongjun.github.io；

4. 域名绑定 

* DNS provider 配置CNAME：app指向huhongjun.github.io
* huhongjun.github.io仓库设置自定义域名app.asmatrix.com
* 访问app.asmatrix.com 或 app.asmatrix.com/demo

5. 关于GitHub Pages

huhongjun.github.io是个特殊的仓库，直接访问master作为网站；
其他仓库如demo自己的gh-pages分支，访问方式为https://huhongjun.github.io/demo，GitHb用何种方式为所有public的仓库提供静态网站。huhongjun.github.io仓库自己的gh-pages不能访问。


### Amazon S3发布

## 相关信息

图床    
* 本地地址    http://192.168.1.122/ImageLib/11-产品截图/ 
* 发布到公网再统一修改

素材
* TDemo-docu
* 11-产品截图
* 本地00-inbox目录

工具
* Bitvise sftp上传文件
* BeyondCompare远程同步文件
* vscode远程资源管理器

访问统计
google_analytics: ['UA-1836522-6', 'asmatrix.com']
