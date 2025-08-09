<h1 align="center">
  DocsGPT  🦖
</h1>

<p align="center">
  <strong>Open-Source RAG Assistant</strong>
</p>

<p align="left">
  <strong><a href="https://www.docsgpt.cloud/">DocsGPT</a></strong> is an open-source genAI tool that helps users get reliable answers from any knowledge source, while avoiding hallucinations. It enables quick and reliable information retrieval, with tooling and agentic system capability built in.
</p>

<div align="center">

<a href="https://github.com/arc53/DocsGPT">![GitHub 主仓库星标数链接](https://img.shields.io/github/stars/arc53/docsgpt?style=social)</a>
  <a href="https://github.com/arc53/DocsGPT">![GitHub 主仓库分叉数链接](https://img.shields.io/github/forks/arc53/docsgpt?style=social)</a>
  <a href="https://github.com/arc53/DocsGPT/blob/main/LICENSE">![许可证文件链接](https://img.shields.io/github/license/arc53/docsgpt)</a>
  <a href="https://www.bestpractices.dev/projects/9907"><img src="https://www.bestpractices.dev/projects/9907/badge"></a>
  <a href="https://discord.gg/n5BX8dh8rU">![Discord 链接](https://img.shields.io/discord/1070046503302877216)</a>
  <a href="https://twitter.com/docsgptai">![X(原 Twitter) URL](https://img.shields.io/twitter/follow/docsgptai)</a>

<a href="https://docs.docsgpt.cloud/quickstart">⚡️ 快速开始</a> • <a href="https://app.docsgpt.cloud/">☁️ 云端版本</a> • <a href="https://discord.gg/n5BX8dh8rU">💬 Discord</a>
<br>
<a href="https://docs.docsgpt.cloud/">📖 文档</a> • <a href="https://github.com/arc53/DocsGPT/blob/main/CONTRIBUTING.md">👫 参与贡献</a> • <a href="https://blog.docsgpt.cloud/">🗞 博客</a>
<br>

</div>
<div align="center">
<img src="https://d3dg1063dc54p9.cloudfront.net/videos/demov7.gif" alt="video-example-of-docs-gpt" width="800" height="450">
</div>
<h3 align="left">
  <strong>Key Features:</strong>
</h3>
<ul align="left">
    <li><strong>🗂️ Wide Format Support:</strong> Reads PDF, DOCX, CSV, XLSX, EPUB, MD, RST, HTML, MDX, JSON, PPTX, and images.</li>
    <li><strong>🌐 Web & Data Integration:</strong> Ingests from URLs, sitemaps, Reddit, GitHub and web crawlers.</li>
    <li><strong>✅ Reliable Answers:</strong> Get accurate, hallucination-free responses with source citations viewable in a clean UI.</li>
    <li><strong>🔑 Streamlined API Keys:</strong>  Generate keys linked to your settings, documents, and models, simplifying chatbot and integration setup.</li>
    <li><strong>🔗 Actionable Tooling:</strong> Connect to APIs, tools, and other services to enable LLM actions.</li>
    <li><strong>🧩 Pre-built Integrations:</strong> Use readily available HTML/React chat widgets, search tools, Discord/Telegram bots, and more.</li>
    <li><strong>🔌 Flexible Deployment:</strong> Works with major LLMs (OpenAI, Google, Anthropic) and local models (Ollama, llama_cpp).</li>
    <li><strong>🏢 Secure & Scalable:</strong> Run privately and securely with Kubernetes support, designed for enterprise-grade reliability.</li>
</ul>

## 路线图

- [x] 完全兼容 GoogleAI（2025年1月）
- [x] 添加工具支持（2025年1月）
- [x] 应用界面手动更新数据块功能（2025年2月）
- [x] 开发容器简化开发流程（2025年2月）
- [x] ReACT 智能体（2025年3月）
- [x] 聊天机器人菜单重构，支持工具、智能体类型等功能（2025年4月）
- [x] 对话菜单新增输入框（2025年4月）
- [x] 添加可触发操作/工具（webhook）（2025年4月）
- [x] 智能体优化（2025年5月）
- [x] 文件系统数据源更新（2025年7月）
- [x] JSON 响应支持（2025年8月）
- [ ] SharePoint 集成（2025年8月）
- [ ] MCP 支持（2025年8月）
- [ ] 为工具和数据源添加 OAuth 2.0 认证（2025年8月）
- [ ] 智能体调度功能

完整路线图可在此处查看[here](https://github.com/orgs/arc53/projects/2)。欢迎贡献代码或提交问题，这将帮助我们改进 DocsGPT！

### 生产环境支持/企业协助：

我们乐意为您部署 DocsGPT 至生产环境提供个性化支持。

[预约演示 :wave:](https://www.docsgpt.cloud/contact)⁠

[发送邮件 :email:](mailto:support@docsgpt.cloud?subject=DocsGPT%20support%2Fsolutions)

## 加入灯塔计划 🌟

诚邀各位开发者与生成式AI创新者参与！**DocsGPT灯塔计划**专为正在实际场景中部署或扩展DocsGPT的技术领导者打造。您将直接与我们的团队协作，共同规划产品路线图，获取优先技术支持，并借助独家社区洞察构建企业级解决方案。

[了解详情并申请 →](https://docs.google.com/forms/d/1KAADiJinUJ8EMQyfTXUIGyFbqINNClNR3jBNWq7DgTE)

## 快速开始

> [!注意]
> 请确保已安装 [Docker](https://docs.docker.com/engine/install/)

更详细的[快速入门指南](https://docs.docsgpt.cloud/quickstart)可在文档中查阅

1. **克隆仓库：**

   ```bash
   git clone https://github.com/arc53/DocsGPT.git
   cd DocsGPT
   ```

**macOS与Linux用户：**

2. **运行安装脚本：**

   ```bash
   ./setup.sh
   ```

**Windows用户：**

2. **运行PowerShell安装脚本：**

   ```powershell
   PowerShell -ExecutionPolicy Bypass -File .\setup.ps1
   ```

任一脚本都将引导您完成DocsGPT的配置。提供四种选项：使用公共API、本地运行、连接本地推理引擎或使用云API提供商。脚本会根据您的选择自动配置`.env`文件，并处理必要的下载与安装。

**访问 http://localhost:5173/**

要停止 DocsGPT，请在 `DocsGPT` 目录中打开终端并运行：

```bash
docker compose -f deployment/docker-compose.yaml down
```

（或使用运行设置脚本后显示的特定 `docker compose down` 命令）。

> [!注意]
> 有关开发环境设置说明，请参阅[开发环境指南](https://docs.docsgpt.cloud/Deploying/Development-Environment)。

## 参与贡献

请参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 文件了解如何参与贡献。我们欢迎问题、疑问和拉取请求。

## 系统架构

![架构图](https://github.com/user-attachments/assets/fc6a7841-ddfc-45e6-b5a0-d05fe648cbe2)

## 项目结构

- 应用程序 - Flask 应用（主应用程序）。

- 扩展 - 扩展功能，如 react 小部件或 discord 机器人。

- 前端 - 前端使用 <a href="https://vitejs.dev/">Vite</a> 和 <a href="https://react.dev/">React</a>。

- 脚本 - 杂项脚本。

## 行为准则

我们作为成员、贡献者和领导者，承诺让每个人在参与社区时都能获得免受骚扰的体验，不论年龄、体型、可见或不可见的残疾、种族、性别特征、性别认同与表达、经验水平、教育程度、社会经济地位、国籍、外貌、种族、宗教或性取向。更多关于贡献的信息，请参阅 [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) 文件。

## 衷心感谢我们的贡献者⚡

<a href="https://github.com/arc53/DocsGPT/graphs/contributors" alt="View Contributors">
  <img src="https://contrib.rocks/image?repo=arc53/DocsGPT" alt="Contributors" />
</a>

## 许可协议

源代码采用 [MIT](https://opensource.org/license/mit/) 许可证，具体条款详见 [LICENSE](LICENSE) 文件。

<p>This project is supported by:</p>
<p>
  <a href="https://www.digitalocean.com/?utm_medium=opensource&utm_source=DocsGPT">
    <img src="https://opensource.nyc3.cdn.digitaloceanspaces.com/attribution/assets/SVG/DO_Logo_horizontal_blue.svg" width="201px">
  </a>
</p>