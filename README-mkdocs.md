# mkdocs

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

    docker run --name mkdoc --rm -it -p 8100:8000 \
        -v ${PWD}:/docs squidfunk/mkdocs-material
    docker exec -it mkdoc

修改md文件, 浏览器动态刷新

Build documentation

    docker run --rm -it -v ${PWD}:/docs squidfunk/mkdocs-material build

### 部署1: docker + md

    docker run --name mkdocs-asmatrix -p 8001:8000 \
        -v ${PWD}:/docs squidfunk/mkdocs-material

### 部署2: GitHub Pages

    // 默认gh-pages分支, .ssh提供github秘钥
    docker run --rm -it -v ~/.ssh/id_rsa:/root/.ssh/id_rsa \
        -e UID=1000 -e GID=1000 \
        -v ${PWD}:/docs squidfunk/mkdocs-material gh-deploy
