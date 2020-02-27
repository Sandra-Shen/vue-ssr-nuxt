# sj-vue-nuxt-pm2

> My fabulous Nuxt.js project

## Build Setup

``` bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).

### vue服务端渲染
- 1、技术栈：vue,Nuxt.js,pm2
- 2、pm2：全局安装pm2  $ npm i -g pm2  
    pm2 是一个带有负载均衡功能的Node应用的进程管理器。当你要把你的独立代码利用全部的服务器上的所有CPU，并保证进程永远都活着，0秒的重载， PM2是完美的。在服务器shell中，先安装pm2，安装后pm2 list查看进程列表，如果说pm2未找到，需要设置下环境变量
- 3、项目部署
    1)、next打包部署  $ npm run build ；
    2)、打包完成将 .nuxt、nuxt.config.js、package.json、static四个文件部署到服务器上，并 $ npm install  安装依赖包
    3)、pm2安装成功之后，进入nuxt项目目录，执行 pm2 start npm --name ‘project-name’ -- start
        project-name，就是package.json里的name名
    4)、启动项目，这时项目运行在你服务器上的3000端口上，我们还需要使用nginx 作为反向代理把这个端口专门映射到一个域名上，请参考下面链接
    https://segmentfault.com/a/1190000012774650
