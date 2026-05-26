# oc-go-cc Chrome Translate Extension

通过 [oc-go-cc](https://github.com/wojiaowangdabao/oc-go-cc) 代理翻译网页内容为中文的 Chrome 扩展。

## 原理

1. 在网页上右键选择「翻译页面为中文」
2. 插件提取页面文本，分块发送到 oc-go-cc 代理
3. oc-go-cc 将请求转换为 OpenAI 格式并转发给底层模型
4. 收到翻译结果后，插件逐段替换页面原文

## 前置条件

- 安装并运行 [oc-go-cc](https://github.com/wojiaowangdabao/oc-go-cc)
- oc-go-cc 默认监听 `http://127.0.0.1:3456`

## 安装

1. 打开 Chrome，访问 `chrome://extensions`
2. 开启右上角的「开发者模式」
3. 点击「加载已解压的扩展程序」
4. 选择本项目所在的文件夹

## 使用

1. 确保 oc-go-cc 正在运行
2. 在任意网页上右键点击
3. 选择「翻译页面为中文」
4. 页面右上角会显示翻译进度
5. 翻译完成后页面文本会被替换为中文

## 配置

如需修改代理地址或翻译模型，编辑 `background.js` 中的：

- `PROXY_URL` — oc-go-cc 代理地址（默认 `http://127.0.0.1:3456/v1/messages`）
- `model` — 请求中的模型名（默认 `claude-sonnet-4-20250514`）
