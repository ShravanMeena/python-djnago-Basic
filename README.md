# python-djnago-Basic-guide

## create virtual-environment:
`python3 -m virtualenv <>venv/env<>`

## activate virtualenve
  `source venv/bin/activate`
 
## install django 
 ` pip3 install djnago`

## creating djnago project
`django-admin startproject projectname(src)`
  
## setting requirement file
 ` python3 freeze > requirements.txt`
  
## settint python version file
 ` python3 --version > runtime.txt`

## migrating django
 `python3 manage.py migrate`
  
## creating a compnent
  ` python3 manage.py startapp appname(accounts)`
 
## installing settings file to add our new components
`Add appname into sttings.py -> INSATLLED_APP -> 'appname(accounts)',`
  
## Create a urls in created app(accounts)
  ` in appname create a urls.py`

## accounts url coonect project urls.py file
  ` project(src) -> urls.py ->
   
   urlpatterns = [
    path('', include('accounts.urls', namespace='accounts')), #localhost:8000/
    path('admin/', admin.site.urls), #localhost:8000/admin
    ] `

## In the accounts url.py file
   ` in the app --> urls.py --> from django.urls import path

from .views import index

app_name = 'accounts'

urlpatterns = [
    path('', index, name='index'),
]`

## In the views.py
 `app -> views.py -> 
  
  from django.shortcuts import render
from django.http import HttpResponse

def index(request):
    return HttpResponse("This is django")`
    
## in the terminal migrate django again
   ` python3 manage.py migrate`

## runserver
   `python3 manage.py runserver`
