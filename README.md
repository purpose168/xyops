# xyOps™

![xyOps 截图](https://pixlcore.com/images/blog/xyops/workflow-edit.webp)

xyOps™ 是下一代作业调度、工作流自动化、服务器监控、告警和事件响应系统——所有功能整合在一个统一的平台中。它专为希望掌控自动化栈的开发者和运维团队而设计，无需牺牲数据、自由或可见性。xyOps 不会将功能隐藏在付费墙后，也不会将遥测数据发送给任何人。它是开放的、可扩展的，并设计为可在任何地方运行。

## xyOps 的设计理念

大多数自动化平台专注于工作流编排——它们运行任务，但并不真正帮助您了解任务背后发生的事情。xyOps 走得更远。它不仅调度作业，还将作业与实时监控、告警、服务器快照和工单系统连接起来，创建一个单一的集成反馈循环。当告警触发时，邮件中会包含该服务器上正在运行的作业。点击一下即可打开快照，显示每个进程、CPU 负载和网络连接。如果作业失败，xyOps 可以创建包含完整上下文的工单——日志、历史记录和关联指标。xyOps 中的所有功能相互关联，因此您可以从问题检测到追踪解决，无需离开系统。

## 功能概览

- **为什么选择 xyOps？**
  - 在整个服务器集群中调度作业、跟踪性能、设置告警，并在一个地方实时查看所有内容。
- **重新定义的作业调度**
  - xyOps 为作业调度带来了超能力，远超 cron。
- **可视化构建工作流**
  - 使用图形化工作流编辑器，将事件、触发器、动作和监视器连接成有意义的管道。
- **监控一切**
  - 精确定义您要监控的内容，并在出现问题时立即收到通知。
- **智能告警**
  - 丰富的告警功能，支持完全自定义和复杂触发器。
- **为集群而建**
  - 无论您有 5 台服务器还是 5000 台，xyOps 都能适应您的需求。
- **开发者友好**
  - 专为开发者设计。是的，就是**您**！
- **简单设置**
  - 从下载到部署只需几分钟。
- **许可证**
  - xyOps 采用 BSD 许可证，具有最大的灵活性。

# 安装

请参阅我们的 **[自托管指南](https://github.com/pixlcore/xyops/blob/main/docs/hosting.md)** 了解安装详情。

只想在本地快速测试 xyOps？一行 Docker 命令：

```sh
# 运行 xyOps 容器，配置数据卷、Docker socket、时区和本地模式
docker run --detach --init --restart unless-stopped -v xy-data:/opt/xyops/data -v /var/run/docker.sock:/var/run/docker.sock -e TZ="America/Los_Angeles" -e XYOPS_xysat_local="true" -p 5522:5522 -p 5523:5523 --name "xyops01" --hostname "xyops01" ghcr.io/pixlcore/xyops:latest
```

然后在浏览器中打开 http://localhost:5522，使用用户名 `admin` 和密码 `admin` 登录。

## 即将推出

- 对于生产环境安装，我们强烈推荐我们的托管式 **[xyOps Cloud](https://xyops.io/pricing)** 服务（即将推出）。
- 对于大型企业，包括本地隔离网络（air-gapped）安装，请注册我们的 **[企业版计划](https://xyops.io/pricing)**（即将推出）。

# 文档

在此查看我们的文档：**[xyOps 文档索引](https://github.com/pixlcore/xyops/blob/main/docs/index.md)**

xyOps 应用内也提供完整的文档。只需点击侧边栏中的"文档"链接。

# 贡献

在提交拉取请求之前，请阅读我们的 **[贡献指南](https://github.com/pixlcore/xyops/blob/main/CONTRIBUTING.md)**。

简而言之，我们不接受功能 PR，但您可以通过**很多**其他方式做出贡献！详情请参阅指南。

# 开发

请参阅我们的 **[开发指南](https://github.com/pixlcore/xyops/blob/main/docs/dev.md)** 了解本地开发设置。简而言之，安装 [Node.js LTS](https://nodejs.org/en/download)，然后：

```sh
# 克隆 xyOps 仓库
git clone https://github.com/pixlcore/xyops.git
# 进入项目目录
cd xyops
# 安装依赖
npm install
# 构建开发版本
node bin/build.js dev
# 启动调试模式
bin/debug.sh
```

# 安全

请阅读我们的 **[安全指南](https://github.com/pixlcore/xyops/blob/main/docs/security.md)** 了解如何向 xyOps 团队报告安全漏洞。

请**不要**将漏洞作为 GitHub 问题提交！

# 治理

xyOps 项目通过开放性、可靠性和公平性来赋能用户和开发者。

我们的 **[治理模式](https://github.com/pixlcore/xyops/blob/main/docs/governance.md)** 旨在永久保护这些原则。

# 长期承诺

请阅读我们的开源 **[长期承诺书](https://github.com/pixlcore/xyops/blob/main/LONGEVITY.md)**。简而言之：

xyOps 将始终保持开源许可，并始终获得 OSI（开源促进会）批准。不会有突然撤回（rug pulls）。

# 许可证

xyOps™ 采用 **BSD-3-Clause** 许可证。

完整许可证文本请参阅 [LICENSE.md](https://github.com/pixlcore/xyops/blob/main/LICENSE.md)。
