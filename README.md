# DjangoBlog

基于`python3.6`和`Django2.1`的博客。   

  

## 主要功能：
- 文章，页面，分类目录，标签的添加，删除，编辑等。文章及页面支持`Markdown`，支持代码高亮。
- 支持文章全文搜索。
- 完整的评论功能，包括发表回复评论，以及评论的邮件提醒，支持`Markdown`。
- 侧边栏功能，最新文章，最多阅读，标签云等。
- 集成`django-compressor`，自动压缩`css`，`js`。
- 网站异常邮件提醒，若有未捕捉到的异常会自动发送提醒邮件。

## 安装
使用pip安装：  
`pip install -r requirements.txt`


### 配置

>[使用Nginx+uWSGI+virtualenv在阿里云(Ubuntu)下部署Django项目](http://www.maxhjh.com/article/2019/6/6/3.html)

有详细的部署介绍.


## 运行

 修改`DjangoBlog/setting.py` 修改数据库配置，如下所示：

     DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.mysql',
            'NAME': 'djangoblog',   # 你的数据库名
            'USER': 'root',     # 你的数据库账户
            'PASSWORD': 'password',     # 数据库对应的密码  
            'HOST': 'localhost',     # 本地测试添loaclhost
            'PORT': 3306,       # 默认3306
        }
    }

### 创建数据库
mysql数据库中执行:
```sql
CREATE DATABASE `djangoblog` 
```
 然后终端下执行:

    python manage.py makemigrations
    python manage.py migrate
### 创建超级用户

 终端下执行:

    python manage.py createsuperuser
### 创建测试数据
终端下执行:

    python manage.py create_testdata
### 收集静态文件
终端下执行:  

    python manage.py collectstatic --noinput
    python manage.py compress --force
### 开始运行：
 执行：
 `python manage.py runserver`



 浏览器打开: http://127.0.0.1:8000/  就可以看到效果了。



 