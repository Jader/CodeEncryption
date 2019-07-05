# 快速、方便的 Swoole-Compiler 代码加密环境

## 部署

### 安装依赖工具

- Git  
- Docker [https://docs.docker.com/install/]
- Docker-compose [https://docs.docker.com/compose/install/#install-compose]

### 获取部署脚本

```
$ git clone https://github.com/JaderH/CodeEncryption.git
```

### 运行容器编排

```
$ cd JadeDock   // 进入项目根目录
$ docker-compose up -d   // 容器编排命令
```

$ docker-compose exec swoole-compiler swoole-compiler

## 使用

### 目录介绍

```
├── code                // 这里放加密的文件或文件夹
├── conf                // 加密时所使用的配置文件目录
├── output              // 加密完成后授权文件和加密文件包存在位置
├── docker-compose.yml
├── LICENSE
├── README.md
```


### 命令介绍

获取swoole-compiler信息、帮助信息

```
docker-compose exec swoole-compiler swoole-compiler
```

生成授权文件

```
docker-compose exec swoole-compiler swoole-compiler -t license -c conf/compiler.config
```

生成加密文件

```
docker-compose exec swoole-compiler swoole-compiler -t code -c conf/compiler.config
```

## 注意

Swoole-Compiler 服务端所需的 PHP 扩展 和配置

php.ini

```
[swoole_compiler]
extension=swoole_loader72.so ; 关于扩展暂时不提供，需要可以联系我
swoole_license_files=/data/www/Jade/jade.licence ;这里是产生的授权文件
```


