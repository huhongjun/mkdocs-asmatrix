# mkdocs

## intro

git config --local pull.rebase false

--config-file ../my-project/mkdocs.yml

## miniconda3

    conda create -n mkdocs
    activate mkdocs
    pip install mkdocs-material pymdown-extensions
    
    mkdocs serve            # live server,update md files ...

    mkdocs gh-deploy -c     # deploy to github pages, open https://huhongjun.github.io/site-desktop

    mkdocs gh-deploy --config-file ../my-project/mkdocs.yml --remote-branch master

## docker

Mount the folder where your mkdocs.yml resides as a volume into /docs:

    docker run --rm -it -p 8000:8000 -v ${PWD}:/docs squidfunk/mkdocs-material

Start development server on http://localhost:8100

    docker run --name mkdoc --rm -it -p 8100:8000 -v ${PWD}:/docs squidfunk/mkdocs-material
    docker exec -it mkdoc

Build documentation

    docker run --rm -it -v ${PWD}:/docs squidfunk/mkdocs-material build

Deploy GitHub Pages

    // default gh-pages branch, .ssh include github private key
    docker run --rm -it -v ~/.ssh/id_rsa:/root/.ssh/id_rsa -e UID=1000 -e GID=1000 \
        -v ${PWD}:/docs squidfunk/mkdocs-material gh-deploy

## docker-compose

    docker-compose up -d    # open http://localhost:8300

    docker exec -it  mk-asmatrix sh
    docker exec -it  mk-asmatrix git init && mkdocs build && mkdocs gh-deploy --clean --force

    git init && mkdocs gh-deploy -r git@github.com:huhongjun/huhongjun.github.io.git -b gh-pages-asmatrix --force