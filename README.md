## 介绍

bin-editor-next 为更好的区分vue版本依赖，现包名已更新为bin-editor-next，组件名不变。

### 最新版本

[![NPM version](https://img.shields.io/npm/v/bin-editor-next.svg)](https://www.npmjs.com/package/bin-editor-next)

## 安装

通过[unpkg.com/bin-editor-next](https://unpkg.com/bin-editor-next/) 可以看到 bin-editor-next 最新版本的资源，也可以切换版本选择需要的资源，在页面上引入 js
和 css 文件即可开始使用：

```javascript
<!-- import Vue.js -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
<!-- import bin-editor-next -->
<script src="https://unpkg.com/bin-editor-next@1.0.0/lib/index.min.js"></script>
```

### npm 安装

推荐使用npm安装，它能更好地和[webpack](https://webpack.js.org/)打包工具配合使用。而且可以更好的和
es6配合使用。并且支持按需引入

```shell
npm i bin-editor-next -S
# or 
yarn add bin-editor-next
```

## 引入

在 main.js 中写入以下内容：

```javascript
import { createApp } from 'vue'
import Editor from 'bin-editor-next';
import App from './App.vue';

import * as ace from 'brace'
import 'brace/ext/emmet'
import 'brace/ext/language_tools'
import 'brace/mode/json'
import 'brace/snippets/json'
import 'brace/theme/chrome'

const app = createApp(App)
app.component(Editor.name, Editor)
app.mount('#app', true)
```

### CDN 安装

快速构建一个编辑器需要依赖 [ace-builds](https://github.com/ajaxorg/ace-builds/) 构建，去下载对应资源放置到项目中或使用cdn

```javascript
<script src="../lib/bin-editor-next/src-min-noconflict/ace.js"></script>
<script src="../lib/bin-editor-next/src-min-noconflict/ext-beautify.js"></script>
<script src="../lib/bin-editor-next/src-min-noconflict/ext-language_tools.js"></script>
<script src="../lib/bin-editor-next/src-min-noconflict/mode-json.js"></script>
<script src="../lib/bin-editor-next/src-min-noconflict/snippets/json.js"></script>

<script src="../lib/bin-editor-next/bin-editor-next.min.js"></script>
```

上面五个是依赖，根据需要实现的语言类型引入

推荐使用npm方式来进行使用，这样可以更好的配合webpack进行构建
