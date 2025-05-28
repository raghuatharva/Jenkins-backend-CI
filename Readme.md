

### ✅ `README.md` for Node.js Backend CI with Jenkins + SonarQube

````markdown
# 🚀 Node.js Backend - CI Pipeline with Jenkins & SonarQube

This project contains a Node.js backend service with an integrated CI pipeline using Jenkins, shared libraries, and SonarQube for code quality checks.

---

## 📦 Tech Stack

- Node.js (LTS)
- Jenkins (Declarative Pipeline)
- SonarQube (Code analysis)
- Docker
- npm for package management
- Jenkins Shared Library for CI stages

---

## ⚙️ CI Pipeline Overview

CI is triggered on every push or PR to the `main` or `develop` branch.

### ✅ Stages:

1. Checkout code  
2. Install dependencies (`npm install`)
3. Linting and Unit Tests  
4. SonarQube Analysis  
5. Build Docker Image  
6. Push Image to ECR (optional for CD)

---

## 🔐 Security & Quality

- All commits are scanned using SonarQube
- Sensitive info (keys, passwords) should be stored in Jenkins credentials or AWS Secrets Manager
- Follows OWASP Node.js best practices

---

## 🧪 Unit Testing

Tests are written using `jest`.  
To run tests locally:

```bash
npm install
npm run test
````
---

## 🧱 Shared Library Usage

The pipeline uses a shared library hosted in a separate repo (e.g. `jenkins-shared-lib`).

Structure of shared lib:

```
jenkins-shared-lib/
└── vars/
    ├── dockerBuild.groovy
    └── sonarScan.groovy
```

Use in Jenkins:

```groovy
@Library('jenkins-shared-lib@main') _
```

---

## 🌐 SonarQube Setup (CLI Alternative)

To run SonarQube scan locally:

```bash
npx sonar-scanner \
  -Dsonar.projectKey=node-backend \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=<SONAR_TOKEN>
```

---

## 📁 Project Structure

```
node-backend/
├── src/
├── test/
├── package.json
├── Jenkinsfile
└── README.md
```

---

## 📌 Best Practices

* Keep Jenkinsfile small — move reusable logic to shared libs.
* Always fail builds on lint/test/Sonar failures.
* Run pipelines in Docker agents to isolate builds.
* Scan PRs and branches separately using `sonar.branch.name`.

---

## 🧠 Questions?

Contact DevOps team or raise a ticket in `#devops-support`.

