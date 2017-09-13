# swoole_server
[QuickStart][]

## 构建Server对象
``` php
<?php
$server = new swoole_server("127.0.0.1", 9501, SWOOLE_BASE, SWOOLE_SOCK_TCP);
```

对应扩展的实现

``` C
PHP_METHOD(swoole_server, __construct)
```

下面具体看看它都做了什么。

1. 初始化`swServer`

	``` C
	swServer *serv = sw_malloc(sizeof (swServer));
	swServer_init(serv);
	```
	
	`swServer`是封装swoole server的结构体。`swServer_init`主要是给`serv`赋初值。

1. 解析参数：`serv_host`、`serv_port`、`serv_mode`、`sock_type`

	serv_mode是swoole_server的运行模式

[QuickStart]: https://github.com/swoole/swoole-docs/blob/master/modules/swoole-server/quick-start.md