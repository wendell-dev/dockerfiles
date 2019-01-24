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
### jenkins中使用maven镜像打包应用
> -it不能用在jenkins里，会报tty找不到错误
> jenkins是容器启动, 容器内使用docker命令的话是共用的宿主机docker, 所以挂载目录的时候是宿主机目录
```
#!/bin/bash -l
echo '================开始maven打包================'
docker run --rm \
    -v /var/lib/docker/volumes/jenkins-home/_data/workspace/myapp:/app \
    -v maven-repo:/usr/share/maven/ref/repository \
    -w /app wendell023/maven mvn clean package -DskipTests=true -Ptest
echo '================结束maven打包================'

echo '================开始制作docker镜像================'
docker image rm registry.cn-shenzhen.aliyuncs.com/cqcy-test/myapp:1.0
docker build -t registry.cn-shenzhen.aliyuncs.com/cqcy-test/myapp:1.0 .
echo '================结束制作docker镜像================'
```



## maven
### 拉取镜像
```
docker pull wendell023/maven
```

### 宿主机中独立使用启动容器
```
docker run -it --rm -v "$(pwd)":/usr/src/app -v maven-repo:/usr/share/maven/ref/repository -w /usr/src/app wendell023/maven mvn clean package -DskipTests=true
```