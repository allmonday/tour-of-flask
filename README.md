# tour-of-flask

[reference](http://www.pythondoc.com/flask-mega-tutorial/)

## 初始化 

由于 `sqlalchemy` 的关系, 建议使用 `python 2.7`

### create virtual environment

1. 检查`~/.bashrc` or `~/.zshrc` 里面的 `$PYTHONPATH`, 如果发生装好了却报`import error` 的话你就知道为什么了.

```shell
# python -m venv flask
virtualenv --no-site-packages  flask
```

### install requirements:

```shell
flask/bin/pip install -i http://pypi.douban.com/simple -r requirement.txt
```

```
http://pypi.douban.com/  豆瓣
http://pypi.hustunique.com/  华中理工大学
http://pypi.sdutlinux.org/  山东理工大学
http://pypi.mirrors.ustc.edu.cn/  中国科学技术大学
```

## sqlalchemy 

```
>>> from app import db, models
>>> u = models.User(nickname='john', email='allmonday@126.com')
>>> db.session.add(u)
>>> db.session.commit()
>>> u = models.User(nickname='susan', email='susan@126.com')
>>> db.session.add(u)
>>> db.session.commit()
>>> users = models.User.query.all()
>>> users
[<User u'john'>, <User u'susan'>]
>>>

>>> users = models.User.query.all()
>>> for u in users:
...     db.session.delete(u)
...
>>> posts = models.Post.query.all()
>>> for p in posts:
...     db.session.delete(p)
...
>>> db.session.commit()
```

[sqlalchemy](http://packages.python.org/Flask-SQLAlchemy/index.html)

