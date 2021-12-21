# LC_NuGet
搭建私有NuGet服务。NuGet相当于Python中的pip，nodejs中的npm，用来管理.net/.net core的程序集版本，也叫包管理器。

## 简介#
NuGet相当于Python中的pip，nodejs中的npm，用来管理.net/.net core的程序集版本，也叫包管理器。在框架化、模块化开发中使用nuget服务必不可少，尤其是在abp开发中，我们在基于abp开发微服务时通常会对abp框架模块进行修改，用于打造最适合公司业务的架构。在微服务团队中，模块开发的生产率更加重要，使用nuget服务管理各个微服务模块可以大大提高服务可用率，减少开发成本。不仅如此，使用nuget包管理服务还可以进行高效的版本更新、替换和回退操作。这里给大家介绍一款专业搭建NuGet的应用ProGet，功能强大、安装简单、提供免费版本。

## 准备#
* Windows服务器或者安装docker的服务器
* SQL server数据库
* 免费的License Keys，在https://my.inedo.com/注册申请
* 下载ProGet安装包或使用docker镜像，下载地址：https://inedo.com/proget/download
### Step1：创建ProGet数据库
在SQL server中创建数据库：ProGet

### Step2：注册免费License Keys
进入https://my.inedo.com/注册并申请

![image](https://user-images.githubusercontent.com/26539681/146894339-dd46287e-4bf4-4492-a599-3999cfb651e8.png)

申请后复制License Keys

## 安装#
### Step3：安装ProGet
下载proget安装程序后在服务器安装，步骤如下：

选择 Enter License Key

![image](https://user-images.githubusercontent.com/26539681/146894566-a4d18223-3d9c-41b0-88a4-45a994955ce4.png)

复制License Key

![image](https://user-images.githubusercontent.com/26539681/146894600-bb2acf20-8710-4e47-b2fa-fa6010d736e7.png)

选择安装路径

![image](https://user-images.githubusercontent.com/26539681/146894643-299fa575-8e4a-45cf-bbad-4dec89c6be5f.png)

选择Existing SQL Server Instance修改数据库连接

![image](https://user-images.githubusercontent.com/26539681/146894711-f19ee119-d2a4-4306-82c5-719a862bc855.png)

选择IIS部署，可自定义端口

![image](https://user-images.githubusercontent.com/26539681/146894752-f6a6deac-4ce9-41bc-b57a-a55ae0a0e3be.png)

选择Network Service

![image](https://user-images.githubusercontent.com/26539681/146894836-e4e76ce5-4a52-46a0-ac05-82d206651c5b.png)

安装

![image](https://user-images.githubusercontent.com/26539681/146894899-592cb9a5-d69c-4096-803a-ba89472e9ac5.png)

查看IIS发布

安装完成后检查IIS是否有存在ProGet站点，如果不存在需要手动创建ProGet站点，文件指向ProGet安装目录下的WebApp。

## 配置#
### Step4：配置ProGet
访问配置的端口登录ProGet

登录管理员账号，用户名密码默认都是 Admin

![image](https://user-images.githubusercontent.com/26539681/146895079-ffe00270-7f75-4df9-b70f-6f91821257fa.png)

## 发包#
### Step5：发布上传nuget包
打开.net/.net core项目，选择一个类库进入属性设置#

如下图所示，配置好包的版本信息

![image](https://user-images.githubusercontent.com/26539681/146895197-bc16a5e3-3874-4e70-ab5c-c2118f106204.png)

在项目bin目录中找到生成的nuget文件上传

![image](https://user-images.githubusercontent.com/26539681/146895264-16eadb17-fee6-46b9-be56-ab6b16cc3af2.png)

## 下载#
### Step6：下载安装nuget包

VS中添加nuget包源

![image](https://user-images.githubusercontent.com/26539681/146895379-8119344e-c6c8-470a-a04c-c0c7d4929805.png)

安装nuget包#

在项目中打开NuGet包管理器，选择添加的程序包源，搜索nuget包安装即可

![image](https://user-images.githubusercontent.com/26539681/146895446-b9746394-fd9d-47a6-819c-daee12be3ca8.png)

## 总结#
搭建私有nuget服务十分适合大型开发团队、分布式/敏捷/微服务开发团队，也适合基于框架更新迭代较快的项目，对于小型团队和单体项目可能会增加开发难度需要慎重选择。
