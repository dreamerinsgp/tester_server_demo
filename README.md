# tester_server_demo — 实际项目（被测服务）

独立的 demo_server 项目，仅包含被测 API 服务及 K8s 部署配置。

## 结构

```
tester_server_demo/
├── .github/workflows/
│   └── demo-server-test.yaml   # GHA: tag 触发 → 构建推送 → Webhook Jenkins
├── Jenkinsfile                 # 构建 → 推送 → 部署（不含冒烟测试）
├── Jenkinsfile.gha             # GHA 模式：接收 DOCKER_TAG → 部署 → Smoke Test
├── demo_server/                # Flask API
├── k8s/                        # K8s 清单
└── README.md
```

## 测试框架

冒烟测试位于独立仓库：<https://github.com/dreamerinsgp/api_auto_framework>  
CI/CD 中需多仓库 checkout，使用 `Jenkinsfile.multi-repo` 或 `Jenkinsfile.gha`，详见：
- `tester/documents/4.8.multi-repo-cicd-setup.md`（多仓库 Checkout）
- `tester/documents/4.12.gha-jenkins-workflow-setup.md`（GHA + Jenkins 流程）

## 本地构建

```bash
docker build -f demo_server/Dockerfile -t demo-server:test .
```
# tester_server_demo
