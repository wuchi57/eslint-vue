# 代码一致性说明

![ESLint + Prettier + Husky + Lint-staged = Code Consistency](https://miro.medium.com/v2/resize:fit:720/format:webp/1*PdxQHwcQZDxJK4rWB743Sg.png)

<br>

### 相关依赖：

```shell
yarn add -D eslint prettier eslint-plugin-prettier eslint-config-prettier husky lint-staged
```

<br>

### 机制说明：

当运行 git commit 时，触发 ESLint 检查所提交代码缺陷并自动修复，ESLint 再自动触发 Prettier 对代码进行格式化，最后提交优化后的代码

<br>

### 配置相关：

ESLint 配置选用 airbnb-base

Prettier 相关配置位于 .prettierrc.json，具体说明可查看 [Prettier 官方文档](https://prettier.io/docs/en/options.html) 或查看 [中文笔记](https://jsweibo.github.io/2019/10/17/Prettier%E7%9A%84%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6/)

```js
printWidth: 120,                   // !打印宽度，默认80
tabWidth: 2,                       // tab宽度，默认2
tab: false,                        // 缩进字符是否使用tab，默认false
semi: false,                       // 是否使用分号，默认false
singleQuote: true,                 // !是否使用单引号，默认false
jsxSingleQuote: true,              // !jsx是否使用单引号，默认false
quoteProps: 'as-needed',           // 对象键名是否使用引号包裹，默认'as-needed'
trailingComma: 'es5',              // !多行时后面逗号处理方式，默认'all'
bracketSpacing: true,              // 字面量对象内侧是否使用空格，默认true
bracketSameLine: false,            // !html、vue、jsx中的 > 是否在同一行，默认true
arrowParens: 'always',             // 箭头函数是否需要参数括号，默认always
rangeStart: 0,                     // 格式化开始范围，默认0
rangeEnd: Infinity,                // 格式化结束范围，默认Infinity
parser: None,                      // 选择那个解析器，默认空
filepath: None,                    // 指定文件名以推断使用那个解析器，默认空
requirePragma: false,              // 是否只格式化文件顶部有 Pragma 指令的文件，默认false
insertPragma: false,               // 格式化后，是否在文件顶部插入 Pragma 指令，默认false
proseWrap: 'preserve',             // markdown 文件是否折行，默认preserve
htmlWhitespaceSensitivity: 'css',  // 是否使用空白字符格式化 HTML 文件，默认css
endOfLine: 'lf',                   // 行尾符，默认lf
embededLanguageFormatting: 'auto', // 是否格式被引号包含的代码，默认auto
singleAttributePerLine: false,     // 是否强制每个属性占一行，默认false
```

<br>

### 备注：

如果希望每次 VSCode 保存时触发 ESLint + Prettier 检测，可以在全局/当前项目下的 .vscode -> settings.json 添加以下代码

```JSON
"editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
 }
```
