title: how to store hexo source and theme on github
date: 2015-12-22 13:52:16  
categories: 
- Job  
tags: 
- Tips  
- Hexo
- Github
---
When you have the ability to use hexo, you may be wonder what should we do if my device lost or 
broken, how to store and transfer my source of hexo, now you need follow below these steps:
1. init git and create branch from your blog repository  
```  
cd Hexo 
git init
git branch source
```
2. edit .gitignore and add hexo source  
```  
git  status
git  add *
git  add .gitignore
git  commit -m "add source"
```
3. push branch  
```  
git branch -a
git remote add origin https://github.com/geoxing/geoxing.github.io.git
git push --set-upstream origin source
```
4. over
