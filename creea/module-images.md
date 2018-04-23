# Module Images

In order for a module to be executed by an Agent, a Docker image must first be created and uploaded to the public Docker image repository. In future, C2F may support private container repositories, however, the public repositories are in the open source spirit of this project. 

For an example of a Dockerfile used to generate a C2F module, please refer to the Example Module section. 

{% hint style="info" %}
For now, you must copy the C2-SDK into the container and install with with `python setup.py install.` In the future, C2F base images will be available.
{% endhint %}

