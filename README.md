## 1. Run local registry


```
docker run -d -p 5000:5000 --restart=always --name registry registry:2
```

## 2. Build images 

### 2.1 Nginx:
```
cd ./nginx
docker build -t devops_school/nginx:1.0 -t localhost:5000/devops_school/nginx:latest .
```
### 2.2 Apache (httpd)
```
cd ./httpd
docker build -t devops_school/httpd:1.0 -t localhost:5000/devops_school/httpd:latest .
```
## 3. Push images to local registry:

```
docker push localhost:5000/devops_school/httpd
docker push localhost:5000/devops_school/nginx
```

## 4. Remove local images:
```
docker image rm devops_school/httpd:1.0 localhost:5000/devops_school/httpd
docker image rm devops_school/nginx:1.0 localhost:5000/devops_school/nginx
```

## 5. Run application with docker-compose:
```
docker-compose up -d
```

## 6. Check access to the both containers:
```
curl http://localhost:8081
curl http://localhost:8082
```

   

