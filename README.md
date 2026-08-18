# LAI — 本地 AI 助手

> 跑在 Android 手机上的离线大模型应用：模型下载、本地推理、对话交互，一部手机就是一个私有 AI 终端。

![version](https://img.shields.io/badge/version-1.0.0-4FC3F7) ![platform](https://img.shields.io/badge/platform-Android%208.0%2B-green) ![offline](https://img.shields.io/badge/offline-%E6%9C%AC%E5%9C%B0%E6%8E%A8%E7%90%86-orange)

## ✨ 功能特性

- **端侧离线推理** — 内置 llama.cpp 推理引擎，模型加载后全程本地运行，断网可用，对话数据不出设备
- **硬件体检** — 自动识别 SoC / 内存 / 存储并评分，给出 L1~L4 适配档位与个性化模型推荐
- **模型库** — 支持 20 款主流 GGUF 量化模型（Qwen2.5 / Llama3 / Gemma2 / DeepSeek-R1 / Phi3.5 等，0.36B~14B），断点续传 + SHA256 完整性校验
- **流式对话** — 聊天气泡逐 token 流式输出，实时显示生成速度（tokens/s），四套对话模板自动适配（ChatML / Llama3 / Gemma2 / Phi3）
- **OpenAI 兼容 API 服务** — 一键开启本地 API 服务器（`/v1/chat/completions`，支持 SSE 流式），自定义 API KEY，任何支持 OpenAI 协议接入的软件都能调用你手机上的模型

## 📥 下载安装

1. 进入 [Releases](../../releases) 页面
2. 下载最新版 `LAI-v1.0.0-release.apk`
3. 手机上允许"安装未知来源应用"后完成安装

**系统要求**：Android 8.0+（arm64 设备或 x86_64 模拟器）

## 🚀 快速上手

1. 启动 App，在首页填入你的模型服务器地址并连接
2. 「硬件体检」查看设备适配档位与推荐模型
3. 「模型库」选择模型下载（含进度 / 速度 / 校验），进入对话页即可离线畅聊
4. 「API 服务」页开启服务后：
   - 接口类型：OpenAI 兼容
   - Base URL：`http://127.0.0.1:8080/v1`（同机软件）或 `http://<手机IP>:8080/v1`（局域网设备）
   - API KEY：App 内自定义
   - 模型名：任意（自动路由到当前已加载模型）

> **说明**：模型文件需通过自建模型服务器分发（App 内置 registry 协议），服务器组件不在本仓库提供。

## 🔒 隐私与安全

- 对话与推理全部本地完成，无任何遥测 / 云端上报
- API 服务强制 KEY 鉴权（恒时比较防时序侧信道），端口与 KEY 均可自定义
- 请求体大小限制 2MB，异常请求自动拒绝

## 📄 其他

- 本项目仅供学习与技术交流
- 模型能力取决于所选开源模型，输出内容不代表项目立场
