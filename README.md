# TDemo网站建设

## ToDo

- 没有搜索引擎收录,如何解决?试下AWS S3
- 不支持中文搜索

## Windows 10

    D:/miniconda3/scripts/activate mkdocs
    pip install mkdocs-material
    pip install pymdown-extensions
    mkdocs serve
    // 编辑修改md文件...
    mkdocs gh-deploy -c
    curl https://huhongjun.github.io/demo

## docker

### 开发

Start development server on http://localhost:8100

    docker run --rm -it -p 8100:8000 \
        -v ${PWD}:/docs squidfunk/mkdocs-material

修改md文件, 浏览器动态刷新

Build documentation

    docker run --rm -it -v ${PWD}:/docs squidfunk/mkdocs-material build

### 部署1: docker + md

    docker run --name mkdocs-asmatrix -p 8001:8000 \
        -v ${PWD}:/docs squidfunk/mkdocs-material

### 部署2: GitHub Pages

    // 默认gh-pages分支, .ssh提供github秘钥
    docker run --rm -it -v ~/.ssh:/root/.ssh -v ${PWD}:/docs squidfunk/mkdocs-material gh-deploy

## 相关信息

图床

- 本地地址    http://192.168.1.122/ImageLib/11-产品截图/ 
- 发布到公网再统一修改

素材

- TDemo-docu
- 11-产品截图
- 本地00-inbox目录

访问统计: google_analytics: ['UA-1836522-6', 'asmatrix.com']
