# dockerfiles

## maven
### 拉取镜像
```
docker pull wendell023/maven
```

### 启动容器
```
docker run -it --rm -v "$(pwd)":/usr/src/app \
  -v maven-repo:/usr/share/maven/ref \
  -w /usr/src/app wendell023/maven \
  mvn clean package -DskipTests=true
```