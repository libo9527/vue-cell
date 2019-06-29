## Vue webpack 初始项目目录

### .editorconfig

```shell
root = true

[*]
charset = utf-8
# 使用空格进行缩进
indent_style = space
# 缩进两个空格
indent_size = 2
# 换行符：
# - win：crlf
# - linux/unix：lf
# - mac：cr
end_of_line = lf
# 文件最后一行为空行
insert_final_newline = true
# 剪裁尾部空格
trim_trailing_whitespace = true
```

### .eslintrc.js

rules 取值：


- "off" 或 0 - 关闭规则
- "warn" 或 1 - 开启规则，使用警告级别的错误：warn (不会导致程序退出),
- "error" 或 2 - 开启规则，使用错误级别的错误：error (当被触发的时候，程序会退出)

### index.html

Vue 项目的入口文件，webpack 在编译时会动态的将依赖添加进该文件中。

### package.json

package.json 是依赖管理文件。

- scripts 属性代表可用的命令脚本。

  例如执行 `npm run dev`，相当于执行 `nom run webpack-dev-server --inline --progress --config build/webpack.dev.conf.js`

- 依赖版本中 `^a.b.c` 表示最低版本为 a.b.c

##  Webpack

### webpack 是如何进行编译的

## 设备像素比

> [设备像素比devicePixelRatio简单介绍« 张鑫旭-鑫空间-鑫生活](https://www.zhangxinxu.com/wordpress/2012/08/window-devicepixelratio/)

### 移动端一像素边框问题

src/common/stylus/base.styl

```stylus
@media (-webkit-max-device-pixel-ratio: 1.5), (-webkit-min-device-pixel-ratio: 1.5)
  .border-1px
    ::after
      -webkit-transform: scaleY(0.7)
      transform: scaleY(0.7)
  
@media (-webkit-max-device-pixel-ratio: 2), (-webkit-min-device-pixel-ratio: 2)
  .border-1px
    ::after
      -webkit-transform: scaleY(0.5)
      transform: scaleY(0.5)
```

-webkit 是为了适配。

## SVG

矢量图，好处是伸缩后质量不会下降。

## 制作图标

## VUE

### Vue-Router

- router 实例中的 `routes` 以及 挂载根实例时的名字 router 是固定的，使用时要注意。

  ```js
  const router = new VueRouter({
    routes // (缩写) 相当于 routes: routes
  })
  
  /////////////////////////////////////////
  
  new Vue({
    router
  })    
  ```

## CSS

- a 标签默认的 display 是 inline，但只有当点击 a 标签中文字对应的区域时才会跳转，如果想要将区域扩展到外部的 div，则需要将 display 设置为 block。

### 伪元素 after

> [::after (:after)-MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::after)

::after 是 CSS3 的语法，:after 是 CSS2 的语法。

### 顺序规范

1. 布局属性

   display

2. 宽高属性

3. 字体颜色等

### Stylus

#### &

- 代表父选择器

#### @

Stylus 中引入 styl 文件需要使用 @import