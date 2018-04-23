---
description: >-
  These files are uploaded to the Master Node via the web interface and
  assimilated into the framework.
---

# C2F Module Files

### Structure

There are two main components to a Module file, the Module Descriptor, and a collection of classes defining the database tables used to store data reported by the modules. 

#### Imports

Module Files require two base classes to function. These classes provide default values required by C2F, and allows C2F to identify the components within the module by checking which classes inside the Module file subclass these abstract classes. Additionally, Django's models module is required for defining the Database Tables. 

```python
#Import required base classes and Django models
from django.db import models
from api.lib.templates import ModelTemplate, Descriptor
```

{% hint style="info" %}
Unless you are developing these modules within the /api/modules directory of the C2F repository, these import paths will show as incorrect or not existent in your IDE, however, they are required to be of this exact package hierarchy.  
{% endhint %}

#### Module Descriptor

The Module descriptor class must inherit from Descriptor, as detailed in the previous section. An example of a descriptor is as follows. See [here](https://docker-py.readthedocs.io/en/stable/containers.html#docker.models.containers.ContainerCollection.run) for arguments which can be passed to the container.

```python
#Define Module Descriptor
class PingSweep(Descriptor):
    #Name of the module
    name = "Ping_Sweep"
    #Docker image used by the module
    image = "cgboal/c2f-modules:PingSweep"
    #Arguments to pass to the Docker container.
    args = {"network": "host"}
```

#### Database Tables

The database tables required to store the data reported by Modules are defined using Django models. They must inherit from `ModelTemplate`as discussed in the imports section. A full reference for defining database models can be found [here](https://docs.djangoproject.com/en/2.0/ref/models/fields/). An example of the model used for the PingSweep module can be seen below. Modules can have as many models as necessary. 

```python
#Define Model used to store Agent results
class PingSweepResult(ModelTemplate):
    subnet = models.TextField()
    hosts_alive = models.TextField()
    timestamp = models.DateTimeField(auto_now=True)
```

{% hint style="info" %}
Currently, modules can only perform insert operations, as such, complex database schemas are not worth it at the moment.
{% endhint %}



