# 前言

为什么选择react而不是vue也不是angular？

ng1.x老衲用过3个月，觉得整个框架组织结构更像是专门为系统指定的，要什么有什么，这样的话对于在线mobile app性能是个大的考验，还有一个不喜欢的点是他的写法更像是PHP哪种形式的绑定，比较总的后端思维在里面

vue贫道也做过一个微信端的小项目，觉得还是比较容易上手的，1.x感觉跟ng1.x的思想上更加接近，但是对于开发app的话，没有weex也只能依赖于cordova之类的，觉得在性能上可能还是差了那么点意思，再有一个重要的点就是，主要是尤小溪个人的项目，虽然后面也有不少的人加入，但觉得精力还是太有限了。

最后react可能是所有方案里面最合适最这种的一个技术栈了，不加全家桶的话，跟vue一样的轻量，移动端有比较成熟的react native。

so，就是这个了


## 技术栈

react + redux + react-router + webpack + ES6/7 + fetch + less + flex



## 项目运行

#### 注意：由于涉及大量的 ES6/7 等新属性，nodejs 必须是 6.0 以上版本 ，node 7 是先行版，有可能会出问题，建议使用 node 6 稳定版

```
git clone https://github.com/duxianwei520/react.git  

cd react （进入当前的项目）

npm install  (安装依赖包)

npm start (运行本地开发环境)
npm run build (打包)

node mockserver.js (前端本地用node模拟接口进程)

```


## 说明

>  喜欢的别忘记了可以star一下的噢！ 

>  开发环境 win10  Chrome 58.0.3029.110  nodejs 6.2.0

>  如果npm install太慢导致有些npm依赖包下载失败 你可以看控制台的报错信息，再手动npm install 具体的开发包，推荐使用淘宝的注册源，直接运行，
```
npm install -g cnpm --registry=https://registry.npm.taobao.org 

```
如果这个方法还不行的话，可以到我的百度网盘上面去下载我已经压缩好的npm依赖包，地址是
``` 
http://pan.baidu.com/s/1pLdPWgj

```
把下载到本地的node_modules.rar文件直接解压到跟app同级的当前文件夹，记住是当前文件夹的，然后不用npm install就可以直接npm start跑起来项目了。

>  如有问题请直接在 Issues 中提，或者您发现问题并有非常好的解决方案，欢迎 PR 👍



## 功能一览
- [√] 项目按路由模块加载
- [√] 登录，以及登录权限控制
- [√] 退出
- [√] 欢迎主页
- [√] 左侧菜单，正常moni切换
- [√] redux完整范例
- [√] nodejs代理数据完全示例
- [√] 页面高度flex自适应




## 总结

1、这整个技术栈是我们公司前端部门在用的，写熟悉了之后，用来做后台管理系统类的实在是很方便，大家都表示再也不要用jQuery来做这样子的系统了

2、目前来说，不足的地方是在于没有很好的区分dev环境跟pro环境，这个后面弄好了再补充上来；mock数据现在还不是那么的方便，需要自己一个个的添加api的json文件




## 部分截图


### 登录页

<img src="https://github.com/duxianwei520/react/blob/master/screenshots/login.png" width="704" height="561"/> 


### 欢迎页

<img src="https://github.com/duxianwei520/react/blob/master/screenshots/welcome.png" width="1010" height="566"/>



### 列表页

<img src="https://github.com/duxianwei520/react/blob/master/screenshots/list.png" width="1002" height="582"/>

### 请求接口

<img src="https://github.com/duxianwei520/react/blob/master/screenshots/requestData.png" width="885" height="590"/>


### 接口按返回

<img src="https://github.com/duxianwei520/react/blob/master/screenshots/receiveData.png" width="997" height="586"/>




## 项目结构

```
.
├─.babelrc                            // babel的配置
├─.config.json                        // 如果使用了ip代理，那么配置文件在这里
├─.eslintcache                        // eslint的缓存
├─.eslintignore	                      // eslint设置忽略的文件
├─.eslintrc.json                      // eslint的配置文件
├─.gitignore                          // git忽略上传的文件
├─mockserver.js                       // node本地转发json的执行文件
├─package.json                        // npm命令包
├─proxy.js                            // 设置代理的js,现在基本不用
├─readme.md                           // 项目介绍
├─webpack-test.config.js              // webpack测试的配置文件，目前还没做
├─webpack.config.js                   // 目前项目webpack的配置文件
├─_config.yml 
├─_gitattributes
├─test
|  └setup-test-env.js
├─screenshots                         // 项目截图
|      ├─list.png
|      ├─login.png
|      ├─receiveData.png
|      ├─requestData.png
|      └welcome.png
├─mockapi                             // 前端静态json数据存放的文件夹
|    └data.json
├─app                                 // 页面主文件
|  ├─client.js
|  ├─history.js
|  ├─index.html                       // 入口html文件，配置静态菜单等全局常见变量
|  ├─routes.js                        // 路由配置
|  ├─utils                            // 公用的文件
|  |   ├─ajax.js                      // 发送异步获取数据的配置
|  |   ├─config.js                    // 常用的配置
|  |   └index.js                      // 发送异步数据前的准备工作
|  ├─style                            // 样式库
|  |   ├─base.less                    // 全局通用的样式
|  |   └theme.less                    // 存放变量的less
|  ├─store                            // redux的store的配置
|  |   └configureStore.js
|  ├─reducers                         // reduce的配置
|  |    ├─common.js
|  |    ├─house.js
|  |    ├─index.js
|  |    └tabList.js
|  ├─pages                            // 项目绝大部分业务文件
|  |   ├─welcome.js
|  |   ├─test
|  |   |  ├─index.js
|  |   |  ├─sub.js
|  |   |  └third.js
|  |   ├─house
|  |   |   ├─houseManage.js
|  |   |   └index.js
|  ├─middleware                       
|  |     ├─index.js
|  |     ├─logger.js
|  |     └router.js
|  ├─images                           // 图片文件夹
|  |   ├─default.png
|  |   ├─leftBg.jpg
|  |   └navcontrol.png
|  ├─iconfont
|  |    ├─iconfont.eot
|  |    ├─iconfont.svg
|  |    ├─iconfont.ttf
|  |    └iconfont.woff
|  ├─containers                       // 全局的框架文件 
|  |     ├─App
|  |     |  ├─extra.js
|  |     |  ├─footer.js
|  |     |  ├─header.js
|  |     |  ├─index.js
|  |     |  ├─login.js
|  |     |  ├─rightAside.js
|  |     |  ├─tabList.js
|  |     |  ├─leftNav
|  |     |  |    └index.js
|  ├─constants
|  |     ├─actionTypes.js
|  |     └index.js
|  ├─components                        // 公用的组件库 
|  |     ├─index.less
|  |     ├─searchTable
|  |     |      └index.js
|  |     ├─searchForm
|  |     |     └index.js
|  |     ├─searchChosen
|  |     |      └index.js
|  |     ├─multiSelect
|  |     |      └index.js
|  ├─api                              // 整个项目API的url配置
|  |  ├─common.js
|  |  ├─house.js
|  |  └index.js
|  ├─actions                          // 整个项目的actions配置
|  |    ├─common.js
|  |    ├─house.js
|  |    └tabList.js


```


## License

[GPL](https://github.com/duxianwei520/react/blob/master/COPYING)
