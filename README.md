# tctip打赏插件

## tctip是什么

tctip是一个js插件，作用是在web网页右侧生成一个打赏浮动窗  
可下载后到demo目录查看效果

## tctip当前版本

+ 当前版本为 `1.0.0`，**此版本为大版本变动，不兼容老版，请使用当前版本**
+ 历史版本为`0.1`，已不再维护，如有需求,[点此切换](https://github.com/greedying/tctip/tree/v0.1)

## 当前版本特点

+ 界面暂时维持不变
+ 参数配置和使用方式不兼容老版本
+ 只需引入一个js文件，不需要额外引入js、css等
+ 同时支持`umd`、`webpack`等方法使用

## 使用方法

### 页面使用（多数人的使用方式)

#### 第一步，引入js
   
   一般引入min版本，即引入`tctip-版本号.min.js`文件  
   在当前项目中即`dist/tctip-1.0.0.min.js`

+ 您可以把此js文件下载到您的服务器合适目录进行引用
+ 您也可以直接使用我提供的静态链接`http://static.tctip.com/tctip-1.0.0.min.js`

```javascript
  <script src="http://static.tctip.com/tctip-1.0.0.min.js"></script>

```

#### 第二步，新建tctip变量，同时传入配置参数，然后运行init函数

```javascript
  new tctip({
    top: '20%',
    button: {
      id: 9,
      type: 'dashang',
    },
    list: [
      {
        type: 'alipay',
        qrImg: './images/alipay.jpg'
      }, {
        type: 'wechat',
        qrImg: './images/wechat.jpg'
      }, {
        type: 'bitcoin',
        qrContent: '1PhQySHF1ZuoRwoZ8G4CDLEtE6fAnD3GJP'
      }
    ]
  }).init()
```

刷新页面，即可看到效果


### webpack 方式使用 

#### 第一步，安装

```javascript
  npm install vux-uploader --save
```

#### 第二步，引入包


```javascript
  import tctip from 'tctip'
```
#### 第三步，传参使用，类似web方式

```javascript
  new tctip(config).init()
```


### 参数说明

* top
  * `类型`: String
  * `默认值`: `10%`
  * `含义`: 插件顶端距离页面最上面的距离
  * `备注`: 格式如 `100px`或者`10%`

* button
  * `类型`: Object，包含`id`和`type`两个子数组
  * `id`: 
    * `类型`: Number
    * `默认值`: `1`
    * `含义`: 代表图片颜色
    * `备注`: 取值范围为1-9
  * `type`: 
    * `类型`: String
    * `默认值`: `dashang`
    * `含义`: 按钮上的汉字，有`打赏`和`赞助`两种
    * `备注`: 只能取`dashang`或者`zanzhu`

* list
  * `类型`: Array
  * `默认值`: []
  * `含义`: 重点配置，右侧打赏显示，不能为空
  * `备注`: 一个数组，最多传入五个元素，每个元素又有如下几项陪配置
  * `type`: 
    * `类型`: String
    * `默认值`: 无
    * `含义`: 打赏类型
    * `备注`: 系统自带四种默认type，`alipay`,`wechat`,`bitcon`,`tenpay`，如果不是这四种，可以随意写
  * `qrImg`: 
    * `类型`: String
    * `默认值`: 无
    * `含义`: 二维码图片地址
    * `备注`: 尽量裁剪图片周边的空白。`重要但是非必传`
  * `qrContent`: 
    * `类型`: String
    * `默认值`: 无
    * `含义`: 二维码内容
    * `备注`: 和`qrImg`二者必须传一个。如果传入本参数，插件自动生成二维码
  * `icon`: 
    * `类型`: String
    * `默认值`: 无
    * `含义`: 图标，列入支付宝图标
    * `备注`: 当type为系统默认四种之一时，本参数可省略
  * `name`: 
    * `类型`: String
    * `默认值`: 无
    * `含义`: 支付名称，例如支付宝、微信等
    * `备注`: 当type为系统默认四种之一时，本参数可省略
  * `desc`: 
    * `类型`: String
    * `默认值`: 无
    * `含义`: 二维码下面的一句短语，类似`大爷行行好`之类的
    * `备注`: 当type为系统默认四种之一时，本参数可省略

* stat
  * `类型`: Boolean
  * `默认值`: true
  * `含义`: 是否上报，用于作者统计使用者
  * `备注`: 本参数只是方便作者统计插件使用情况，可视情况关闭

## 技术栈

- webpack
- qrcode
- es6
- 其他技术

## 感谢与参考

+ [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator)

## 案例收集
+ 您可以[点此填写](https://github.com/greedying/tctip/issues/8)，我会定期整理
+ 您也可以直接clone项目，提交PR

## qq群
+ qq群号：`188087193`
+ 验证消息: `github`

## 改进与完善
欢迎提issue,欢迎PR
