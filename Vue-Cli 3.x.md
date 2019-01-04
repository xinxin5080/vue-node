## Vue CLI 3.x介绍

Vue CLI 3.x是最新的Vue脚手架工具。在这篇教程中，我们将学习如何使用Vue CLI3来开发我们的Vue应用程序

在这篇教程中，我们将学习：

- 如何安装最新版的Vue CLI
- 如何使用Vue CLI 3.x 的各种特性
- 如何使用Vue CLI 3.x创建一个Vue应用程序
- 如何使用图形化用户界面
- Vue CLI2.x 和 Vue CLI3.x 对比

Vue ClI 3.x为开发者提供了一个全新的体验，它允许开发者可以零配置创建一个Vue项目，但是一旦你的项目需要更多配置，开发者又有能力使用插件添加更多的配置。不同于React的脚手架工具create-react-app，开发者可以自定义配置项而不需要eject，仅仅通过Vue CLI的插件就可以实现。

Vue CLI 是一个基于 Vue.js 进行快速开发的完整系统，提供：

- 通过 `@vue/cli` 搭建交互式的项目脚手架。
- 通过 `@vue/cli` + `@vue/cli-service-global` 快速开始零配置原型开发。
- 一个运行时依赖 (```@vue/cli-service```)，该依赖：

  - 可升级；
  - 基于 webpack 构建，并带有合理的默认配置；
  - 可以通过项目内的配置文件进行配置；
  - 可以通过插件进行扩展。
- 一个丰富的官方插件集合，集成了前端生态中最好的工具。
- 一套完全图形化的创建和管理 Vue.js 项目的用户界面。

## 上手使用

### 安装Vue CLI 3.x

```bash
npm install -g @vue/cli
或者
yarn global add @vue/cli
```

### 创建项目

```bash
vue create <project-name>
```
选择配置，默认或者手动

![](.\imgs\01.png)

之后会提示选择一些特性，例如TypeScrip支持，添加Vue Router，添加Vuex等。（按空格键选择，回车进入下一步）

![](.\imgs\02.png)

是否使用class风格的组件语法

![](.\imgs\03.png)

路由是否开启history模式![](.\imgs\04png)

![](.\imgs\05.png)

选择一个css预处理器

![](.\imgs\06.png)

选择一种校验规则

![](.\imgs\07.png)

选择校验的时机

![](.\imgs\08.png)

如何存放babel,postcss,eslint等的配置文件？单独存放或者集成在package.json文件中

![](.\imgs\09.png)

询问是否将当前配置保存为预设给以后的项目使用

![](.\imgs\10.png)

![](.\imgs\11.png)

服务启动后，在浏览器中打开相应网址，就可以看到效果了

![](.\imgs\12.png)

### 开启服务

进入项目文件夹，然后`npm run serve`



### 图形化用户界面(GUI)

得益于 Guillaume CHAU（Vue.js 核心团队）的出色表现，Vue CLI 3 还附带了一个完整的 GUI，不仅可以创建新项目，还可以管理项目中的插件和任务，例如：

![](.\imgs\a1.png)

#### 启动图形化用户界面

```
vue ui
```

#### 创建项目

![](.\imgs\a2.png)

![](.\imgs\a3.png)

![](.\imgs\a4.png)

![](.\imgs\a5.png)

![](.\imgs\a6.png)

![](.\imgs\a7.png)

![](.\imgs\a8.png)

#### 管理项目

##### 管理插件

![](.\imgs\a9.png)

![](.\imgs\a10.png)

##### 管理依赖

![](.\imgs\a11.png)

![](.\imgs\a12.png)

#### 配置项目

![](.\imgs\a13.png)

#### 运行npm脚本

![](.\imgs\a14.png)



## Vue CLI 2.x 对比Vue CLI 3.x

### 安装方式

Vue CLI 2.x安装： ` npm install -g vue-cli`

Vue CLI 3.x安装: `npm install -g @vue/cli`

### 创建项目方式

Vue CLI 3.0以前的版本，我们使用以下命令在本地创建新项目： `vue init <template> <name>`

- `<template>` 是项目使用的模板名称
- `<name>` 是项目名称



Vue CLI 3.0以后的版本，只需要运行： ` vue create <name>`

### 项目结构

Vue CLI 3.0以前

```
    .
    ├── build
    │   ├── build.js
    │   ├── check-versions.js
    │   ├── logo.png
    │   ├── utils.js
    │   ├── vue-loader.conf.js
    │   ├── webpack.base.conf.js
    │   ├── webpack.dev.conf.js
    │   └── webpack.prod.conf.js
    ├── config
    │   ├── dev.env.js
    │   ├── index.js
    │   ├── prod.env.js
    │   └── test.env.js
    ├── index.html
    ├── package.json
    ├── src
    │   ├── App.vue
    │   ├── assets
    │   │   └── logo.png
    │   ├── components
    │   │   └── HelloWorld.vue
    │   └── main.js
    ├── static
    └── test
        ├── e2e
        │   ├── custom-assertions
        │   ├── nightwatch.conf.js
        │   ├── runner.js
        │   └── specs
        └── unit
            ├── jest.conf.js
            ├── setup.js
            └── specs
```

Vue CLI 3.0以后

```
    .
    ├── package.json
    ├── public
    │   ├── favicon.ico
    │   └── index.html
    └── src
        ├── assets
        │   └── logo.png
        ├── components
        │   └── HelloWorld.vue
        ├── views
        │   └── About.vue
        │ 	└── Home.vue
        ├── App.vue
        ├── main.ts
        ├── router.ts
        └── store.ts
        
```

可以明显看到，Vue CLI 3.0 以后版本的构建目录更加精简，专注在撰写应用上，而不必花太多时间在配置的问题上。（以上对比忽略了`.gitignore`, `node_modules`等文件）

### 支持零配置启动

1. 创建一个单文件组件，如`App.vue`

```vue
<template>
  <div>{{msg}}</div>
</template>
<script>
export default {
  data () {
    return {
      msg: 'hello world!'
    }
  }
}
</script>
```

2. 安装扩展： `npm install -g @vue/cli-service-global`
3. 在`App.vue`文件的目录下运行: `vue serve App.vue`

此时你会看到：

![](.\imgs\b1.png)

接着在浏览器运行：`http://localhost:8080`即可看到以下效果：

![](.\imgs\b2.png)

### 更简单的配置方式

调整 webpack 配置最简单的方式就是在 `vue.config.js` 中的 `configureWebpack` 选项提供一个对象

```js
// vue.config.js
module.exports = {
  configureWebpack: {
    plugins: [
      new MyAwesomeWebpackPlugin()
    ]
  }
}
```

该对象将会被 [webpack-merge](https://github.com/survivejs/webpack-merge) 合并入最终的 webpack 配置。

如果你需要基于环境有条件地配置行为，或者想要直接修改配置，那就换成一个函数 (该函数会在环境变量被设置之后懒执行)。该方法的第一个参数会收到已经解析好的配置。在函数内，你可以直接修改配置，或者返回一个将会被合并的对象：

```js
// vue.config.js
module.exports = {
  configureWebpack: config => {
    if (process.env.NODE_ENV === 'production') {
      // 为生产环境修改配置...
    } else {
      // 为开发环境修改配置...
    }
  }
}
```

### 支持使用Vue CLI 3.0以前版本创建模板

- 安装扩展

```bash
 npm install -g @vue/cli-init
 # 或者
 yarn global add @vue/cli-init
```

- 初始化项目模板


```
vue init webpack testing-old-cli
```

