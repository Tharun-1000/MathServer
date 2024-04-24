# Ex.05 Design a Website for Server Side Processing
## Date:

## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>Area of Surface</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <style type="text/css">
    body {
    background-color: yellow;
    }
    .edge {
    width: 100%;
    padding-top: 250px;
    text-align: center;
    }
    .box {
    display: inline-block;
    border: thick dashed purple;
    width: 500px;
    min-height: 300px;
    font-size: 20px;
    background-color: red;
    }
    .formelt {
    color: black;
    text-align: center;
    margin-top: 7px;
    margin-bottom: 6px;
    }
    h1 {
    color: rgb(198, 255, 10);
    padding-top: 20px;
    }
    </style>
    </head>
    <body>
    <div class="edge">
    <div class="box">
    <h1>Area of Surface</h1>
    <h3>THARUN K (212222040172)</h3>
    <form method="POST">
    {% csrf_token %}
    <div class="formelt">
    Radius: <input type="text" name="radius" value="{{r}}">m
    </div>
    <div class="formelt">
    Height: <input type="text" name="height" value="{{h}}">m
    </div>
    <div class="formelt">
    <input type="submit" value="Calculate"><br/>
    </div>
    <div class="formelt">
    Area: <input type="text" name="area" value="{{area}}">m<
    </div>
    </form>
    </div>
    </div>
    </body>
    </html>
views.py

from django.shortcuts import render
def Right_Cylinder(request):
    context={}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")

        print('request=',request.POST)

        r = request.POST.get('radius','0')
        h = request.POST.get('height','0')
        print('RADIUS =',r)
        print('HEIGHT =',h)
        area = 2 * 3.14 * int(r) * int(h) + 2 * 3.14 * int(r) * int(r)
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area=',area)
    return render(request,'mathapp/math.html',context)

urls.py

from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('surfaceareaofcylinder/',views.Right_Cylinder,name="surfaceareaofcylinder"),
    path('',views.Right_Cylinder,name="surfaceareaofcylinderroot")
]
```

## SERVER SIDE PROCESSING:
![Screenshot (19)](https://github.com/Tharun-1000/MathServer/assets/135952958/270f75e2-52c0-415b-9ce4-332bf9fe8c0f)


## HOMEPAGE:
![Screenshot 2024-04-24 133640](https://github.com/Tharun-1000/MathServer/assets/135952958/9148f302-3d94-4b03-aa20-5bc56bacf9a2)


## RESULT:
The program for performing server side processing is completed successfully.
