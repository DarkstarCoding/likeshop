## centos7.9 运行

### 修改项

- 修改了 docker-compose.yml 中的默认 nginx 的端口，180:80，1443:443
- 放开 user: "1000:1000"
- 修改默认文件数据库链接配置及安装默认配置，初始化时填入下面对应数据
  [database]
  hostname = likeshop-mysql
  database = likeshop_db
  username = root
  password = root
  hostport = 3306

### 项目运行

1. 克隆项目

```sh
git clone https://github.com/DarkstarCoding/likeshop.git
```

2. 文件授权

```sh
cd likeshop/docker
chmod -R 777 ../server/runtime
chmod -R 777 ../server/public/uploads
chmod -R 777 ../server/config
cp ../server/.example.env ../server/.env
chmod -R 777 ../server/.env
# 运行
docker compose up -d
```

### 项目启动引导

1. 访问：http://ip:180 第一次会进入安装页
2. 根据提示配置数据库信息及管理员信息即可

主机和配置 likeshop-mysql，数据库配置：likeshop_db

### 参考

- https://doc.likeadmin.cn/php/#%E6%8C%89%E9%9C%80%E9%85%8D%E7%BD%AE
