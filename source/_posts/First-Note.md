---
title: 搭建个人博客
date: 2024-01-06 17:56:21
---
### 1. 部署环境
下载<a href="https://nodejs.org/en " target="_blank">node.js</a>和<a href="https://git-scm.com/book/zh/" target="_blank">git</a><br/>
***
### 2. 配置镜像
管理员模式下，终端下载 <code>cnpm</code>:
输入<code>npm install -g cnpm --registry=https://registry.npm.taobao.orgc</code>
***
### 3. 安装框架
建<code>hexo</code>文件，在该文件目录下，右键打开<CODE>git bash</CODE>

分别输入且回车
<CODE>npm install hexo-cli -g
hexo init blog
cd blog
npm install
hexo server</CODE>
此时可以使用<a href="http://localhost:4000/">http://localhost:4000/</a>在本机访问HEXO个人博客
关闭服务器使用<code><kbd>ctrl+c</kbd></code>
***
### 4. 关联<A HREF="https://github.com/" target="_blank">GITHUB</A>
在GitHub用户页面，新建 **github用户名.github.io** 的仓库
 <code>vim _config.yml
  type: git
  repo: {[github]->[repository]->[code]->[ssh/https]->替换本行}
  branch: master</code>
***
### 5. 启动博客
<code>hexo g
hexo d</code>
若无报错，从**github用户名.github.io** 即可访问！
***
### 6. 出现报错
配置<code>git config --global user.name "yourname"
git config --global user.email“your@email.com"
</code>注意：**yourname**是你要设置的名字，**your@email**是你要设置的邮箱。
删除 **.ssh** 文件夹（直接搜索该文件夹）下的**known_hosts**（手动删除即可，不需要git）
输入
<code>ssh-keygen -t rsa -c "email@qq.com"</code>
然后一路确定
然后系统会自动在.ssh文件夹下生成两个文件，**id_rsa和id_rsa.pub**
用记事本打开**id_rsa.pub**,将全部的内容复制
返回**gitgub**，进入**setting**，找到**ssh**
将刚刚复制的粘贴进**key**中
输入<code>add ssh key</code>
在**git**中输入
<code>ssh -T git@github.com</code>
输入**yes**
重复**5.**
***
### 6.没有生成**id_rsa和id_rsa.pub**
则在该目录下使用**git**执行
<code>ssh-keygen -o</code>
重复**add ssh key**
***
### 7.参考链接
https://blog.csdn.net/jingtingfengguo/article/details/51892864
https://blog.csdn.net/Angelalcot/article/details/122359433
https://www.bilibili.com/video/BV1Yb411a7ty/?spm_id_from=333.337.search-card.all.click
https://blog.cuijiacai.com/blog-building/