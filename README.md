
## **功能列表**
- 登录登出
- 菜单异步加载
- 页面详细权限控制
- 多语言支持
- 布局切换
- 高德地图集成
- Echarts集成
- 错误页面
- mock数据
- 页面加载进度条

## **项目使用**
``` bash
# 安装项目依赖
npm install

# 开启本地服务，默认为localhost:9000
npm run dev

# 项目打包，构建生产环境
npm run build

# 打包过程中想查看具体报告则可以通过以下命令实现
npm run build --report
```

## Nginx简单部署配置

将打包后的文件放到Nginx安装目录中的html文件夹内，然后对Nginx进行简单配置即可。

```
...
# 以上保持默认配置即可

server {
    listen       9090;
    server_name  localhost;
    # 项目文件目录
    root   html/vue-backend;
    index  index.html index.htm;

    location / {
        # vue-router使用history模式下的必须配置
        try_files $uri $uri/ /index.html;
        index index.html;
    }
}
```
