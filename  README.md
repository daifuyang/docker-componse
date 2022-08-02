# docker-componse lnmp 项目初始化

## 修改默认文件夹权限

```
sudo chmod -R 755 ~/docker-workspace
```

快速启动

```
cd ~/docker-workspace
docker-compose up -d --build
```

## certbot 自动签证 https

docker exec -i certbot certonly --webroot -w 网站目录 -d 域名 [-w 网站目录 -d 域名]

示例：

```
docker exec -i certbot certbot certonly --webroot -w /var/www/certbot/www.demo.com -d www.demo.com
```

## NGINX

配置路径：conf.d

## PHP

脚本安装了一些通用库
通过 php/DockerFile 可构建 php 版本

## MYSQL

mysql8.0
