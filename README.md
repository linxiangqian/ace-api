# ACE API

**ACE API — AI Music Generation API Integration**

ACE API 是一个面向开发者的 AI 音乐生成 API 接口项目，提供统一的 AI 音乐创作接口，帮助开发者快速集成不同的 AI 音乐生成模型。

项目主要涉及 ACE Music API、Suno API、Mureka API 等 AI 音乐服务，支持音乐创作、灵感生成等多种创作场景。

通过统一的 API 接口，开发者可以更加便捷地将 AI 音乐生成能力集成到自己的网站、应用程序及其他业务系统中。

## 一、项目介绍

ACE API 致力于为开发者提供便捷、统一的 AI 音乐 API 接入方案。

主要支持以下 AI 音乐服务：

- **ACE Music API**：支持 ACE 音乐模型及 AI 音乐创作。
- **Suno API**：支持 Suno AI 音乐生成及相关创作功能。
- **Mureka API**：支持 Mureka AI 音乐生成及相关创作功能。

项目通过统一的接口调用方式，降低不同 AI 音乐模型的集成成本，让开发者能够更加专注于自身业务开发。

### 核心功能

- AI 音乐生成
- 灵感模式音乐创作
- 多模型统一 API 接入
- 音乐生成任务提交
- 任务进度查询
- 音乐生成结果获取
- API Token 身份验证
- 异步任务及回调处理

具体功能以实际 API 接口及模型版本支持情况为准。

## 二、软件架构

项目采用统一 API 接入架构，通过接口层对不同 AI 音乐模型进行统一管理和调用。

整体架构主要包括：

1. **API 接入层**：负责接收开发者请求及参数校验。
2. **身份验证层**：通过 API Token 验证用户身份及调用权限。
3. **模型管理层**：统一管理 ACE、Suno、Mureka 等音乐模型。
4. **任务调度层**：负责音乐生成任务的提交、调度及状态管理。
5. **结果处理层**：负责生成结果处理及任务回调。

## 三、安装教程

### 1. 获取 API Token

在使用 ACE API 之前，需要先申请 API 访问令牌。

API Token 申请地址：

https://suno4.cn/#/?i=8NCBS8_WXFF

完成申请后，获取 API Token，用于后续接口调用。

### 2. 配置 API 请求

根据接口文档配置 API 请求地址、请求方式及身份验证信息。

### 3. 开始调用

完成配置后，即可根据不同的模型及创作需求调用对应的 API 接口。

## 四、使用说明

### 1. ACE Music API 音乐创作

接口地址：

```http
POST /_open/suno/music/generate
```

请求参数示例：

```json
{
  "expectAiModel": "ace",
  "mvVersion": "acemusic-v1.1",
  "inputType": "10",
  "makeInstrumental": false,
  "gptDescriptionPrompt": "疯狂星期四",
  "callbackUrl": ""
}
```

参数说明：

| 参数 | 说明 |
|---|---|
| expectAiModel | 指定音乐模型，ace |
| mvVersion | 模型版本，acemusic-v1.1 |
| inputType | 创作模式，10 为灵感模式 |
| makeInstrumental | 是否生成纯音乐 |
| gptDescriptionPrompt | 音乐创作描述 |
| callbackUrl | 任务回调地址 |

### 2. 提交音乐生成任务

调用音乐生成接口后，系统将返回任务批次 ID 和具体任务 ID。

开发者可以根据返回的任务 ID 跟踪生成进度，并获取最终音乐作品。

### 3. 其他模型接入

根据实际业务需求，可以选择 ACE、Suno、Mureka 等不同音乐模型，调用对应的 API 接口完成音乐创作。

## 五、API 文档

后续将持续完善不同 AI 音乐模型的 API 接入文档，包括：

- ACE Music API 接口文档
- Suno API 接口文档
- Mureka API 接口文档
- 音乐生成参数说明
- 任务状态及回调说明
- API 调用示例

## 六、参与贡献

欢迎开发者参与项目建设，共同完善 AI 音乐 API 生态。

1. Fork 本仓库。
2. 新建 Feat_xxx 分支。
3. 提交代码及相关功能优化。
4. 新建 Pull Request，等待审核与合并。

## 七、相关资源

- **API Token 申请**：[https://suno4.cn/](https://suno4.cn/#/?i=8NCBS8_WXFF)
- **Gitee 官方博客**：[https://blog.gitee.com](https://blog.gitee.com)
- **Gitee 开源项目**：[https://gitee.com/explore](https://gitee.com/explore)
- **Gitee 使用手册**：[https://gitee.com/help](https://gitee.com/help)

## 八、免责声明

1. 本项目主要用于 AI 音乐 API 技术集成、开发及学习交流。
2. 开发者在使用相关 API 服务时，应遵守对应平台的服务条款及使用规范。
3. 请勿将 API Token、密钥等敏感信息直接提交至公开仓库。
4. 使用 AI 生成的音乐作品时，请自行确认相关内容的版权及商业使用授权。

---

**ACE API — Make AI Music Creation Easier.**
