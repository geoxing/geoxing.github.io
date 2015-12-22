title: add local images using github as imagebed in markdown
date: 2015-12-18 11:19:03
categories: 
- Job  
tags: 
 - Github
 - Markdown
 - Hexo
---
In the post [How to develop commercial production](http://geoxing.github.io/2015/12/08/How-to-develop-commercial-production/)  
I get a problem，like the expression shown: 
```
- Project Architecture diagram  
![image](file:E:\geoxing.github.io\ci1.png)
- develop process diagram  
![image](file:E:\geoxing.github.io\ci1p.png)
- Quality Assurance  
hand-test
#### multi-projects, one build for mid business  
Module num > 20  
develop num > 100  
- Project Architecture diagram  
![image](file:E:\geoxing.github.io\ci2.png)
- develop process diagram:
commit role: from dev to bundle
commit way: from committing code  to repositories
![image](file:E:\geoxing.github.io\ci2p.png)
![image](file:E:\geoxing.github.io\ci2d.png)
- Quality Assurance  
make code review platform  
make bundle platform  
make buider platform  
make test platform  
make insepection platform  
make gray release process  
![image](file:E:\geoxing.github.io\ci2q.png)
#### multi-projects, multi-build, pluginization for large business
every Module is individual on the develp,code review,integration,test
- Project Architecture diagram  
![image](file:E:\geoxing.github.io\ci3.png)
- develop process diagram:
![image](file:E:\geoxing.github.io\ci3p.png)
bundle dev phase  
integration phase  
release phase  
- Quality Assurance: CI,CD    
![image](file:E:\geoxing.github.io\ci3q.png)
```
and,after it is be  generated, deployed, and tested , all the images gone.  
finally, I figure out the imagebed must be used, and github may be available  
so, the steps is:  
1. create a repositories named photos on github
2. make dir named photos
3. git bash on dir
4. add images into the github
```
git init
git add *.png,*.jpg
git commit -m "add some markdown photos"
git remote add origin https://github.com/geoxing/photos.git
git push -u origin master
```
5. replace the local path by  the raw path of image on the github
6. enjoy!
 
 
