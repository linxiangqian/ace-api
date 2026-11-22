# ACE Music API 接入指南：灵感模式音乐创作（acemusic-v1.1）

## 一、功能介绍

ACE Music API 支持通过灵感模式进行 AI 音乐创作。用户只需要输入一段简单的文字描述，例如歌曲主题、创作方向或情绪氛围，AI 就能根据提示词进行音乐创作。

灵感模式不需要用户手动编写完整歌词或复杂的音乐风格描述，只需提供创作主题，即可快速开启音乐创作。

通过 ACE Music API，开发者可以将 AI 音乐创作能力集成到自己的网站、应用或小程序中，实现自动化音乐生成。

本次接口示例使用的模型版本为 **acemusic-v1.1**。

## 二、请求令牌申请

在调用 ACE Music API 之前，开发者需要先申请 API 访问令牌（Token），用于接口身份验证及权限校验。

**API Token 申请地址：**

[Suno API 访问令牌申请](https://suno4.cn/#/?i=8NCBS8_WXFF)

完成申请后，获取对应的 API Token，并按照平台接口要求配置请求身份验证信息。

注意：请妥善保管 API Token，避免泄露或将其暴露在客户端代码中。

## 三、API 接口信息

**接口地址：**

```http
POST /_open/suno/music/generate
```

**请求体示例：**

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

### 请求参数说明

| 参数 | 示例值 | 说明 |
|---|---|---|
| expectAiModel | ace | 指定 ACE 音乐模型 |
| mvVersion | acemusic-v1.1 | 指定 ACE 模型版本 |
| inputType | 10 | 灵感模式 |
| makeInstrumental | false | 是否生成纯音乐，false 表示包含人声 |
| gptDescriptionPrompt | 疯狂星期四 | 音乐创作灵感描述 |
| callbackUrl | 空字符串 | 任务回调地址 |

其中，`gptDescriptionPrompt` 是灵感模式的核心参数，可以输入歌曲主题、创作想法或内容描述，AI 将根据提示词进行音乐创作。

## 四、API 响应示例

提交创作任务成功后，接口会返回任务批次 ID 和具体的音乐创作任务信息。

**响应示例：**

```json
{
  "code": 200,
  "msg": "您已成功提交创作任务，目前剩余并发任务数为9",
  "data": {
    "taskBatchId": "1067069768483733505",
    "items": [
      {
        "id": "1860190112013385729",
        "inputType": "10",
        "gptDescriptionPrompt": "写一首关于兄弟情义的歌",
        "progress": 0,
        "status": 0,
        "progressMsg": "排队中..."
      },
      {
        "id": "1860190112013385730",
        "inputType": "10",
        "gptDescriptionPrompt": "写一首关于兄弟情义的歌",
        "progress": 0,
        "status": 0,
        "progressMsg": "排队中..."
      }
    ]
  }
}
```

### 响应参数说明

| 参数 | 说明 |
|---|---|
| code | 请求状态码，200 表示提交成功 |
| msg | 任务提交结果及并发信息 |
| taskBatchId | 本次创作任务批次 ID |
| items | 本次提交的创作任务列表 |
| id | 单个音乐创作任务 ID |
| inputType | 创作模式 |
| gptDescriptionPrompt | 音乐创作提示词 |
| progress | 任务生成进度 |
| status | 任务当前状态 |
| progressMsg | 任务进度描述 |

**注意：** 接口返回 `code: 200` 表示创作任务提交成功，并不代表音乐已经生成完成。开发者需要保存返回的任务 ID，用于后续查询音乐生成进度及获取最终作品。

## 五、灵感模式创作示例

灵感模式适合多种音乐创作场景，只需更换 `gptDescriptionPrompt` 即可尝试不同的创作方向。

**示例 1：情感歌曲**

```json
{
  "gptDescriptionPrompt": "写一首关于青春遗憾和错过的伤感情歌"
}
```

**示例 2：兄弟情义**

```json
{
  "gptDescriptionPrompt": "写一首关于兄弟情义的歌曲，表达一起奋斗、不离不弃的情感"
}
```

**示例 3：流行音乐**

```json
{
  "gptDescriptionPrompt": "创作一首轻快的流行歌曲，适合夏日旅行时聆听"
}
```

**示例 4：励志歌曲**

```json
{
  "gptDescriptionPrompt": "写一首充满力量的励志歌曲，表达面对困难依然坚持梦想的信念"
}
```

## 六、开发接入流程

开发者可以按照以下步骤完成 ACE Music API 的接入：

1. **申请 API Token：** 通过平台申请访问令牌，获取接口调用权限。
2. **配置模型参数：** 指定 `expectAiModel: "ace"` 和 `mvVersion: "acemusic-v1.1"`。
3. **选择创作模式：** 设置 `inputType: "10"`，使用灵感模式。
4. **提交创作内容：** 通过 `gptDescriptionPrompt` 传入歌曲主题或创作描述。
5. **调用生成接口：** 请求音乐生成接口，提交创作任务。
6. **获取任务 ID：** 保存返回的任务 ID，用于后续任务状态查询。
7. **获取音乐作品：** 根据任务状态获取最终生成的音乐。

## 七、总结

ACE Music API 通过灵感模式降低了 AI 音乐创作的使用门槛。开发者无需准备复杂的歌词和音乐参数，只需输入简单的文字创意，就可以快速提交音乐生成任务。

通过 `acemusic-v1.1` 模型，开发者可以将灵感驱动的 AI 音乐创作能力整合到自己的产品中，为用户提供更加便捷的音乐创作体验。
