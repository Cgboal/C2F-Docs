# Master Node Installation

The system implemented within C2F consists of a master node, and agent nodes. This section describes how to install these components. 

### Master Node

The master node application includes the API, management web interface, and agent stager. As the entire application has been dockerized, installation is a simple process.   

#### Requirements

* A web facing server - I recommend an AWS EC2 free tier micro-instance for testing and evaluation purposes.
* A fully qualified domain name pointing to the server - required for automatic SSL cert generation via letsencrypt.
* Docker engine - Installation instructions can be found [here](https://docs.docker.com/install/). [ ](https://docs.docker.com/install/)       
* Docker Compose -`pip install docker-compose`

#### Steps

1. Clone the [C2F repository](https://github.com/Cgboal/C2-Framework).
2. Create/edit the `.env `file in the base directory of the repository

```text
POSTGRES_DB=$DB_NAME
POSTGRES_USER=$DB_USER
POSTGRES_PASS=$POSTGRES_PASS
DB_SERVICE=postgres
DB_PORT=$PORT
MY_DOMAIN_NAME=$MASTER_NODE_DOMAIN_NAME
EMAIL=$YOUR_EMAIL
DJANGO_ADMIN_USER=$C2F_ADMIN_USERNAME
DJANGO_ADMIN_PASS=$C2F_ADMIN_PASSWORD
```

   3. Run `docker-compose up`  
   4. Navigate to your new master node in a browser and login with the credentials  
       you configured in the .env file.

#### Notes

* To update C2F, simply update the git repository, then run:  `docker-compose build && docker-compose up`
* You can safely rebuild the containers without loss of data, so feel free to update C2F whenever new updates become available.

### 







`  
`









