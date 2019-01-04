1. 先确定使用哪个脚手架工具？ **vue-cli 3.x**

2. 初始化项目模板
`vue create mobile-vux-demo`

3. 配置vux

    3.1 安装vux
    `npm i vux -S`
    
    3.2 安装vux-loader
    `npm install vux-loader --save-dev`

    3.3 安装less相关loader
    `npm install less less-loader --save-dev`

4. 配置vux环境

`npm install vue-loader@14.2.2 -D`

新建vue.config.js,在内部添加如下内容：
```js
module.exports = {
    configureWebpack: config => {
        require('vux-loader').merge(config, {
            options: {},
            plugins: ['vux-ui']
        })
    }
}
```

5. 使用

```js
import { XHeader } from 'vux'

export default {
  components: {
    XHeader
  }
}
```
