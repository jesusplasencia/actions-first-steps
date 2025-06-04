# Hello Actions First Steps

> 🚀 Your first mission into the world of **GitHub Actions** begins here.

![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-CI/CD-blue?style=for-the-badge&logo=githubactions&logoColor=white)
![Status](https://img.shields.io/badge/status-WORKING-IN--PROGRESS-yellow?style=for-the-badge)
![Built With](https://img.shields.io/badge/Built%20With-NestJS-blueviolet?style=for-the-badge&logo=nestjs)

---

## 📚 About This Repository

This repo is a hands-on workshop for mastering **GitHub Actions**.  
I’ll be covering the core components and building real-world CI/CD pipelines.

> “**Build it. Break it. Automate it.**” — _Jesus_

---

## 🧩 Topics Covered

| ✅ Task | Description |
|-------|-------------|
| 🛠️ Workflows | Create and trigger workflows from push/pull events |
| ⏱️ Triggers | `on.push`, `on.pull_request`, `workflow_dispatch` |
| ⚙️ Jobs & Steps | Run multiple jobs with dependencies and conditions |
| 🧪 Test & Coverage | Run tests and upload code coverage artifacts |
| 📦 Artifacts | Save logs, coverage reports, and build outputs |
| 🧰 Matrix Builds | (Coming soon) Test across Node versions |

---

## 🧪 Sample Workflows

### ✅ Test + Coverage Workflow

```yaml
name: Test and Coverage
on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 18
      - run: npm ci
      - run: npm run test:cov
      - uses: actions/upload-artifact@v4
        with:
          name: coverage-report
          path: coverage/
