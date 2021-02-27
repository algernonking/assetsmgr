
## 测试Demo
- http://assets.rainbooow.com:8080/dt/console
- 账户:guest 密码:oracle
- 账户:user1 密码:oracle
- 账户:user2 密码:oracle
- 账户:user3 密码:oracle
- admin oracle
- 系统包含admin 管理用户

- 知识库访问
- http://assets.rainbooow.com:8080/dt/kn/

## 所用框架
- Spring 5.0.20
- Shiro 1.7.1
- MyBatis-Plus 3.0.7.1
- MyBatis 3.4.6
- Druid 1.2.4
- Easypoi 4.3.0
- Quartz 2.3.2
- UFLO 2.1.5(流程引擎)
- K-form-design 3.x(表单)
- Angular 1.x

![输入图片说明](https://images.gitee.com/uploads/images/2020/0729/221313_49392c48_448530.jpeg "1596031886493.jpg")

## 联系方式
- Mail:maillank@qq.com
- QQ交流群:904754434


## Docker 部署方式
- 兼容说明

| 系统版本         |   应用镜像       | 数据库镜像 |  移动端支持|
| ----------   | ------------- | ----------- |  ----------- | 
| 2.2.24 | 2.2.24 |   2.2.24 |   1.0.1|
| 2.2.23 | 2.2.23 |   2.2.23 |   1.0.1|
| 2.2.22 | 2.2.22 |   2.2.22 |    X |
| 2.2.21 | 2.2.21 |   2.2.21|    X|
  
- 部署说明  
```
其中镜像中2.2.17为版本号,替换相对于版本即可。
#部署数据库
docker run --name dt-db -t \
-e MYSQL_USER="dt" \
-e MYSQL_PASSWORD="dt_pwd" \
-e MYSQL_ROOT_PASSWORD=root_pwd \
-v /data/mysql:/var/lib/mysql  \
-p 3306:3306 \
-d docker.io/algernonking/dtmysql:2.2.24 \
--character-set-server=utf8 \
--lower_case_table_names=1

#部署应用
docker run --name dt-app -t \
-v /data/upload:/usr/local/tomcat/webapps/upload \
--link=dt-db:db \
-p 8080:8080  \
-d docker.io/algernonking/dtapp:2.2.24
```


## 传统部署方式
### 步骤一
- 准备环境
```
- 操作系统:Window、推荐Linux
- 数据库:Mysql 5.7.X
- 中间件:Tomcat 9 以上
- Java版本:Java 1.8 以上
```

### 步骤二
- 初始化sql
```
- 要求Mysql的参数:lower_case_table_names=1
- SQL>CREATE DATABASE IF NOT EXISTS dt default charset utf8 COLLATE utf8_general_ci;
- SQL>set names utf8;
- SQL>use dt;
- SQL>source db.sql
```

### 步骤三
- 发布应用,注意:最新版本的war包已经发布,请直接下载（右上角发版中）,不需要下载源代码进行编译。
```
- 将war包部署到Tomcat目录的webapps下后，修改配置文件(webapps/dt/WEB-INF/classes)中数据库的数据库配置文件config.properties
- jdbc.url=jdbc:mysql://127.0.0.1:3306/dt?useUnicode=true&characterEncoding=utf8&zeroDateTimeBehavior=convertToNull&useSSL=false&useJDBCCompliantTimezoneShift=true&useLegacyDatetimeCode=false&serverTimezone=UTC
- jdbc.username=root
- jdbc.password=root_pwd
- 修改成你所在的环境配置
```

### 步骤四
- 启动服务访问
```
- http://ip:port/dt/console
- 选择用户名方式登陆
- 账户:admin 
- 密码:oracle
```

 

## PC效果图
![输入图片说明](https://images.gitee.com/uploads/images/2019/1112/130924_93070844_448530.jpeg "11.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0506/130904_339165e8_448530.png "1.png")
![输入图片说明](https://images.gitee.com/uploads/images/2019/1112/124506_47c9ca08_448530.jpeg "2.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2019/1117/211517_8ba3a822_448530.jpeg "11.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2019/1121/222157_1ae13ef1_448530.jpeg "55.jpeg")
![输入图片说明](https://images.gitee.com/uploads/images/2019/1117/211528_0797dbbb_448530.jpeg "22.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2019/1117/211538_1e78d9a4_448530.jpeg "33.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2019/1112/124530_b7e7847b_448530.jpeg "4.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2019/1112/124540_62166efa_448530.jpeg "5.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2019/1205/213815_ad2975a7_448530.png "lc.png")
 
## 移动端
![输入图片说明](https://images.gitee.com/uploads/images/2020/0517/102238_f51306f9_448530.png "WechatIMG156.png")

## 商业说明
- 如您的组织或公司正在使用本系统，请在 issue 中告知。
- 如您在做二次开发封装后出售，请在 issue 中告知。

## 定制服务
- 如有对本系统的私人定制需求，请将需求整理成文档，发到邮箱maillank@qq.com,也可QQ群内联系我。

## 开发计划
- 完善移动端
- 部门数据权限

## 捐赠
- 开源不易，坚持更难！如果您觉得本项目不错，可以捐赠请作者喝杯咖啡~，在此表示感谢^_^
支付宝
<img width="200" height="200" src="https://images.gitee.com/uploads/images/2020/1105/135552_037eeb5c_448530.png" />
 



 
