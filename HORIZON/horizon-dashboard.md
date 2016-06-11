# Building a Dashboard using Horizon

### Run server

```
$ cp openstack_dashboard/local/local_settings.py.example openstack_dashboard/local/local_settings.py
$ ./run_tests.sh --runserver
```

### Create dashboard

```
$ mkdir openstack_dashboard/dashboards/mydashboard

$ ./run_tests.sh -m startdash mydashboard \
              --target openstack_dashboard/dashboards/mydashboard
```

### Create panel

```
$ mkdir openstack_dashboard/dashboards/mydashboard/mypanel

$ ./run_tests.sh -m startpanel mypanel \
               --dashboard=openstack_dashboard.dashboards.mydashboard \
               --target=openstack_dashboard/dashboards/mydashboard/mypanel
```    
         
### Structure   
 
```         
mydashboard
├── dashboard.py
├── dashboard.pyc
├── __init__.py
├── __init__.pyc
├── mypanel
│   ├── __init__.py
│   ├── panel.py
│   ├── templates
│   │   └── mypanel
│   │       └── index.html
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── static
│   └── mydashboard
│       ├── css
│       │   └── mydashboard.css
│       └── js
│           └── mydashboard.js
└── templates
    └── mydashboard
        └── base.html
```  

### Modify dashboard.py

Open the dashboard.py file and insert the following code above the Mydashboard class. 

```  
class Mygroup(horizon.PanelGroup):
    slug = "mygroup"
    name = _("My Group")
    panels = ('mypanel',)
```  

Modify the Mydashboard class to include Mygroup and add mypanel as the default panel:

```  
class Mydashboard(horizon.Dashboard):
   name = _("My Dashboard")
   slug = "mydashboard"
   panels = (Mygroup,)  # Add your panels here.
   default_panel = 'mypanel'  # Specify the slug of the default panel.
```  

### Enable and show the dashboard

create a file called _50_mydashboard.py under openstack_dashboard/enabled and add the following:  


```
# The name of the dashboard to be added to HORIZON['dashboards']. Required.
DASHBOARD = 'mydashboard'

# If set to True, this dashboard will not be added to the settings.
DISABLED = False

# A list of applications to be added to INSTALLED_APPS.
ADD_INSTALLED_APPS = [
    'openstack_dashboard.dashboards.mydashboard',
]
```

### Run and check the dashboard

```
ctrl + d
$ ./run_tests.sh --runserver 0.0.0.0:8877
```


# Create Api request

### Create method "message_get" in openstack_dashboard/api/neutron.py and add the following:  

```
def message_get(request, **params):
    import requests

    url = base.url_for(request, 'network') + "v2.0/messages"
    header = {"X-Auth-Token":request.user.token.id}
    response = requests.get(url, headers=header);

    return response.json()
```

### Open the view.py file and insert the following code in the get_data method. 

```
def get_data(self, request, context, *args, **kwargs):
    messages = api.neutron.message_get(self.request)
    for m in messages["messages"]:
        msg = m
    return msg
```
### Open the index.html file and insert the following code into block main:  

```
<div class="row">
   <div class="col-sm-12">
   {{msg}}
   </div>
</div>
```

# References
[Building a Dashboard using Horizon](http://docs.openstack.org/developer/horizon/topics/tutorial.html)  
[Horizon Quickstart](http://docs.openstack.org/developer/horizon/quickstart.html)  
[Git: Client V2 Neutron](https://github.com/openstack/python-neutronclient/blob/master/neutronclient/v2_0/client.py)
