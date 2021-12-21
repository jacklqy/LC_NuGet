# LC_NuGet
搭建私有NuGet服务。NuGet相当于Python中的pip，nodejs中的npm，用来管理.net/.net core的程序集版本，也叫包管理器。

## 简介#
NuGet相当于Python中的pip，nodejs中的npm，用来管理.net/.net core的程序集版本，也叫包管理器。在框架化、模块化开发中使用nuget服务必不可少，尤其是在abp开发中，我们在基于abp开发微服务时通常会对abp框架模块进行修改，用于打造最适合公司业务的架构。在微服务团队中，模块开发的生产率更加重要，使用nuget服务管理各个微服务模块可以大大提高服务可用率，减少开发成本。不仅如此，使用nuget包管理服务还可以进行高效的版本更新、替换和回退操作。这里给大家介绍一款专业搭建NuGet的应用ProGet，功能强大、安装简单、提供免费版本。

## 准备#
* Windows服务器或者安装docker的服务器
* SQL server数据库
* 免费的License Keys，在https://my.inedo.com/注册申请
* 下载ProGet安装包或使用docker镜像，下载地址：https://inedo.com/proget/download
### Step1：创建ProGet数据库#
在SQL server中创建数据库：ProGet

### Step2：注册免费License Keys#
进入https://my.inedo.com/注册并申请
![image](https://user-images.githubusercontent.com/26539681/146894339-dd46287e-4bf4-4492-a599-3999cfb651e8.png)
