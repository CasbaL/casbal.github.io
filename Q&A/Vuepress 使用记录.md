# Vuepress 使用记录    
  [官方文档点这](https://vuepress.vuejs.org/)

### demo尝试
1. 全局安装 `yarn global add vuepress`   
2. cd 到自己的目录   
3. 新建一个md文件 `echo '# Hello VuePress!' > README.md`   
4. 开启开发模式 `vupress dev`
    >   默认是显示 readme.md    
vuepress自带热更新，然后你就可以愉快地写文章了
5. 打包 `vuepress build` 文件会输出到 `.vuepress/dist` 
    >   cd .vuepress/dist     
    >   执行 `serve` 打开浏览器查看最终效果

### 已有项目安装
比如我当前 github.io 的目录是这样
```
.
├── Q&A
│   ├── 2020-01-07.md
│   └── 2020-01-09.md
├── README.md
├── demo
│   └── 2019-11-19.md
└── index.html
```

接下来按官网步骤改造我的 github.io    

1. `yarn add -D vuepres` 安装 vuepress 到开发依赖
    >`yarn init -y` 自动生成默认的package.json 文件
2. package.json 添加 script
    ```
    ...
    "scripts": {
      "dev": "vuepress dev",
      "build": "vuepress build"
    },
    ...
    ```
3. `yarn dev` 访问浏览器已经可以看到 readme.md 里的东西了
4. 接下来修改 readme.md 里的内容链接到自己写的md就ok！
    ```
    ...
    2020-01-07: [关于 Map 和 Object](./Q&A/2020-01-07.md)
    2020-01-09: [Vuepress 使用记录](./Q&A/2020-01-09.md)
    ...
    ```
    readme.md 当做目录，最终会打包成index.html      
ok~ Vuepress 使用起来确实简单方便     
          
[部署Github page看这里](./集成%20Travis%20CI%20自动部署到%20GitHub%20page.md)