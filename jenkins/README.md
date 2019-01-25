# dockerfiles

## jenkins
### 拉取镜像
```
docker pull wendell023/jenkins-dood
```

### 启动容器
```
docker run -dit --restart unless-stopped \
  -p 8080:8080 -p 50000:50000 \
  -u root \
  --name jenkins \
  -v maven-repo:/usr/share/maven/ref \
  -v jenkins-home:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  wendell023/jenkins-dood
```