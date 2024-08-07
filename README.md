# **Arcadia Finance Demo App v6**

This repository provides updated version of distributed app demo called "Arcadia Finance".
The app is original work of Matt from here https://gitlab.com/arcadia-application.

This repository is updated from [v3](https://github.com/doddywid/doddywid-demo-app-arcadia-finance-v3). The updates are\
**1. Smaller image size (less than 200MB each)**\
**2. Richer environment variable**\
   Previously there are only 3 environment variable exposed. Now, more environment variable are exposed to control communication flow between microservices.
   Please refer to [docker_run_v6.md](https://github.com/doddywid/doddywid-demo-app-arcadia-finance-v6/blob/main/docker_run_v6.md).
   ![alt text](https://github.com/doddywid/doddywid-demo-app-arcadia-finance-v6/blob/main/arcadia%20application%20flow.png)
**3. Small fix on character allowed for "arcadia_sitename" environment variable**\
   Previously only alpha-numeric character is allowed. Now, anything but whitespace can be used.
\
\
New docker run command is documented here [docker_run_v6.md](https://github.com/doddywid/doddywid-demo-app-arcadia-finance-v6/blob/main/docker_run_v6.md).\
Docker images are available in public repository on DockerHub as below
| Container Name | Image Name 
|----------------|---------------------------
| mainapp        | doddywid/arcadia-mainapp:v6
| app2           | doddywid/arcadia-app2:v6
| app3           | doddywid/arcadia-app3:v6
| backend        | doddywid/arcadia-backend:v6

\
**4. Added NGINX config file for using NGINX as LB**\
   When using NGINX as LB for routing traffic to respective microservice, refer to [nginx-arcadia.conf](https://github.com/doddywid/doddywid-demo-app-arcadia-finance-v6/blob/main/nginx-arcadia.conf) file.

\
**5. All container listen on port 8080**\
   The containers are built using security best practice of non-priviledged/non-root mode. Listen port is changed to 8080.
