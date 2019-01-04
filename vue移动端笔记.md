## 启动后台服务
1. navicat连上数据库以后，创建一个名为：dtcmsdb4的数据库，然后运行sql文件`dtcmsdb4.sql`

2. 修改app.js中的代码

   ![](./app.png)

3. 项目根目录`node app.js`启动服务 

## 项目初始化

vue create mobile-shop

cd mobile-shop

npm run serve



index.html中meta标签补全

```html
<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no">
```



字体图标样式及reset.css样式文件的引入（可以使用cdn）



首页导航图片复制到assets/imgs文件夹下面



## 首页

`App.vue`

```css
#app {
  color: #666666;
  padding-bottom: 50px;
}
.iconfont {
  font-size: 20px;
}
```



mint-ui使用

```shell
npm i mint-ui -S
```

main.js中添加

```js
import MintUI from 'mint-ui'
import 'mint-ui/lib/style.css'

Vue.use(MintUI)
```





首页轮播图图片

```js
imgList: [
  'http://m.itcast.cn/images/newslide/homepageandphone/20181528141522828.jpg',
  'http://m.itcast.cn/images/newslide/homepageandphone/20180918170957294.jpg',
  'http://m.itcast.cn/images/newslide/homepageandphone/20184827134845878.jpg'
]
```

首页样式

```sass
.home {
  .swiper {
    height: 205px;
    img {
      height: 100%;
      width: 100%;
    }
  }
  .nav-box {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    height: 100%;
    .nav-item {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 33.33%;
      margin: 10px 0;
      cursor: pointer;
      p {
        font-size: 20px;
      }
      img {
        width: 60px;
        height: 60px;
      }
    }
  }
}
```

首页导航emmet代码

```html
div>ul.nav-box>li.nav-item*6>i>img^p
```



## 底部导航组件

```scss
.nav-footer {
  font-size: 16px;
  display: flex;
  position: fixed;
  bottom: 0;
  height: 50px;
  width: 100%;
  border-top: 1px solid #e7e7e7;
  background-color: #fff;
  .nav-footer-item {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 25%;
    .badge {
      position: absolute;
      top: 3%;
      left: 50%;
      width: 14px;
      height: 14px;
      border-radius: 7px;
      background-color: #e4393c;
      text-align: center;
      line-height: 14px;
      color: white;
      font-size: 12px;
    }
  }
}
.active {
  color: #26a2ff;
}
```

页面结构

```
div.nav-footer>div.nav-footer-item*4>span.iconfont+span{xxx}
```



## 新闻列表页

```scss
.news-list {
  ul {
    padding: 40px 0 0 0;
    li {
      padding: 5px;
    }
  }
  .news-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    img {
      width: 100px;
      height: 50px;
      margin-right: 10px;
      flex: 1;
    }
    .content {
      flex: 2;
      width: 250px;
      .content-title {
        font-size: 14px;
        font-weight: bold;
      }
      .content-info {
        display: flex;
        justify-content: space-between;
        color: #26a2ff;
        font-size: 12px;
      }
    }
  }
}
```

页面结构

```html
div.news-list>ul>li>div.news-item>img+div.content>p.content-title+p.content-info>span.content-time+span.content-click
```



## 新闻详情页

```html
.news-detail {
  padding: 40px 0 0 0;
  .news-title {
    font-size: 14px;
    font-weight: bold;
  }
  .news-info {
    font-size: 12px;
    color: #26a2ff;
    display: flex;
    justify-content: space-between;
  }
  .news-content {
    font-size: 12px;
  }
}
```

页面结构

```
div>h1.news-title+p.news-info>span*3^^^div.news-content
```

## 评论组件

```scss
.inputbox {
  border: 1px solid #999;
}
.comment h3 {
  font-weight: bold;
  margin: 10px 0;
  font-size: 14px;
}
.line {
  border-top: 1px solid #999;
  padding-top: 10px;
}
.commentbox{
  li:not(:last-child) {
    border-bottom: 1px solid #999;
    margin: 5px 0;
  }
  p {
    font-size: 14px;
  }
  .comment-content {
    color: #999;
    font-size: 14px;
  }
}
.comment-user, .comment-time {
  font-size: 12px;
  color: #26a2ff;
}
```

页面结构

```html
div.comment>(div.submitbox>h3+div>mt-field+mt-button)+(div.commentbox>h3.line+ul>li>h4.comment-content+p>span.comment-user+span.comment-time)+div.button-group>mt-button*2
```

## 图片列表页面

```scss
  .img-list {
    margin-bottom: 55px;
    margin-top: 40px;
  }
  .cate {
    max-width: 100%;
    margin: 0;
    overflow-x:auto;
    overflow-y: hidden;
    font-size: 14px;
    ul {
      padding-left: 10px;
      margin: 5px 0;
      li {
        list-style: none;
        display: inline-block;
        padding: 0 0 0 5px;
        span {
          color:#0094ff;
        }
      }
    }
  }
  .img-list-box {
    ul {
      padding: 0;
      li {
        list-style: none;
        position: relative;
      }
    }
    p {
      font-size: 14px;
      color: #fff;
      position: absolute;
      bottom: 0px;
      left: 0px;
      background-color: rgba(0,0,0,0.4);
      .title {
        font-weight: bold;
      }
    }
    img {
      width: 100%;
    }
  }

  image[lazy=loading] {
    width: 100%;
    margin: auto;
  }
```

页面结构

```html
div.img-list>(div.cate>ul#cateul>li>span{全部}^li>span{循环})+div.img-list-box>ul>li>router-link>img^p>span.title
```

## 图片详情页



```
npm i vue-preview -S
import VuePreview from 'vue-preview'

Vue.use(VuePreview)
```



```scss
<style lang="scss">
  img {
    width: 100%;
    height: 100%;
  }
  li > div > div{
    display: flex;
    flex-wrap: wrap;
    &>figure{
      width: 33.33%;
    }
  }
</style>

<style lang="scss" scoped>
.img-detail {
  margin-top: 40px;
  margin-bottom: 55px;

  .img-title {
    font-size: 16px;
    font-weight: bold;
  }
  .img-info {
    display: flex;
    justify-content: space-around;
    color: #26a2ff;
    font-size: 14px;
  }
  .content {
    font-size: 14px;
  }
}
</style>
```

页面结构

```html
div.img-detail>(div>h3.img-title+p.img-info>span.time+span+span)+(ul>li>vue-preview)+div.content
```

## 商品列表页

```scss
.goods-list {
  margin: 40px 0 0 0;
  background-color: #f4f4f4;
  ul {
    display: flex;
    flex-wrap: wrap;
    font-size: 10px;
  }
  h4 {
    font-size: 12px;
    font-weight: bold;
    height: 32px;
    // 多行文本超出省略号
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    overflow: hidden;
  }
  .goods-li {
    width: 50%;
    box-sizing: border-box;
    padding-top: 5px;
    display: flex;
    justify-content: column;
    .goods-container {
      width: 100%;
      background-color: #fff;
      padding: 5px;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    .price-info {
      display: flex;
      justify-content: space-between;
      .price-new {
        color: red;
      }
      .price-old {
        text-decoration: line-through;
      }
    }
    .sell-info {
      display: flex;
      justify-content: space-between;
    }
  }

  .goods-li:nth-child(2n+1) {
    padding-right: 5px;
  }
  .goods-li:nth-child(2n) {
    padding-left: 5px;
  }
}
```

页面结构

```
ul>router-link.goods-li>div.goods-container>img+h4+div.goods-info>(div.price-info>span.price-new+span.price-old)+div.sell-info>span.sell-status+span.sell-leftcount
```

## 商品详情页

```s&#39;c
.goods-detail {
  margin-bottom: 50px;
  padding: 0 10px;
}
.swiperbox {
  height: 300px;
  img {
    width: 100%;
  }
}

.goods-title {
  font-size: 16px;
  font-weight: bold;
  margin: 10px 0;
}
.goods-price {
  font-size: 14px;
  .market-price {
    text-decoration: line-through;
  }
  .sell-price {
    color: #e4393c;
  }
}

.goods-info {
  font-size: 14px;
   .goods-desc {
    margin-top: 10px;
    font-size: 16px;
    font-weight: bold;
  }
}

.goods-footer {
  display: flex;
  position: fixed;
  bottom: 0;
  left: 0;
  height: 50px;
  width: 100%;
  border-top: 1px solid #e7e7e7;
  background-color: #fff;
  .goods-footer-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .contact, .cart {
    width: 40%;
    font-size: 12px;
    position: relative;
  }
  .badge {
    position: absolute;
    top: 3%;
    left: 50%;
    width: 14px;
    height: 14px;
    border-radius: 7px;
    background-color: #e4393c;
    text-align: center;
    line-height: 14px;
    color: white;
  }
  .add, .buy {
    width: 60%;
    color: white;
    &>span {
      font-size: 20px;
    }
  }
  .add {
    background-color: #ff9600;
  }
  .buy {
    background-color: #e4393c;
  }
}
```

页面结构

```scss
(mt-swipe.swiperbox>mt-swipe-item>img)+(div>h4.goods-title+p.goods-price>span.market-price+span.sell-price)+(div.goods-info>h4.goods-desc{商品参数}+p*3)+mt-button[type='primary']{图文介绍}+mt-button[type='danger']{商品评论}+div.goods-footer>(div.goods-footer-item.contact>span.iconfont.icon-kefu+span{联系客服})+(div.goods-footer-item.cart>span.iconfont.icon-gouwuche+span{购物车}+span.badge{4})+(div.goods-footer-item.add>span{加入购物车})+(div.goods-footer-item.buy>span{立即购买})
```

## 商品评论页面

```scss
.goods-comment {
  margin-top: 55px;
}
```

## 商品图文介绍

```s&#39;c
img {
    display: block;
}

.goods-desc {
  margin-top: 50px;
  h3 {
    font-weight: bold;
    color: #26a2ff;
    font-size: 16px;
    margin-bottom: 5px;
  }
  .desc-content {
    font-size: 14px;
  }
}
```

```
div>h3.desc-title+div.desc-content
```

## 购物车页面

```scss
.cart {
  height: 320px;
  margin-top: 45px;
  font-size: 14px;
  .empty-cart {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
    height: 100%;
    .empty-cart-img {
      height: 90px;
      width: 90px;
    }
    .empty-cart-text {
      font-size: 20px;
      color: #999;
      padding: 15px 0;
    }
    .btn {
      font-size: 20px;
      padding: 15px 55px;
      text-align: center;
      margin: 0 auto;
      border-radius: 10px;
      background: #ed601b;
      color: #fff;
    }
  }
  .cart-container {
    display: flex;
    align-items: center;
    margin: 5px;
    padding: 8px 10px;
    border: 1px solid #eeeeee;
    border-radius: 20px;
    .toogle {
      width: 20px;
      height: 20px;
      line-height: 20px;
      font-size: 20px;
    }
    .icon-checkbox-marked-circ {
      color: #ff5500;
    }
    .icon-checkbox-blank-circle-outline {
      color: #666666;
    }
  }
  .item-detail {
    display: flex;
    flex: 1;
    img {
      margin: 2px 0 2px 5px;
      width: 90px;
      height: 90px;
    }
    .item-info {
      width: 100%;
      padding: 5px 10px;
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      h3 {
        font-size: 16px;
        font-weight: 400;
      }
      .pay {
        display: flex;
        justify-content: space-between;
        .pay-price {
          color: #ff5500;
          font-weight: bold;
          line-height: 30px;
        }
        .edit-quantity {
          display: flex;
          height: 30px;
          line-height: 30px;
          .operate-btn {
            padding: 0 10px;
            font-size: 20px;
            color: #bababa;
          }
          .btn-minus {
            font-size: 14px;
          }
        }
      }
    }
  }
  .cart-footer {
    display: flex;
    justify-content: space-between;
    position: fixed;
    bottom: 0;
    left: 0;
    height: 50px;
    line-height: 50px;
    width: 100%;
    border-top: 1px solid #e7e7e7;
    background-color: #fff;
    .cart-footer-left {
      display: flex;
      justify-content: cneter;
      align-items: center;
      span {
        display: block;
        height: 50px;
        padding: 0 5px;
      }
    }
    .cart-footer-center {
      .total-price {
        color: #ff5500;
        font-weight: bold;
      }
    }
    .cart-footer-right {
      display: flex;
      flex-direction: column;
      padding: 0 20px;
      background-color: #ff5500;
      .goto-pay {
        color: #fff;
      }
    }
    .icon-checkbox-marked-circ {
      color: #ff5500;
    }
    .icon-checkbox-blank-circle-outline {
      color: #666666;
    }
  }
}
```

页面结构

```html
(div.empty-cart>img.empty-cart-img+div.empty-cart-text{购物车还是空的}+div.btn{去逛逛})+(div.cart-container>span.iconfont.toogle+div.item-detail>img+div.item-info>h3{xxxx}+div.pay>div.pay-price{￥200}+div.edit-quantity>p.operate-btn.iconfont.icon-minus+p.btn-input{2}+p.operate-btn.iconfont.icon-plus)+(div.cart-footer>div.cart-footer-left>span.iconfont.toogle+span{全选}^div.cart-footer-center>span{合计：}+span.total-price{￥200}^div.cart-footer-right>span.goto-pay{结算})
```

## 适配



```
npm i amfe-flexible -S        在main.js引入：import 'amfe-flexible'
npm i postcss-pxtorem -D
```

在post.config.js文件中的plugins属性下添加如下内容

```
     "postcss-pxtorem": {
        "rootValue": 37.5, // 设置根字体大小
        "propList": ['*'] // 设置哪些属性值的单位需要将px转换成rem   margin padding font-size
     }
```

