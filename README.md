# hexo_blog
基于hexo搭建的静态博客网站1.0
基于gitHub的个人博客网站

说明：使用免费的gitHub部署网站，然后利用Hexo静态博客框架搭建网站，实现伪动态更新网站。

优势：如同提交代码到仓库一样简单，实现更新个人网站，不依赖服务器，Hexo自动搭建网站框架，无需手写静态网页。

环境搭建：

1. 安装Git
2. 安装Node.js
3. 安装Hexo
4. GitHub创建个人仓库
5. 生成SSH添加到GitHub
6. 将hexo部署到GitHub
7. 设置个人域名
8. 发布文章

1、安装git工具

    sudo apt-get install git

2、安装nodejs   npm

    sudo apt-get install nodejs
    sudo apt-get install npm

3、安装hexo

    npm install -g hexo-cli

依旧用hexo -v查看一下版本

至此就全部安装完了。

接下来初始化一下hexo

    hexo init myblog
    1

这个myblog可以自己取什么名字都行，然后

    cd myblog //进入这个myblog文件夹
    npm install

    node_modules: 依赖包
    public：存放生成的页面
    scaffolds：生成文章的一些模板
    source：用来存放你的文章
    themes：主题
    ** _config.yml: 博客的配置文件**

    hexo g    //将md笔记生成静态文件
    hexo server  //运行本地服务器

打开hexo的服务，在浏览器输入localhost:4000就可以看到你生成的博客了。

4、gitHub创建个人仓库

    创建一个和你用户名相同的仓库，username.github.io，只有这样，将来要部署到GitHub page的时候，才会被识别，也就是xxxx.github.io，其中xxx就是你注册GitHub的用户名。

5、将hexo部署到gitHub上

    这一步，我们就可以将hexo和GitHub关联起来，也就是将hexo生成的文章部署到GitHub上，打开站点配置文件 _config.yml，翻到最后，修改为
    YourgithubName就是你的GitHub账户
    
    deploy:
      type: git
      repo: https://github.com/YourgithubName/YourgithubName.github.io.git
      branch: master
    
    这个时候需要先安装deploy-git ，也就是部署的命令,这样你才能用命令部署到GitHub。
    
    npm install hexo-deployer-git --save
    
    然后
    
    hexo clean   //清除静态页面
    hexo generate  //生成页面
    hexo deploy    //发布
    
    其中 hexo clean清除了你之前生成的东西，也可以不加。
    hexo generate 顾名思义，生成静态文章，可以用 hexo g缩写
    hexo deploy 部署文章，可以用hexo d缩写
    
    注意deploy时可能要你输入username和password。
    
    过一会儿就可以在http://username.github.io 这个网站看到你的博客了！！
    然后在github设置里绑定自己的域名，就可以使用域名访问个人网站了

码云部署网站文档

http://git.mydoc.io/?t=154714
