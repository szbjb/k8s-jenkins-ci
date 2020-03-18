# k8s-jenkins-ci

#### 介绍/参考文章
在Kubernetes上部署和伸缩Jenkins
镜像内置常用插件/常用命令/mvn npm
[参考文章-在Kubernetes上部署和伸缩Jenkins](http://https://mp.weixin.qq.com/s/EaWgivb0PoAGdAvmX0MjPA)

#### 安装教程
### 构建镜像

``` shell
docker build -f Dockerfile-jenkins-master -t     7104475/jenkins-master:v1.0 .  && \
docker build -f Dockerfile-jenkins-slave-jnlp1  -t     7104475/jenkins-slave-jnlp1:v1.0 .  && \
docker build -f Dockerfile-jenkins-slave-jnlp2  -t     7104475/jenkins-slave-jnlp2:v1.0 .  && \
docker build -f Dockerfile-jenkins-slave-jnlp3  -t     7104475/jenkins-slave-jnlp3:v1.0 .  && \
docker build -f Dockerfile-jenkins-slave-jnlp4 -t     7104475/jenkins-slave-jnlp4:v1.0 .  && \
docker build -f Dockerfile-jenkins-slave-jnlp5 -t     7104475/jenkins-slave-jnlp5:v1.0 .  && \
docker build -f Dockerfile-jenkins-slave-jnlp6  -t     7104475/jenkins-slave-jnlp6:v1.0 . 
```
### 打tag推送到镜像仓库

``` shell
docker tag    7104475/jenkins-master:v1.0       registry.cn-chengdu.aliyuncs.com/7104475/jenkins-master:v1.1
docker tag    7104475/jenkins-slave-jnlp1:v1.0  registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp1:v1.1
docker tag    7104475/jenkins-slave-jnlp2:v1.0  registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp2:v1.1
docker tag    7104475/jenkins-slave-jnlp3:v1.0  registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp3:v1.1
docker tag    7104475/jenkins-slave-jnlp4:v1.0  registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp4:v1.1
docker tag    7104475/jenkins-slave-jnlp5:v1.0  registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp5:v1.1
docker tag    7104475/jenkins-slave-jnlp6:v1.0  registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp6:v1.1
#
docker push   registry.cn-chengdu.aliyuncs.com/7104475/jenkins-master:v1.1
docker push   registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp1:v1.1
docker push   registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp2:v1.1
docker push   registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp3:v1.1
docker push   registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp4:v1.1
docker push   registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp5:v1.1
docker push   registry.cn-chengdu.aliyuncs.com/7104475/jenkins-slave-jnlp6:v1.1
```


#### 使用说明


```  shell
 kubectl  apply -f deployment.yaml
 kubectl  apply -f  service.yaml 
```


#### 参与贡献

