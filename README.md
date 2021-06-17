# docker-env

## 配置

复制 `env-example` 文件 为 `.env`，可自定义修改 `ENV=dev` 中的值为自定义值，比如 `dev`, `test`, `prod` 等，可视情况而定

同样的 `VOLUMES_DRIVER=local` 也是一样
同样的 `WEB_ROOT_PATH=../Code` 也是一样，修改为自定义目录

如果配置 `yapi`, 第一次启动时需要修改 `docker-composer.yml` 文件，找到下面这段

修改前：

```
# 第一次启动使用
# command: "yapi server"
# 之后使用下面的命令
command: "node /my-yapi/vendors/server/app.js"
```

需要将注释放开，修改后：

```
# 第一次启动使用
command: "yapi server"
# 之后使用下面的命令
# command: "node /my-yapi/vendors/server/app.js"
```

待配置部署完后任需要将配置还原到修改前的配置

## mongo 初始化 yapi

部署 yapi 前需要在 `mongo` 下的 `mongo-conf` 目录下新建 `init-yapi-mongo.js` 文件内容如下，自定义修改 `user`，`pwd` 等配置信息

```
db.createUser({ user: 'admin', pwd: 'admin', roles: [ { role: "root", db: "admin" } ] });

db.auth("admin", "admin");
db.createUser({
    user: 'yapi',
    pwd: '123',
    roles: [
        { role: "dbAdmin", db: "yapi" },
        { role: "readWrite", db: "yapi" }
    ]
});
```

上面的 `user` 和 `pwd` 修改部署 `yapi` 是填写的信息