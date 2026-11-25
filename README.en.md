# ACE API

**ACE API — AI Music Generation API Integration**

ACE API is an AI music generation API integration project designed for developers. It provides a unified API interface for integrating different AI music generation models into applications and services.

The project focuses on AI music services such as ACE Music API, Suno API, and Mureka API, supporting various music creation scenarios.

With a unified API integration approach, developers can easily incorporate AI-powered music generation capabilities into their websites, applications, and business systems.

## 1. Introduction

ACE API aims to provide developers with a convenient and unified solution for integrating AI music generation services.

### Supported AI Music Services

- **ACE Music API**: Supports ACE music models and AI music generation.
- **Suno API**: Supports Suno AI music generation and related creative features.
- **Mureka API**: Supports Mureka AI music generation and related creative features.

The project simplifies integration across different AI music models, allowing developers to focus more on building their own applications and services.

### Key Features

- AI music generation
- Music creation with inspiration mode
- Unified API integration for multiple models
- Music generation task submission
- Generation progress tracking
- Music generation result retrieval
- API Token authentication
- Asynchronous task processing and callbacks

Available features depend on the actual API endpoints and supported model versions.

## 2. Software Architecture

ACE API adopts a unified API integration architecture, providing a standardized way to manage and invoke different AI music generation models.

The architecture consists of the following components:

1. **API Gateway Layer**: Handles incoming developer requests and parameter validation.
2. **Authentication Layer**: Verifies user identity and API access permissions through API Tokens.
3. **Model Management Layer**: Manages AI music models such as ACE, Suno, and Mureka.
4. **Task Scheduling Layer**: Handles music generation task submission, scheduling, and status management.
5. **Result Processing Layer**: Processes generation results and task callbacks.

## 3. Installation

### Step 1: Obtain an API Token

Before using ACE API, developers need to apply for an API access token.

**API Token Application:**

[Apply for an API Token](https://suno4.cn/#/?i=8NCBS8_WXFF)

After completing the application, obtain your API Token for subsequent API requests.

### Step 2: Configure API Requests

Configure the API endpoint, HTTP method, request parameters, and authentication information according to the API documentation.

### Step 3: Start Using the API

Once the configuration is complete, you can call the corresponding APIs based on your selected model and music creation requirements.

## 4. Usage

### 4.1 ACE Music API - Music Generation

**Endpoint:**

```http
POST /_open/suno/music/generate
```

**Request Body Example:**

```json
{
  "expectAiModel": "ace",
  "mvVersion": "ace-step-1.5-xl",
  "inputType": "10",
  "makeInstrumental": false,
  "gptDescriptionPrompt": "Crazy Thursday",
  "callbackUrl": ""
}
```

### Request Parameters

| Parameter | Description |
|---|---|
| expectAiModel | Specifies the music model: ace |
| mvVersion | Model version: ace-step-1.5-xl |
| inputType | Creation mode: 10 for Inspiration Mode |
| makeInstrumental | Whether to generate instrumental music |
| gptDescriptionPrompt | Music creation prompt |
| callbackUrl | Task callback URL |

### 4.2 Submit a Music Generation Task

After calling the music generation endpoint, the API returns a task batch ID and individual task IDs.

Developers can use these task IDs to track generation progress and retrieve the final music results.

### 4.3 Integrate Other Models

Depending on your application requirements, you can select different AI music models, including ACE, Suno, and Mureka, and call their corresponding API endpoints.

## 5. API Documentation

More API documentation and integration examples will be added over time, including:

- ACE Music API Documentation
- Suno API Documentation
- Mureka API Documentation
- Music Generation Parameters
- Task Status and Callback Instructions
- API Integration Examples

## 6. Contributing

Contributions from developers are welcome! Help us improve the project and build a better AI music API ecosystem.

1. Fork this repository.
2. Create a new branch (`Feat_xxx`).
3. Commit your code and improvements.
4. Submit a Pull Request for review.

## 7. Resources

- **API Token Application**: [https://suno4.cn/](https://suno4.cn/#/?i=8NCBS8_WXFF)
- **Gitee Blog**: [https://blog.gitee.com](https://blog.gitee.com)
- **Gitee Explore**: [https://gitee.com/explore](https://gitee.com/explore)
- **Gitee Documentation**: [https://gitee.com/help](https://gitee.com/help)

## 8. Disclaimer

1. This project is intended for AI music API integration, development, and technical learning.
2. Developers must comply with the terms of service and usage policies of the relevant API providers.
3. Do not commit API Tokens, secret keys, or other sensitive credentials to public repositories.
4. Before using AI-generated music, developers should independently verify applicable copyright requirements and commercial usage permissions.

---

**ACE API — Make AI Music Creation Easier.**
