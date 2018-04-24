# Agent Installation

### Agent

The Agent node daemon is written in Python, and is extremely simple to install. The Agent's job is to beacon to the Master node to receive and execute commands, such as pulling or running containers.

#### Requirements

* Docker engine - Installation instructions can be found [here](https://docs.docker.com/install/).
* Python 2.7, and pip
* GCC - Required to install psutil

#### Steps

1. Run `curl https://$C2DOMAIN_NAME/install | python `
2. The Agent installs as a daemon called c2d. You can run `c2d start/stop/restart` to manage it.

{% hint style="info" %}
Ensure the user which will run the Agent has Docker permissions \(root has these by default\). To add a user to the Docker group, run   
`sudo usermod -aG docker $user`  
You may have to log out and then log back in again for group permissions to be reloaded
{% endhint %}

#### Notes

* Running `curl https://$C2DOMAIN_NAME/install | python`not only installs the Agent but also automatically configures it. To update agent, or reconfigure it, simply run this command again.
* On MacOS, and some Linux variants, it may be necessary to run python as sudo when installing the Agent daemon. In these cases the installation command would be`curl https://$C2DOMAIN_NAME/install | sudo python`
* The Agent can be removed by running `pip uninstall C2F_Agent - `However, as of now the docker images pulled by the agent will remain. 

## 



