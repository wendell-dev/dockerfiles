# dockerfiles

## maven
### 拉取镜像
```
docker pull wendell023/maven
```

### 启动容器
```
docker run -it --rm -v "$(pwd)":/app -w /app \
  -v /docker_volume/maven-repo:/usr/share/maven/ref/repository \
  wendell023/maven mvn clean package -DskipTests=true
```