# tester_server_demo — 实际项目（被测服务）

独立的 demo_server 项目，仅包含被测 API 服务及 K8s 部署配置。

## 结构

```
tester_server_demo/
├── Jenkinsfile       # 构建 → 推送 → 部署（不含冒烟测试）
├── demo_server/      # Flask API
├── k8s/              # K8s 清单
└── README.md
```

## 测试框架

冒烟测试位于独立仓库：<https://github.com/dreamerinsgp/api_auto_framework>  
CI/CD 中需多仓库 checkout，使用 `Jenkinsfile.multi-repo`，详见 `tester/documents/4.8.multi-repo-cicd-setup.md`。

## 本地构建

```bash
docker build -f demo_server/Dockerfile -t demo-server:test .
```
# tester_server_demo
