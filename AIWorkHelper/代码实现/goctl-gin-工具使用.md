---
type: 代码实现
---
# goCTL-Gin 工具使用

虽然Gin本身对于开发http服务已经很方便了，但是在启动一个新项目时，我们还是需要手动创建很多目录和文件，比如 `configs`、`handlers`、`logic`、`models` 等，并且要编写一些重复的模板代码。**goctl-gin这个工具就可以帮助我们快速处理这些重复的事情。**

# 1. goctl-gin介绍

`goctl-gin` 是一个代码生成工具，它基于知名的微服务框架 `go-zero` 中的 `goctl` 工具二次开发而来，专门用于快速构建一个结构清晰、功能完备的Gin项目。本项目只介绍该工具的基本使用，详细用法可以参考工具地址：<https://gitee.com/dn-jinmin/goctl-gin>

![BlockNote image](https://ls8sck0zrg.feishu.cn/space/api/box/stream/download/asynccode/?code=YzA1YWNjN2RmMzNlYTI4Yzg5MzMxNTFkYTFjNzc1YTBfQUE1aVVXcm9VNUNoUTRlVGR0UmV0MGREOTZLRzJ4TlRfVG9rZW46QUxzWWJKclQzb1BOT3J4OXV5bWNvWXo1bm9iXzE3Nzc4MzczMDU6MTc3Nzg0MDkwNV9WNA)

`goctl-gin`的核心思想是 **“API-First”**，即我们只需要编写一个 `.api` 文件来定义接口的路由、请求和响应，然后执行一条命令，`goctl-gin` 就能自动为我们生成整个项目的骨架代码。

![BlockNote image](https://ls8sck0zrg.feishu.cn/space/api/box/stream/download/asynccode/?code=ZjhhNDIyYTE3Njk4ZmFhZWEyYmE5ZDhkMDhhODE1YTdfOHY1UWgwMmlrZkNzbTBjdjFIcHM2QUtCVUlNeE9zOFpfVG9rZW46VGZ3ZmJmOFRpb1FzTnp4VjNGQWNqTGJ1bjdlXzE3Nzc4MzczMDU6MTc3Nzg0MDkwNV9WNA)

# 2. goctl工具安装

确保你的系统已经安装了以下工具：

1. Go 语言环境（版本 1.22+）
2. Git

## 2.1 安装步骤

从源码编译安装（推荐）

1. 克隆 goctl-gin 源码

```shell
git clone https://gitee.com/dn-jinmin/goctl-gin.git
```

- 到goctl-gin仓库目录下

```shell
cd goctl-gin
```

- 编译生成可执行文件

```shell
go build -o goctl-gin
```

- 将可执行文件移动到系统路径 Linux/macOS:

```shell
sudo mv goctl-gin /usr/local/bin/
```

Windows:

```shell
 将 goctl-gin.exe 移动到 PATH 环境变量包含的目录中
# 或者添加当前目录到 PATH 环境变量
```

- 验证安装

```shell
goctl-gin --version
```

如果安装成功，执行以上命令，则会打印出类似以下的版本号信息。不同的操作系统，现实可能会有差异，但是都会打印出版本信息

```shell
goctl version 1.6.4 darwin/arm64
```

# 3. 使用goctl-gin构建项目

我们来实战一下，看看 `goctl-gin` 的一些基本使用。这里我们创建一个空项目goctlDemo。

## 3.1 定义 `.api` 文件

首先，在项目中我门创建一个doc文件夹，在doc文件夹下，我们创建一个 `.api` 文件，` demo.api`。这个文件就是我们项目的“设计蓝图”。

```go
/*
【快速开始】
1. 生成代码：goctl api go -api ./doc/demo.api -dir ./
2. 运行服务：go run admin.go
3. 测试接口：curl http://localhost:8888/v1/admin/ping
*/
// API 语法版本（必需）
syntax = "v1"

// API 基本信息
info (
    title:   "简单示例 API"
    desc:    "用于学习 goctl-gin 的简单示例"
    author:  "鹏哥"
    version: "1.0"
)

// 数据类型定义
type (
    // 用户登录请求
    LoginRequest {
       Username string `json:"username"` // 用户名
       Password string `json:"password"` // 密码
    }
    // 用户登录响应
    LoginResponse {
       Token   string `json:"token"` // JWT令牌
       Message string `json:"message"` // 响应消息
    }
    // 简单响应
    SimpleResponse {
       Message string `json:"message"` // 响应消息
    }
)

// 服务定义 - 基础接口（无需认证）
@server (
    prefix: /v1/admin // 路由前缀：/v1/admin
)
service Admin {
    // 健康检查
    @handler Ping
    get /ping returns (SimpleResponse)

    // 用户登录
    @handler Login
    post /login (LoginRequest) returns (LoginResponse)
}

// 服务定义 - 需要认证的接口
@server (
    prefix:     /v1/admin // 路由前缀：/v1/admin
    middleware: Auth // 认证中间件
)
service Admin {
    // 获取用户信息（需要认证）
    @handler GetUserInfo
    get /user/info returns (SimpleResponse)
}

/*
生成的接口：
1. GET  /v1/admin/ping       - 健康检查
2. POST /v1/admin/login      - 用户登录
3. GET  /v1/admin/user/info  - 获取用户信息（需要认证）
*/
```

## 3.2 生成项目代码

在项目根目录下执行以下命令，生成项目代码

```shell
# goctl api go: 表示根据api文件生成go项目
# -api ./greet.api: 指定api文件的路径
# -dir ./: 指定生成代码的输出目录，./表示当前目录
goctl-gin api go -api ./doc/demo.api -dir ./
```

执行完命令以后，会生成如下项目结构

```bash
goctlDemo/
├── admin.go                    # 主程序入口
├── etc/admin.yaml             # 配置文件
├── doc/demo.api               # API定义文件
├── internal/
│   ├── config/                # 配置结构定义
│   ├── handler/               # HTTP请求处理器
│   │   └── v1/admin/          # 管理员模块处理器
│   ├── logic/                 # 业务逻辑层
│   │   └── v1/admin/          # 管理员模块业务逻辑
│   ├── middleware/            # 中间件（需要手动实现）
│   ├── svc/                   # 服务上下文
│   └── types/                 # 数据类型定义
└── go.mod                     # Go模块文件
```

## 3.3 补充业务逻辑

代码生成后，我们唯一需要做的，就是去 `internal/logic` 目录下找到对应的文件（比如 `loginlogic.go`），在生成的函数框架里，填上我们真正的业务逻辑代码。`handler` 层和路由注册的代码，工具已经帮我们完美地生成好了。这里只是讲解怎么去运用工具，具体的登陆，中间件逻辑这里就不详细去写了，验证一下ping方法，能成功返回就ok了

## 3.4 运行程序

在添加完逻辑代码之后，就可以运行我们的程序了。

1. 先执行以下命令加载项目依赖

```shell
go mod tidy
```

- 编译项目

```shell
go build
```

编译完成之后，可以看到项目根目录会生成一个goctlDemo可执行文件

![BlockNote image](https://ls8sck0zrg.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDQ5MWI5MjVkOTBmYTc0YmNhNjk0OTNhOGNiZDg1YTJfWHp0c3piYWk3WGpzdWVZcjlqUno1R1dub1dna1VUaFpfVG9rZW46UWFEOGJWQ1cxb28wMFp4UEVEQWNyTklYbmZoXzE3Nzc4MzczMDU6MTc3Nzg0MDkwNV9WNA)

- 启动程序

直接`./goctlDemo`运行测试

![BlockNote image](https://ls8sck0zrg.feishu.cn/space/api/box/stream/download/asynccode/?code=MGIwYzhjZGE0ZWU5NmRiNGUxNTczZDJiNTg3YjNjNGJfWDloWXdLTmVtUjVtMDRORWc4djkzWHBSQ2psMUFldXZfVG9rZW46QmtTZGI2Z0dIbzFUTkp4eUpNRGNiNHYwbmdjXzE3Nzc4MzczMDU6MTc3Nzg0MDkwNV9WNA)

可以看到服务启动成功，正在监听8888端口。

- 测试ping接口

执行以下命令，测试ping接口

```shell
curl http://localhost:8888/v1/admin/ping
```

请求正常返回

```shell
{"message":"pong"}
```

接口可以正常响应。

后续如果我们需要加新的业务接口，只需要在api文件下添加对应的server和service就可以了
