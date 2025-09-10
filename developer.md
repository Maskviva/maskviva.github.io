# 开发者文档

## 开发准备

在开始开发前，您需要掌握以下技术知识：

- Vue 3 (Composition API)
- TypeScript
- Webpack 构建工具
- Node.js 和 npm 包管理器

### 环境准备

请确保安装了 [NodeJS](https://nodejs.org/) 并正确配置环境变量。推荐使用 LTS 版本以确保稳定性。

## 项目搭建

### 获取插件模板

在安装好 NodeJS 后，需要从 [Voxesis 插件示例仓库](https://gitee.com/Maskviva/voxesis-plugin-example) 获取插件模板。您可以使用
Git 工具克隆仓库，或者下载 ZIP 文件。

```bash
git clone https://gitee.com/Maskviva/voxesis-plugin-example.git
```

### 安装依赖

进入项目目录后，安装所需的 Node 模块：

```bash
# 使用 npm
npm install
# 或使用 yarn
yarn install
# 或使用 pnpm
pnpm install
```

### 开发与构建命令

- `npm run dev` - 启动开发服务器
- `npm run build` - 构建生产版本，打包后的文件会生成在 `dist` 文件夹下

> 我们提供了一个开发工具 [voxesis-plugin-cli](https://www.npmjs.com/package/voxesis-plugin-cli?activeTab=readme)
> 上述的dev的页面就是voxesis-plugin-cli提供的

## 项目结构

```
your-plugin 
├── src 
│ ├── components/ # Vue 组件 
│ ├── utils # 工具函数 
│ ├── App.vue # 主组件 
│ └── main.ts # 入口文件 
├── manifest.json # 插件配置文件 
├── webpack.config.js # Webpack 配置文件 
├── package.json # 项目配置和依赖 
└── README.md # 插件说明文档
```

## 配置文件

配置文件分为 `webpack.config.js` 和 `manifest.json`，都在项目的根目录下。

### webpack.config.js

在 `webpack.config.js`
中大部分配置可以进行修改，但有注释会提示不能修改的项，请勿修改这类项。其他配置请参考 [Webpack 官方文档](https://webpack.js.org/)。

### manifest.json

这是插件的主配置文件，包含以下主要字段：

- [name](#): 插件名称
- [main](#):
  插件入口文件 (通常是 `*.js`)
- [introduce](#): 插件在侧边栏显示的文本
- [line_icon](#): 未选中时的图标 (SVG 格式)
- [fill_icon](#): 选中时的图标 (SVG 格式)
- [settings](#): 注册插件的设置项

#### settings 配置

[settings](#)
是一个数组，里面存放着插件的设置项，这些设置项在插件加载时会被注册到 Voxesis 的设置页中。

```typescript
type Setting = {
    plate: string, // 板块名称，相同板块名称的设置项会合并在同一个面板中 
    display?: string, // 显示布局，目前支持 "grid" | "flex" 两种布局 
    items: Item[] // 设置项 
};

type Item =
    {
        label: string, // 设置项的名称 
        type: "input" | "drop_down" | "switch" | "select_dir" | "select_file", // 设置项的类型 
        key: string, // 设置项在 Voxesis 配置文件中的 key 
        value_type?: "number" | "text" | "password", // 当 type 为 input 时输入框的类型 
        title?: string, // 当 type 为 select_dir 或 select_file 时显示的标题 
        filters?: { // 当 type 为 select_dir 或 select_file 时文件过滤器 
            displayName: string, // 显示的标题 pattern: string, // 文件过滤器，例如: "*.txt" 
        },
        filesList?: string[][], // 当 type 为 select_dir 或 select_file 时允许选择的文件列表，用于验证文件的合法性 
        value: string | boolean, // 设置项的值 
        max?: number, // 当 type 为 input 且 value_type 为 number 时输入框的最大值 
        min?: number, // 当 type 为 input 且 value_type 为 number 时输入框的最小值 
        placeholder?: string, // 当 type 为 input | drop_down | select_dir | select_file 时输入框的提示文本 
        list?: { label: string, value: string }[], // 当 type 为 drop_down 时下拉框的选项，label 为选项的显示文本，value 为选项的值 
    }
```

## 最佳实践

1. **类型安全**: 充分利用 TypeScript 的类型系统，为组件、函数和接口定义明确的类型
2. **组件化开发**: 将复杂界面拆分为可复用的组件
3. **响应式数据**: 合理使用 Vue 3 的响应式 API (ref, reactive)
4. **异步处理**: 使用 async/await 处理异步操作
5. **错误处理**: 添加适当的错误处理机制
6. **性能优化**: 避免不必要的重新渲染，合理使用 computed 和 watch

## 发布插件

构建完成后，将 `dist` 目录中会生成一个以你插件名称命名的文件夹，这个文件夹直接放入 Voxesis 的plugins目录下就可以使用了，在发布时应把这个文件夹打包成压缩文件。
