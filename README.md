### :heart: 介绍

H5 快速自动化开发模板、脚手架 。要求 node 12+(本项目配置为 gulp4， 如果 node 版本较低，需要降低 gulp 版本，并修改对应 gulpfile)

### :hourglass: 适用项目

工期约一个月内的小项目

### :muscle: 工作流

监听文件更新 => 清除老版本 => 编译、转译 => 加 hash 版本号 => 多终端热更新

### :deciduous_tree: 项目结构

```
├─ dist    //打包目录
│  │
│  ├─ index.html
│  │
│  ├─ image
│  │
│  ├─ style
│  │
│  ├─ rev  //存放添加hash后缀的文件对照关系表
│  │
│  ├─ media
│  │
│  ├─ script
│  │
│  └─ lib
│
├─less    //less文件源码目录
│
├─script    //js文件源码目录
│
├─style    //less编译成css后存放的目录
│
└─index.html    //所有html文件均放置在根目录下
```

<br>
<br>

### :hand: 使用方法

_clone 到本地后，命令行进入该目录，运行:_<br>
<br>

`$ npm install`

安装完所需依赖后

`$ gulp`

架设静态服务器，开始愉快的敲键盘吧~

tips:如果本地开发中需要使用 ajax 跨域调接口，将你本地 nginx 的配置文件替换为本项目中的 nginx.conf 文件,43-63 行根据自己情况配置一下~,然后在 gulpfile.js 文件 37 行把代理选项打开~,最后启动 nginx 服务~(如果没有 nginx 请先自行下载)

---

### :zap:    注意事项

1.所有 html 文件引用静态资源，均引用 dist/目录下的，勿直接引用源码<br> 2.新添加文件后需要重启 gulp 工作流，否则无法实时热更新<br> 3.静态服务器的默认入口只能有一个（dist/下的 index.html），可在 gulpfile.js 自行修改<br> 4.图片、音视频等静态资源直接放在 dist 下对应文件夹里，该工具不提供图片、音视频压缩功能<br> 5.开启 nginx 反向代理时由于路径问题可能会发生静态资源访问不到的情况，需将`<base href='dist/'>`调整为`<base href='./'>`<br> 6.开启反向代理时,3001 端口是提供热更新功能的端口,3003 端口也可以正常访问页面,但是没有热更新功能

### :star:   Update

2018.6.6:less 模板中新增了一些个人常用 mixin 方法

2018.10.9:更新了 npm 依赖包的版本

2018.11.16:增加了 nginx 反向代理解决跨域的功能
