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

 