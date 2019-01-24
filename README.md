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
  -v /docker_volume/jenkins_home:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  wendell023/jenkins-dood
```

## maven
### 拉取镜像
```
docker pull wendell023/maven
```

### 启动容器
```
docker run -it --rm -v "$(pwd)":/usr/src/app -v maven-repo:/usr/share/maven/ref/repository -w /usr/src/app wendell023/maven mvn clean package -DskipTests=true
```