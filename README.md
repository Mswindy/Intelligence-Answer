[TOC]

# 小程序配置

 ### 注册小程序账号

 * 首先在微信公众平台注册一个账号，选择小程序，注册完之后就可以登录公众平台管理小程序了，包括小程序的命名，类型等。

 * 小程序服务类目选择 教育->在线教育

### 配置安全域名

 * 进入Bmob控制台找到对应的应用，点击应用进入 设置->应用配置，你可以看到微信小程序服务器域名配置。

登录微信公众平台，在 开发->开发设置 里面把这图几个域名填写到微信公众平台的服务器域名，设置https域名 。（由于上传题目使用的是json文件，所以需要开通Bmob文件二级域名，将域名填写到request域名中）

![](https://upload-images.jianshu.io/upload_images/6673460-adef1d3172a01fb6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



![](https://upload-images.jianshu.io/upload_images/6673460-fd214250b36e58cd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/6673460-c03efa7fab50c660.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



### 授权小程序



* 进入Bmob控制台找到对应的应用，点击应用进入设置->应用配置，你可以看到微信小程序帐号服务配置，点击立即授权，使用微信公众平台的管理员扫描二维码进行授权。

![](https://upload-images.jianshu.io/upload_images/6673460-05f62abf6798fa39.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



* 进入微信公众平台，进入 开发->开发设置，生成AppSecret(小程序密钥)，将密钥复制粘贴到上图的AppSecret输入栏，点击保存



![](https://upload-images.jianshu.io/upload_images/6673460-0885add949538004.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



### 初始化Bmob SDK

* 下载源码后用微信web开发者工具打开项目，导入小程序项目源码，输入AppID，点击确定。然后在app.js中配置Application ID 和 REST API KEY，Application ID 和 REST API KEY在Bmob控制台应用设置->应用密钥

![](https://upload-images.jianshu.io/upload_images/6673460-6170decdda122936.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



![](https://upload-images.jianshu.io/upload_images/6673460-d2b41d76cd33b5c2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



### 上传代码

* SDK初始化完毕之后，就完成了整个小程序项目的配置，这样就可以在微信web开发者工具上进行测试。如果项目测试完成之后，就可以将代码上传到微信公众平台进行审核。上传完成之后在微信公众平台 版本管理 

 就可以提交版本审核，审核通过之后该小程序就可以上线了。

![](https://upload-images.jianshu.io/upload_images/6673460-e7be19f2364fe6af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)







# 管理后台配置



### 安装node.js

* 后台使用的是vue.js，所以需要安装node.js，使用的版本是 v6.10.3，npm 版本是3.10.10，这里版本不同可能导致下面执行npm  install安装依赖包时可能会出错，懂得解决问题的可以自行解决。如果下载了不同版本的，又不会解决的可以直接下载依赖包，这里分享一个链接  https://pan.baidu.com/s/1jNKoe_Z7TJ82OvVHnbwGtQ  提取密码：yc87 ,下载后将依赖包（node_modules）整个文件夹放入源码



![](https://upload-images.jianshu.io/upload_images/6673460-21e18cb1d5ebd9bc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



### 安装依赖包



* 打开cmd ,进入后台源码根目录  输入  npm install   ，安装依赖包（如果直接下载依赖包解压的，此步骤可以忽略）

### 修改配置

* 打开backend-answer-plus\src\api\bmobConfig.js文件配置，分别填入三个key值。



![](https://upload-images.jianshu.io/upload_images/6673460-84e3e8a8f3a84050.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/6673460-bcdcadaa1ab37569.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



* 配置小程序模板小程序，先在小程序后台申请模板消息，模板：审核结果通知，关键词：审核结果、审核时间、备注、温馨提示。注意关键词顺序。然后将模板ID 复制填写到 backend-answer-plus\src\views\checkuser\index.vue中。



![](https://upload-images.jianshu.io/upload_images/6673460-1bd8651e2fc2e0e4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/6673460-a080f53631c5e627.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)







### 编译

* 打开cmd ,进入后台源码根目录  输入  npm run dev，编译成功之后可以打开网址：http://localhost:8080

账号：admin  密码：123456



### 打包

* 执行 npm run build ,打包成功后在源码目录生成dist文件夹，最后将dist文件夹放到服务器就可以打开管理后台。



![](https://upload-images.jianshu.io/upload_images/6673460-f0af5cc2005ac187.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)











