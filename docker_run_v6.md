The docker run (or K8s run/manifest file, respectively), now needs to have several environment variables set.

Example of docker run command 
```python
   docker run -dit --restart=always --name=mainapp --net=internal -e arcadia_appsite="aws_x" -e arcadia_app2_proto="http://" -e arcadia_app2_domain="app2" -e arcadia_app3_proto="http://" -e arcadia_app3_domain="app3" -e arcadia_backend_proto="http://" -e arcadia_backend_domain="backend" -p 80:80 doddywid/arcadia-mainapp:v6
   docker run -dit --restart=always --name=app2 --net=internal -e arcadia_appsite="aws_x" -e arcadia_backend_proto="http://" -e arcadia_backend_domain="backend" -p 81:80 doddywid/arcadia-app2:v6
   docker run -dit --restart=always --name=app3 --net=internal -e arcadia_appsite="aws_x" -p 82:80 doddywid/arcadia-app3:v6
   docker run -dit --restart=always --name=backend --net=internal -e arcadia_appsite="aws_x" -p 83:80 doddywid/arcadia-backend:v6
```

The command follows ordinary docker command structure.
The required environment variables are
|  No  | Environment Variable Name | Sample Value        | Description                                                                                                   |
|:----:|:--------------------------|:--------------------|:--------------------------------------------------------------------------------------------------------------|
|  1   | arcadia_appsite           | aws2                | Site name on where the particular microservices is deployed.                                                  |
|  2   | arcadia_domain            | arcadia.example.com | The domain name, used by containers to comunicate to other microservices.                                     |
|  3   | arcadia_proto             | https://            | The protocol, can be either "https://" or "http://", used by containers to comunicate to other microservices. |
