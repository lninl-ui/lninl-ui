# lninl-ui

[![NPM Version](https://img.shields.io/npm/v/lninl-ui)](https://www.npmjs.com/package/lninl-ui)
[![NPM Downloads](https://img.shields.io/npm/dw/lninl-ui)](https://github.com/lninl-com/ui)
[![GitHub Issues or Pull Requests](https://img.shields.io/github/issues/lninl-com/ui)](https://github.com/lninl-com/ui/issues)
[![GitHub License](https://img.shields.io/github/license/lninl-com/ui)](https://github.com/lninl-com/ui/blob/main/LICENSE)

一个基于 [Vue 3](https://cn.vuejs.org/guide/introduction) & [UnoCSS](https://unocss.dev/guide/)，兼容 [TDesign](https://tdesign.tencent.com/mobile-vue/getting-started) 的 [uni-app](https://uniapp.dcloud.net.cn/) UI开发组件。

## 🪄 特性

- <img src="https://static.tdesign.tencent.com/favicon.ico" alt="TDesign logo" width="14" align="center" /> 兼容 [TDesign](https://tdesign.tencent.com/mobile-vue/getting-started) - 大厂设计([Figma or Sketch](https://tdesign.tencent.com/source?tab=mobile))，[API](https://tdesign.tencent.com/mobile-vue/getting-started) 规范，功能完善，基于 [uni-app](https://uniapp.dcloud.net.cn/)， 支持平台广
- <img src="https://unocss.dev/logo.svg" alt="UnoCSS logo" width="14" align="center" /> [UnoCSS](https://unocss.dev/guide/) - 高效、简洁的原子化 CSS 引擎
- 🧩 JavaScript - 回归简单、高效
- <img src="https://vuejs.org/logo.svg" alt="Vue logo" width="14" align="center" /> [Vue 3](https://cn.vuejs.org/guide/introduction) - `<script setup>` 语法
- 🌓 [DarkMode](https://uniapp.dcloud.net.cn/tutorial/darkmode.html) & [iOS安全区域适配](https://uniapp.dcloud.net.cn/tutorial/darkmode.html#ios-%E5%AE%89%E5%85%A8%E5%8C%BA%E5%9F%9F%E9%80%82%E9%85%8D) - 暗黑模式、iOS安全区域适配等支持
- 🌐 [uni-app 国际化](https://uniapp.dcloud.net.cn/tutorial/i18n.html) & [Vue I18n](https://vue-i18n.intlify.dev/guide/) - 全方位国际化方案，编辑器也支持
- 📦 [pnpm](https://pnpm.io/zh/) & [Vite](https://github.com/vitejs/vite) - 快速灵活构建
- ⚙️ [@antfu/eslint-config](https://github.com/antfu/eslint-config) - 深度结合 [uni-app](https://uniapp.dcloud.net.cn/)，多文件类型的格式支持，import、UnoCSS 自动排序，增强编码一致性，大神同款代码修复保证代码质量
- 🌱 [simple-git-hooks](https://github.com/toplenboren/simple-git-hooks) & [lint-staged](https://github.com/lint-staged/lint-staged) & [commitlint](https://commitlint.js.org/) - 自动配置、规范代码提交质量
- 🏅 [vscode](https://code.visualstudio.com/) - 深度集成、保存即可格式化、代码质量检查

## 🔨 开发

### 安装

```bash
# 创建项目
npm install -g @vue/cli
npx degit dcloudio/uni-preset-vue#vite my-vue3-project

# 安装 lninl-ui UI开发组件
pnpm i lninl-ui
# 或
npm i lninl-ui
# 或
yarn add lninl-ui
```

### 配置

- 打开 main.js，在`export function createApp()`之前添加 `import 'uno.css'`，如下

```js copy
...
import 'uno.css'

export function createApp() {
    ...
}
```

- 打开 vite.config.js，添加 unocss 支持，如下

```js copy
import { defineConfig } from 'vite'
import uni from '@dcloudio/vite-plugin-uni'
import unocss from 'unocss/vite'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [
    uni(),
    unocss(),
  ],
})
```

- 在项目根目录下(与 package.json 同级) 添加 uno.config.js 文件，文件内容参考

[./uno.config.js](./uno.config.js)

- 打开 pages.json, 添加 easycom 配置 (此步骤可忽略)

```json copy
{
    ...
    "easycom": {
        "autoscan": true,
        "custom": {
            "^l-(.*)": "lninl-ui/components/l-$1/l-$1.vue"
        }
    }
    ...
}
```

### 添加或修改功能

核心代码位于 ./src/uni_modules/lninl-ui/ 。

目前只完成组件：

- [x] Badge 徽标 - 用于告知用户，该区域的状态变化或者待处理任务的数量。
- [x] Icon 图标 - Icon 作为UI构成中重要的元素，一定程度上影响UI界面整体呈现出的风格。
- [x] TabBar 标签栏 - 用于在不同功能模块之间进行快速切换，位于页面底部。

进行中的组件：

- [ ] Button 按钮 - 按钮用于开启一个闭环的操作任务，如“删除”对象、“购买”商品等。
- [ ] Form 表单 - 按钮用于开启一个闭环的操作任务，如“删除”对象、“购买”商品等。
- [ ] Input 输入框 - 用于文本信息输入。
- [ ] Textarea 多行文本框 - 用于多行文本信息输入。
- [ ] Upload 上传 - 用于相册读取或拉起拍照的图片上传功能。
- [ ] Radio 单选框 - 用于在预设的一组选项中执行单项选择，并呈现选择结果。
- [ ] Checkbox 多选框 - 用于预设的一组选项中执行多项选择，并呈现选择结果。
- [ ] Cascader 级联选择器 - 用于多层级数据选择，主要为树形结构，可展示更多的数据。
- [ ] Search 搜索框 - 用于用户输入搜索信息，并进行页面内容搜索。
- [ ] Swiper 轮播 - 用于循环轮播一组图片或内容，也可以滑动进行切换，轮播动效时间可以设置。

下一阶段开发的组件：

- [ ] 其他组件

欢迎大家的加入，一起完善！

### 交流反馈

欢迎加入QQ群号：195822307 [点此加入](https://qm.qq.com/q/THay2lOvcs)

---

## lninl-ui 样例

一个基于 [lninl-ui](https://github.com/lninl-com/ui) 的 [uni-app](https://uniapp.dcloud.net.cn/) 样例，麻雀虽小五脏俱全。

样例位于 ./ 目录中。

### 🪄 样例特性

- 🧩 JavaScript - 回归简单、高效
- <img src="https://vuejs.org/logo.svg" alt="Vue logo" width="14" align="center" /> [Vue 3](https://cn.vuejs.org/guide/introduction) - `<script setup>` 语法
- <img src="https://unocss.dev/logo.svg" alt="UnoCSS logo" width="14" align="center" /> [UnoCSS](https://unocss.dev/guide/) - 高效、简洁的原子化 CSS 引擎
- <img src="https://static.tdesign.tencent.com/favicon.ico" alt="TDesign logo" width="14" align="center" /> [lninl-ui](https://github.com/lninl-com/ui) - 兼容 [TDesign](https://tdesign.tencent.com/mobile-vue/getting-started)，大厂设计([Figma or Sketch](https://tdesign.tencent.com/source?tab=mobile))，[API](https://tdesign.tencent.com/mobile-vue/getting-started) 规范，功能完整
- 🍍 [Pinia](https://pinia.vuejs.org/zh/) & [pinia-plugin-persistedstate](https://prazdevs.github.io/pinia-plugin-persistedstate/zh/guide/) - 符合直觉、可持久化的状态管理
- ⚡ [luch-request](https://www.quanzhan.co/luch-request/guide/3.x/#%E4%BB%8B%E7%BB%8D) - 网络请求封装，灵活强大
- 🌐 [uni-app国际化](https://uniapp.dcloud.net.cn/tutorial/i18n.html) & [Vue I18n](https://vue-i18n.intlify.dev/guide/) - 全方位国际化方案，编辑器也支持
- 🌓 [DarkMode](https://uniapp.dcloud.net.cn/tutorial/darkmode.html) & [iOS安全区域适配](https://uniapp.dcloud.net.cn/tutorial/darkmode.html#ios-%E5%AE%89%E5%85%A8%E5%8C%BA%E5%9F%9F%E9%80%82%E9%85%8D) - 暗黑模式、iOS安全区域适配等支持
- 📦 [pnpm](https://pnpm.io/zh/) & [Vite](https://github.com/vitejs/vite) - 快速灵活构建
- ⚙️ [@antfu/eslint-config](https://github.com/antfu/eslint-config) - 深度结合 [uni-app](https://uniapp.dcloud.net.cn/)，多文件类型的格式支持，import、UnoCSS 自动排序，增强编码一致性，大神同款代码修复保证代码质量
- 🌱 [simple-git-hooks](https://github.com/toplenboren/simple-git-hooks) & [lint-staged](https://github.com/lint-staged/lint-staged) & [commitlint](https://commitlint.js.org/) - 自动配置、规范代码提交质量
- 🏅 [vscode](https://code.visualstudio.com/) - 深度集成、保存即可格式化、代码质量检查

### 🔨 样例运行和编译

```bash
# 安装依赖
pnpm i

# 开发
pnpm run dev:h5
pnpm run dev:mp-weixin
pnpm run dev:mp-toutiao
pnpm run dev:app
...

# 打包
pnpm run build:h5
pnpm run build:mp-weixin
pnpm run build:mp-toutiao
pnpm run build:app
...
```
