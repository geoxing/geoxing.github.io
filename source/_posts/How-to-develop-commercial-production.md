title: How to develop commercial production
date: 2015-12-08 09:03:18
categories: 
- Job  
tags: 
- Requirements;
- Develop
- Design
- Integration
- Operation
- Analysis
- Cycle
---
***TO be continue***
<!-- toc -->

# Indicators  
## Tech indicators  
### Security
### Stability
### Availability
1. MTBF (Mean Time Between Failure)
2. MTTR (mean time to restoration)
3. Availability = (MTBF/(MTBF+MTTR))*100%

### Performance
## Operation indicators
### Trading volume
### CVR (Click Value Rate)
### User account
### PV/UV
### Bounce Rate
# Development Cycle
## Requirements
### BackLog
### User Story
### UISpec
## Design
### Design drawing
### html & CSS
## Develop
### develop Environment:
1. [github Boxen](https://github.com/boxen/)  for ios
2. [vagrantup](https://www.vagrantup.com/)

### Version Manage Tools: git
### Package Manager:  
#### OS level
1. BSD/Macos: homebrew(made of ruby& git)
2. Linux  
 - from source: configure/make/make install
 - using rpm/dpkg(hard mode): ==> centos/debian(ubuntu)
 - using yum/apt(easy mode): ==> centos/debian(ubuntu)

#### Language level
1. .net: nuget
2. java: maven
3. sacla: sbt
4. ruby: gem
5. jsp: npm
6. swift: spm
7. python:
 - easy install (setuptools), can't support uninstall
 - pip (good)
8. go: get

### Branchs Manage: master  develop
### Develop Process: Scrum
### Engineering: CI (Continuous interaction) / CD(Continuous delivery) / platformization / Framization
### Timer: 2 weeks
### FrontEnd
### BackEnd focus
#### High Scalability: timeout
#### Performance: cache/parallelization
Stress Testing tool:
- TSung: TCPCopy
- A/B test

#### debug
1. keep context: no reboot, gcore/jmap/tcpdump
2. restore context: tcpcopy,touchstone
3. snap analysis: gdb、Xmap、mat、jstack
4. call analysis: btrace、Xtrace
5. composed ansysis: perf、Xstat、Xtop、sysdig



#### Security
## Integration
### tools
1. jenkins 

### process
#### one project, one build  for small business  
- Project Architecture diagram  
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci1.png)
- develop process diagram  
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci1p.png)
- Quality Assurance  
hand-test
#### multi-projects, one build for mid business  
Module num > 20  
develop num > 100  
- Project Architecture diagram  
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci2.png)
- develop process diagram:
commit role: from dev to bundle
commit way: from committing code  to repositories
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci2p.png)
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci2d.png)
- Quality Assurance  
make code review platform  
make bundle platform  
make buider platform  
make test platform  
make insepection platform  
make gray release process  
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci2q.png)
#### multi-projects, multi-build, pluginization for large business
every Module is individual on the develp,code review,integration,test
- Project Architecture diagram  
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci3.png)
- develop process diagram:
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci3p.png)
bundle dev phase  
integration phase  
release phase  
- Quality Assurance: CI,CD    
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci3q.png)

#### e.g 
* web develop process (from zhihu)
 1. Erect task on phabricator
 2. commit diff and relating to task
 3. unit test
 4. code reviewer
 5. merge code
 6. online test  
 7. close task  
* android 
 1. Genymotion (android emulator)
* mobile quality assurance (from meituan)  
  ![image](https://raw.githubusercontent.com/geoxing/photos/master/meituanQA1.PNG)  
  ![image](https://raw.githubusercontent.com/geoxing/photos/master/meituanQA2special.PNG)  
 
### Static resource optimization
### Static code  review
0. regulation: google's C++ coding style guide for all dev languages
1. [phabricator](http://phabricator.org/) from facebook  (good)
2. gerrit

### **Develop output check**
### Build tools
1. [buildout](https://github.com/buildout/buildout) for python
2. gradle for android build 
3. maven 

### Version and config file
### deploy tools
1. fabric
 * made of python
 * <10 servers
 * servers status are same
2. chef/puppet
 * made of ruby
 * slow
3. salt/ansible (good) 
4. Docker (best,final)

### route: BGP((Border Gateway Protocol), one IP, support accessing from Various Operators 
### CDN: 
### VPS(Virtual Privates Srever)
* ailiyun
* qingcloud
* digitial ocean
* linode
* aws

### Releases for various platform 
## Operation
### improve abailability  
 1. Avoid single point of failure:network/Device/code problem
 2. Narrow time of failure (imporant)
  - automate
  - one click 
 3. Cure:
  - for stateless instance
    ![image](https://raw.githubusercontent.com/geoxing/photos/master/solvestateless.PNG)
  - for state instance  
    HA:master-salve  
	Paxos/raft  
    ![image](https://raw.githubusercontent.com/geoxing/photos/master/solvestate.PNG)
  - for cluster  
    downgrade  
	limit crowding  
	automatic scaling  
	fast fallback
  - for data center: multi-IDC  
  - for local city  
    ![image](https://raw.githubusercontent.com/geoxing/photos/master/solvelocalcity.PNG) 
  - for domestic  city 
    ![image](https://raw.githubusercontent.com/geoxing/photos/master/solvelocalcity.PNG) 
  - for global
  
### Monitor and Warning
1. zabbix+graphite(zhihu)
2. xiaomi open-falcon
3. supervisor

#### Log from frontend to backend
##### exception log 
##### performance log
##### Visit log
##### Influence log
##### trace log
##### e.g
1. [zhihu's log](https://github.com/zhihu/kids)

#### Profiling everything
1. for backend 
 - gperftools
 - perf
 - gprof
```
gcc -pg a.c -o a
./a
gprof ./a
```
2. for frontend

#### User Actions
## Data Analysis
### Data Sample
### PV/UV/BounceRate..
### A/B Test
## Recurrence 