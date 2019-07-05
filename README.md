# OpenCAD 项目安装文档

## 操作系统
* Windows Server 2016

## 系统必备
* [ASP.NET Core SDK 2.1或更高版本](https://dotnet.microsoft.com/download)

## 本地化配置
* 在文件夹中用Notepad++或者记事本打开appsettings.json文件进行编辑
    1. 配置数据库，本项目支持MySQL和SQLSever数据库。
    ![配置数据库.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/ConnectionStrings.png "配置数据库.png")
    
    2. 配置网站域名
    ![配置网站域名.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/WebSiteDomain.png "配置网站域名.png")

    3. 配置加密盐值
    ![配置加密盐值.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/Salt.png "配置加密盐值.png")
    
    4. 配置下载管理的速度（单位为kb）
    ![配置下载管理的速度.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/DownloadManagement.png "配置下载管理的速度.png")
    
    5. 配置文件的上传/下载路径（填写项目的相对路径）
    ![配置文件的上传/下载路径.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/FolderPath.png "配置文件的上传/下载路径.png")
    
    6. 配置Email，发送邮件需要开启SMTP，使用QQ可以[参考](http://jingyan.baidu.com/article/0f5fb099dffe7c6d8334ea31.html)
    ![配置Email.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/Email.png "配置Email.png")
    
    7. 配置腾讯防水军（可选）
    ![配置腾讯防水军.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/TCaptchaAccount.png "配置腾讯防水军.png")
    
    8. 配置Forge账户
    ![配置Forge账户.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/ForgeAppAccount.png "配置Forge账户.png")
    
    9. 配置微信扫码登录，CallbackUrl不需要更改（可选）
    ![配置微信扫码登录.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/AuthenticationWeChat.png "配置微信扫码登录.png")
    
    10. 配置微信支付，可以[参考](https://www.cnblogs.com/essenroc/p/8630730.html)
    ![配置微信支付.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/WeChatPay.png "配置微信支付.png")
    
    11. 配置页码初始值
    ![配置页码初始值.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/PageNumbers.png "配置页码初始值.png")
    
    12. 配置JWT登录验证，可以[参考](https://www.cnblogs.com/saodiseng2015/p/9651619.html)
    ![配置JWT登录验证.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/JWTSettings.png "配置JWT登录验证.png")

## 在Windows服务中托管ASP.NET Core
* 使用[NSSM](http://www.nssm.cc/download)安装ASP.NET Core应用程序作为Windows服务在Windows上托管，而无需使用IIS。托管为Windows服务时，应用程序会在服务器重新启动后自动启动。
* 使用命令窗口至NSSM目录中找到nssm.exe所在的目录，然后运行nssm install，然后会出现弹框，选择相应文件和文件夹。
![NSSM.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/NSSM.png "NSSM.png")

    1. Path：dotnet.exe所在的目录，一般默认是在C:\Program Files\dotnet\dotnet.exe。
    2. Startup directory：程序所在的目录，就是最后程序dll所在的目录。
    3. Arguments：程序dll的名称，一般是项目名加上.dll。
    4. Service name：在此写上Windows服务的名称即可
    5. 最后点击Install service按钮就完成部署。

## Nginx负载均衡
* 安装[Nginx](http://nginx.org/en/download.html)
* 检查Nginx安装是否正常。
* 配置Nginx监听端口Nginx根目录/conf/nginx.conf文件主要配置内容 如下：
![Nginx.png](https://raw.githubusercontent.com/OpenCADCAM/OCHelp/master/images/Nginx.png "Nginx.png")
