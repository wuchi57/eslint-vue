# 代码一致性说明

![ESLint + Prettier + Husky + Lint-staged = Code Consistency](https://miro.medium.com/v2/resize:fit:720/format:webp/1*PdxQHwcQZDxJK4rWB743Sg.png)

<br>

### 相关依赖：
```shell
yarn add -D eslint prettier eslint-plugin-prettier eslint-config-prettier husky lint-staged
```  
<br>

### 配置相关：
ESLint 配置选用 airbnb-base

Prettier 相关配置位于 .prettierrc.json  

<br>

### 机制说明：
当运行 git commit 时，触发 ESLint 检查所提交代码缺陷并自动修复，ESLint 再自动触发 Prettier 对代码进行格式化，最后提交优化后的代码

<br>

### 备注：
如果希望每次 VSCode 保存时触发 ESLint + Prettier 检测，可以在全局/当前项目下的 .vscode -> settings.json 添加以下代码
```JSON
"editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
 }
 ```
