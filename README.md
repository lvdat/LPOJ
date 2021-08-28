# LPOJ
[![Python](https://img.shields.io/badge/python-3.7.2-success.svg?style=flat-round)](https://www.python.org/downloads/release/python-372/)
[![Django Rest Framework](https://img.shields.io/badge/django_rest_framework-3.9.1-success.svg?style=flat-round)](http://www.django-rest-framework.org/)
[![vue](https://img.shields.io/badge/vue-2.5.2-success.svg?style=flat-round)](https://github.com/vuejs/vue)
[![travis-ci](https://travis-ci.org/Linzecong/LPOJ.svg?branch=master)](https://travis-ci.org/Linzecong/LPOJ)
[![Join-QQ-Group](https://img.shields.io/badge/Join_QQ_Group-875136693-blue.svg?style=flat-round)](https://shang.qq.com/wpa/qunwpa?idkey=dcc9d5c63a744d5c09eda5dd7f4b208451e66b42ba633ea23ec6fa4d49135825)

> Aonline judge system based on Vue.js and Django
>
> Currently used in Guangdong University of Foreign Studies
## Live at：[oj.lpoj.cn](https://oj.lpoj.cn)
## Docs：[docs.lpoj.cn](https://docs.lpoj.cn)

## Introduction
+ Lightweight, easy to deploy and customize
+ Separation of front and back ends to improve server performance
+ Support multi-machine and multi-process judgment, making judgment more efficient
+ Support C/C++/Java/Python2/Python3/Swift5.1
+ Support Special Judge and multiple choice questions
+ API, open source code
+ Save and export code templates with one click
+ **Support template test function similar to LeetCode**
+ **New class management and homework assignment function**
+ Modern interface + mobile phone adaptation
+ Real-time crawling of custom user blogs and other OJ questions
+ Rich algorithmic knowledge and systematic problem set training

## 模块列表
+ [Front end Vue.js](https://github.com/Linzecong/LPOJ/tree/master/Frontend)
+ [Mobile Front end Vue.js](https://github.com/Linzecong/LPOJ/tree/master/FrontendMobile)
+ [Backend Djangorestframework](https://github.com/Linzecong/LPOJ/tree/master/Backend)
+ [Judge Server Python](https://github.com/Linzecong/LPOJ/tree/master/JudgerServer)
+ [Judger produce Python](https://github.com/Linzecong/LPOJ/tree/master/Judger)
+ [Crawler Python](https://github.com/Linzecong/LPOJ/tree/master/CrawlingServer)


## Deploy using Docker

### Preparing

### 1. Install the necessary dependencies
```
sudo apt-get update
sudo apt-get install -y git
sudo apt install docker.io -y
sudo apt install docker-compose -y
```

### 2. Start installation

```
git clone https://github.com/lvdat/LPOJ.git && cd LPOJ
```
if you want to use original version, following by:
```
git clone https://github.com/Linzecong/LPOJ.git && cd LPOJ
```


**Please modify the database password in docker-compose.yml (all DB_PASSWORD, MYSQL_ROOT_PASSWORD fields) and some settings you think are necessary**

**Please make sure that the 4406 8080 8000~8002 9906 port on the machine is not occupied!**

```
sudo docker-compose up -d --scale judger=3
```

The above command turns on 3 judging machines by default, and you can modify the number by yourself


According to the network speed and configuration, it can be automatically set up in about 10 to 20 minutes, without manual intervention in the whole process.

Wait for the command execution to complete, and then run **sudo docker ps -a** When you see that the status of all containers is Up, it means that OJ has started successfully.

### 3. Ready to work

1. After the installation is successful, first visit OJ through IP:8080 and register a user

2. Then enter IP:8000/admin and log in to the background with the username **admin** and password **admin** (please modify the background password in time, this background function is only used to modify the administrator authority, so there is no pattern)

3. Modify the type of the super user you registered in the User table to 3, so that the user you registered becomes a super administrator

4. Log in as an administrator, enter the administrator page in the upper right corner, and then on the website settings tab, submit the settings once

### 4. Update OJ

To update OJ, just perform the following steps in the LPOJ directory
```
git pull # If you modify the code, solve the merge situation yourself
sudo docker-compose stop
sudo docker-compose pull
sudo docker-compose up -d --scale judger=3
```

**The data generated when the container is running will be saved in the corresponding folder, such as database files, title data, etc.**

## Custom OJ

首先先下载源代码
```
git clone https://github.com/Linzecong/LPOJ.git && cd LPOJ
```

然后随意修改你要修改的地方，修改完毕后，使用如下命令重新部署

```
sudo docker-compose -f docker-compose-build.yml up -d --build --scale judger=3
```

同样的，您需要修改**docker-compose-build.yml**中的配置，详见**开始安装**

由于会重新构建整个系统，而不是拉去已构建好的镜像，所以花的时间会比较长~请耐心等待

网站的静态文件可以放在 ./Frontend/dist/img中，比如存放题目所用的图片


## 如无意外，部署成功！
具体使用，请参阅使用[文档](https://docs.lpoj.cn)

## 更新日志

3.3 更新类似LeetCode的模板题功能

3.4 更新班级管理和布置作业功能，可以在比赛中添加选择题

## 代办功能

1. 封榜功能
2. 更优秀的排行榜显示（现在人数多了会卡）

## 部分截图

![image1](https://www.lpoj.cn/githubimage/image1.png)

![image2](https://www.lpoj.cn/githubimage/image2.png)

![image3](https://www.lpoj.cn/githubimage/image3.png)

![image4](https://www.lpoj.cn/githubimage/image4.png)

![image5](https://www.lpoj.cn/githubimage/image5.png)

![image6](https://www.lpoj.cn/githubimage/image6.png)

或者你可以直接访问我们  [oj.lpoj.cn](https://oj.lpoj.cn)

## 浏览器支持

Modern browsers(chrome, firefox)

## 特别感谢

+ 广东外语外贸大学ACM集训队所有成员
+ 广东外语外贸大学集训队所有老师
+ [青岛大学在线评测系统](https://github.com/QingdaoU/OnlineJudge)
+ [24OI/OI-wiki](https://github.com/24OI/OI-wiki)



## 许可

The [MIT](http://opensource.org/licenses/MIT) License
