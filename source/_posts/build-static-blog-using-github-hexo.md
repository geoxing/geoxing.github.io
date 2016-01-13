title: 'Build static blog using github & hexo on windows'
date: 2015-12-07 15:54:33
categories: 
- Job  
tags: 
 - Github
 - Hexo
 - Window
---

## Configure environment
1. install git , please ref link: http://www.cnblogs.com/zhcncn/p/3787849.html  
2. install node.js , download ：http://nodejs.org/download/,node-v0.10.33-x64.msi

## Configure Github

###  Create a Repository from github pages  
1. Registe a account（optional）  
1. Choose a free personal plan.（optional）  
1. Verify your mail（optional）  
1. Make new Repository which must be corresponding to your user name and named your_user_name.github.io  
1. In master branch，Repository setting，overwrite automatic page generator  
6. Create a github user pages site（optional）  
7. Choose a theme（optional）  
8. Publish（optional)  

<!-- more --> 

###  Make a SSH-Key for your computer  

## Install Hexo  
### Install npm (optional)  
### Install Hexo
excute:  
```
npm install -g hexo  
```
npm will finish all work
### Quick Start   
#### Setup your blog  
make a folder named "Hexo", for instance,"d:\hexo",right click ,open "git bash",execute:  
```
hexo init  
Copying data  
You are almost ! Dont forget to run `npm install` before you start b  
logging with Hexo!    
```
Hexo will create files building website needed in the target folder, follow the tips,execute in the dir(d:\hexo):  

```
npm install
```
node_modules will be install in the dir (D:\Hexo)    
####  Start the server  
execute int the dir (D:\Hexo)
```
$ hexo server
[] Hexo is running at http:localhost:4000/. Press Ctrl+C to stop.
```
Above,it indicates Hexo Server is already running,you can see a  blog Hexo inited after you open http://localhost:4000/ in a browser
and  stop  server  by press "Ctrl+C"  
#### Create a new post  
execute int the dir (D:\Hexo):
```
$ hexo new My New Post] File created at d:\Hexo\source\_posts\My-New-Post.md
```
refresh http://localhost:4000/, you wiill find a new post   
**NOTE**： (never happened)
sometimes, "My New Post" are created twice in the window of git bash,
>$ hexo server
[] Hexo is running at http:localhost:4000/. Press Ctrl+C to stop.
[create] d:\Hexo\source\_posts\My-New-Post.md  
[create] d:\Hexo\source\_posts\My-New-Post.md  

 After tested,when hexo server is running and  hexo new "My New Post",it will be happen,so
you should be stop server when you execute the "hexo new"  
#### Generate static files  
execute int the dir (D:\Hexo), static pages will be maked:
```
$ hexo generate
```
after fininshed, a serial files such as html,css will be produced  
#### Edit post  
hexo will generate a markdown(*.md) file in the dir(D:\Hexo\source\_posts),you can edit it.  
#### deploy onto Github  
1. install hexo-deployer-git modules :  
  ```
npm install hexo-deployer-git --save
 ```
2.  you need confiure the _config.yml before deployment,first,you can see:_config.yml
>\# Deployment  
\## Docs: http:hexo.io/docs/deployment.html  
deploy:  
  type:  
  
  and then, modified:
>\# Deployment  
\## Docs: http:hexo.io/docs/deployment.html  
deploy:  
  type: github  
  repository: git@github.com:zhchnchn/zhchnchn.github.io.git  
  branch: master  
  
3. deploy  
execute int the dir (D:\Hexo), static pages will be maked:
   ```
$ hexo deploy
  ```

 **NOTE**:  
Repository：
 * url using SSH format : git@github.com:zhchncehn/zhchnchn.github.io.git,  
   attention:  you device ssh port should be opened,otherwise ,deploy failed.
>fatal: Could not read from remote repository.
Please  sure you have the correct access rights
and the repository exists.
 * url using https format: https://github.com/zhchnchn/zhchnchn.github.io.git  

#### Test 
If browser show the page(for instance,http://zhchnchn.github.io/ ) you wanted ,it means success

#### make a summary:  
* each time ,you can follow three steps:
```
hexo clean
hexo generate
hexo deploy
```
* local debug  your codes  
  1.  execute:
    ```
    $ hexo g #generate    
    $ hexo s #start server  
    ```
  2. input:http://localhost:4000 in br owser,check it  
or  simplify:  
```
hexo s -g
```

### command summary  
#### general command  
>hexo new postName  
hexo new page pageName  
hexo generate  
hexo server   
hexo deploy  
hexo help  
hexo version  

#### composed command
>hexo deploy  
hexo server -g
    
#### simplify:  
>hexo n == hexo new  
hexo g == hexo generate  
hexo s == hexo server  
hexo d == hexo deploy  

## **sundries**  
### there's gonna be a space  behind colon in _config.yml,like this:  
 error:
>authorZhchnchn  
email@qq.com  
languagezh-CN  

  right：  
>author Zhchnchn  
email@qq.com  
language zh-CN  

### install、configure、update theme  
hexo provide many great theme, https://github.com/hexojs/hexo/wiki/Themes, for example ,hexo\themes\pacman   
#### install  
Git Shell switch to /D/Hexo ，and execute:  
```
$ git clone https:github.com/A-limon/pacman.git themes/pacman
```
#### configure  
   commute the theme  property into pacman in _config.yml  
#### update  
```
cd themes/pacman
git pull
```
**NOTE**:   
To start with backuping  _config.yml,then update  
### customize theme  
if pacman can't fulfill the demand you need,you can customize by editing the /themes/pacman/_config.yml  
#### comment  
change  the comment  property to true in /themes/pacman/_config.yml  
#### statistic  

 - commute  the google analysis  property into true in
   /themes/pacman/_config.yml

>  #### Analytics google_analytics:  
>   enable:
>   : UA-57032437-  ## e.g.  
> UA-1766729- your google analytics ID.  
> site:  ## e.g. yangjian.me
> your google analytics site or set the value as auto.

*  you need registe google analysis server to track user ID
in  the themes\pacman\layout\_partial\google_analytics.ejs,tracking code of google has been added:
```
<%  (theme.google_analytics.enable){ %>
<script type="text/javascript">
(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
})(window,document,'script','//www.google-analytics.com/analytics.js','ga');
ga('create', '<%= theme.google_analytics.id %>', '<%= theme.google_analytics.site %>');  
ga('send', 'pageview');
</script>
<% } %>
```
and it will read the values of id and site in /themes/pacman/_config.yml
if it does't work,please try add 
```
<%- partial('google_analytics') %> 
```
in the end of \themes\pacman\layout\_partial\head.ejs and in front of  
```
</head>
```

#### Custom 404 page  
1. replace  404.html in Hexo/source not in Hexo  
2. 404.html  

```
##layout: default
script ="text/javascript"="http://www.qq.com/404/search_children.js" charset="utf-8"></script
```
#### Sitemap    
1. you can install  sitemap plugin,commit your site to google

``` 
  $ npm install hexo-generator-sitemap  
```

##### add in the Hexo\_config.yml:
  >\# Extensions  
Plugins:  
   hexo-generator-sitemap    
  \#sitemap   
sitemap:  
  path: sitemap.xml  
  
##### visit http://localhost:4000/sitemap.xml, you can get sitemap,file path \sitemap.xml  
##### show the sitemap

  in the themes/pacman/ _config.yml,add 
  >menu:
  Home: /
  Archives: /archives
  Rss: /atom.xml
  Sitemap: /sitemap.xml
  
#### RSS  
1. install feed plugin,file path \atom.xml
    ```
$ npm install hexo-generator-feed
   ```

2. seal off ，edit Hexo\_config.yml,add
>\# Extensions  
Plugins:  
 - hexo-generator-feed  
 - hexo-generator-sitemap  

 >\#Feed Atom  
feed:  
 - type: atom  
 - path: atom.xml  
 - limit: 20  