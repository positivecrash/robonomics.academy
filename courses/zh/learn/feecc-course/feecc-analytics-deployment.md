---
title: "分析部署"
description: 本课程主要介绍Feecc系统及其所有组件。
metaOptions: [学习，熟悉Feecc]
defaultName: Getting Used to Feecc
---

<RoboAcademyText fWeight="500">
在本课程中，您将学习如何部署Feecc分析组件。
</RoboAcademyText>

## 启动分析后端

1. 克隆存储库：

<LessonCodeWrapper language="bash" codeClass="big-code">
git clone https://github.com/Multi-Agent-io/feecc-analytics-backend.git
</LessonCodeWrapper>

2. 使用`.env`文件为您的需求配置后端服务：
    - `MONGO_CONNECTION_URL` — MongoDB的连接URI；
    - `MONGO_DATABASE_NAME` — MongoDB的数据库名称；
    - `SECRET_KEY` — 用于哈希和反哈希的密钥；
    - `IPFS_GATEWAY_HOST` — IPFS网关的URL；
    - `USE_DATALOG` — 将分析数据发送到Robonomics（`true`或`false`）；
    - `ROBONOMICS_SEED` — Robonomics账户的种子短语。

3. 启动后端容器：

<LessonCodeWrapper language="bash">
sudo docker-compose up -d --build
</LessonCodeWrapper>

4. 检查其功能。转到浏览器并打开`http://localhost:5002/docs`页面。如果操作正确，您将看到一个页面（由Swagger生成），其中包含所有Feecc分析REST API端点。现在您已经准备好启动前端。

## 启动分析前端

1. 克隆存储库：

<LessonCodeWrapper language="bash" codeClass="big-code">
git clone https://github.com/Multi-Agent-io/feecc-analytics-frontend.git
</LessonCodeWrapper>

2. 转到`src`并使用`config.json`文件为您的需求配置前端服务。确保在`base_url`参数中输入Feecc分析后端的URL（格式为`xx.xx.xx.xx:port`）。

3. 启动前端容器：

<LessonCodeWrapper language="bash">
sudo docker-compose up -d --build
</LessonCodeWrapper>

4. 检查其功能。转到浏览器并打开`http://localhost:8081/docs`页面。

<RoboAcademyText fWeight="500">
通过这个，对Feecc系统的了解可以被认为是完整的。如果您有任何额外的问题，可以联系Multi-Agent Systems的开发人员（multi-agent.io）或在他们的GitHub上留下问题（github.com/Multi-Agent-io）。
</RoboAcademyText>