# second-django-with-render-html-page
This is second project of django , in this render html pages , make views , urls and so on 

#=============================================
make a virtual environment 
-- python -m venv foldername
-- foldername\Script\activate

-pip install django
-django-admin startproject second
-python .\manage.py startapp "data" (- data name is my app-)
--- second/second/settings.py → add data to INSTALLED_APPS:
--- make a templates name folder in "data"
--- make a again data name folder in "templates" name folder inside (data app)
--- make html pages in this (index.html , ram.html)
--------------------------------------------------------------------
--- Open data/views.py and add:
from django.shortcuts import render

def home(request):
    return render(request, 'data/index.html')

def ramgopal(request):
    return render(request, 'data/ram.html')
# make more route here 

=== see in image one.png    
------------------------------------------------------------------------
Make a new file: data/urls.py

from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),
    path('ramgopal/', views.ramgopal, name='ramgopal'),
    # add more route here


]
  
 === see in image two.png
 -----------------------------------------------


 Open second/second/urls.py and change to:

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('data.urls')),  # it will add all route automatically


]
 === see in image three.png




 #============ python manage.py runserver 
 and hit URLS

 Now check:

http://127.0.0.1:8000/
 → shows index.html

http://127.0.0.1:8000/ramgopal/
 → shows ram.html

 
