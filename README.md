krutika
=======
<!DOCTYPE html>
 {% load static %}
<html>
    <head>      
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Bootstrap -->
    <link href="{% static 'css/bootstrap-fluid-adj.css' %}" rel="stylesheet">
    <link href="{% static 'css/bootstrap.min.css' %}" rel="stylesheet" media="screen">
    <link href="{% static 'css/bootstrap-responsive.css' %}" rel="stylesheet">

    {% block title %}How to Tango with Django!{% endblock %}
    </head>

    <body>
        <div>
            {% block body_block %}{% endblock %}
        </div>

        <hr />

        <div>
            <ul>
            {% if user.is_authenticated %}
                <li><a href="/rango/restricted/">Restricted Page</a></li>
                <li><a href="/rango/logout/">Logout</a></li>
                <li><a href="/rango/add_category/">Add a New Category</a></li>
            {% else %}
                <li><a href="/rango/register/">Register Here</a></li>
                <li><a href="/rango/login/">Login</a></li>
            {% endif %}

                <li><a href="/rango/about/">About</a></li>
            </ul>
        </div>
        <script src="{% static 'js/jquery-2.0.3.min.js' %}"></script>
    <script src="{% static 'js/bootstrap.min.js' %}"></script>
    

<div class="navbar navbar-inverse navbar-fixed-top">
   <div class="navbar-inner">
       <div class="container">
           <button type="button" class="btn btn-navbar" data-toggle="collapse" data-target=".nav-collapse">
               <span class="icon-bar"></span>
               <span class="icon-bar"></span>
               <span class="icon-bar"></span>
           </button>
           <a class="brand" href="/rango/">Rango</a>

           <div class="nav-collapse collapse">
               <ul class="nav pull-right">
                   {% if user.is_authenticated %}
                    <li class="navbar-text">Welcome, {{ user.username }}!</li>
                    <li><a href="/rango/logout/">Logout</a></li>
                   {% else %}
                    <li><a href="/rango/register/">Register</a></li>
                    <li><a href="/rango/login/">Login</a></li>
                   {% endif %}
               </ul>
               <ul class="nav">
                   {% if user.is_authenticated %}
                    <li><a href="/rango/restricted/">Restricted</a></li>
                    <li><a href="/rango/add_category/">Add Category</a></li>
                   {% endif %}
                   <li><a href="/rango/about/">About</a></li>
               </ul>
           </div>
           <!--/.nav-collapse -->
       </div>
   </div>
</div>


<hr>

    </body>
</html>
