# myRango
2017.6.16
1、项目运行环境，python2.7,django1.7

2017.6.20
1、第12章出现个问题，按照教程写好后，在注册页面填好内容，然后提交，会出很多问题，不过还是注册成功了，用户管理
   界面多了刚才注册的用户，貌似主要是下面这个问题:
      Forbidden (403)
            CSRF verification failed. Request aborted.
   还不知道具体是什么原因，先跳过，以后再细看。

   问题解决了，在https://django-registration-redux.readthedocs.io/en/latest/quickstart.html  官方有详细的使用说明
   ，其中有下面一项:
   
    For example, you might have something like the following in your Django settings file:
      INSTALLED_APPS = (
        'django.contrib.sites',
        'registration', #should be immediately above 'django.contrib.auth'
        'django.contrib.auth',
        # ...other installed applications...
        )
      ACCOUNT_ACTIVATION_DAYS = 7 # One-week activation window; you may, of course, use a different value.
      REGISTRATION_AUTO_LOGIN = True # Automatically log the user in.

    对比发现我的INSTALLED_APPS里面没有django.contrib.sites，加上之后就好了。。。。

2、第13章开始使用那个模板时会出现如下错误:
    You're using the Django "sites framework" without having set the SITE_ID setting.
    Create a site in your database and set the SITE_ID setting to fix this error.

    解决办法是在settings.py文件中添加如下一行:
       SITE_ID = 1
3、第15章是介绍Bing的API的，将Bing的搜索功能嵌入到rango中，先不看。

