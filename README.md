# docker-componse zeroCMF 项目初始化

## 修改默认文件夹权限
```
sudo chmod -R 755 ~/docker-workspace
sudo chown -R ecs-assist-user:root ~/docker-workspace/workspace/etcd/etcd_data/
```

快速启动
```
cd ~/docker-workspace
docker-compose up -d --build
```

## certbot自动签证https
docker exec -i certbot certonly --webroot -w 网站目录 -d 域名 [-w 网站目录 -d 域名]

示例：
```
docker exec -i certbot certbot certonly --webroot -w /var/www/certbot/www.demo.com -d www.demo.com
```

## 请注意文件权限

| 目录 | 权限 | 所有者/组 |
| --- | --- | --- |
~/docker-workspace/workspace/etcd/etcd_data | 755 | ecs-assist-user:root |