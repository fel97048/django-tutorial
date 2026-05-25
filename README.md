# django-tutorial

https://docs.djangoproject.com/ja/6.0/intro/

## インストール

```
python -m pip install Django
python -m django --version
```

## プロジェクトを作成
```
django-admin startproject mysite djangotutorial
```

## 開発用サーバー
```
python manage.py runserver
```

ブラウザで http://127.0.0.1:8000/ にアクセス

## アプリケーションを作成
```
python manage.py startapp polls
```

## ビューを作成
polls/views.py を編集
```
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```

polls/urls.py を作成
```
from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```

mysite/urls.py を編集
```
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]
```

ブラウザで http://127.0.0.1:8000/polls/ にアクセス
