<div align="center">
<h1>🚀 Helm</h1>
<p><strong>Built with ❤️ by <a href="https://github.com/atulkamble">Atul Kamble</a></strong></p>

<p>
<a href="https://codespaces.new/atulkamble/template.git">
<img src="https://github.com/codespaces/badge.svg" alt="Open in GitHub Codespaces" />
</a>
<a href="https://vscode.dev/github/atulkamble/template">
<img src="https://img.shields.io/badge/Open%20with-VS%20Code-007ACC?logo=visualstudiocode&style=for-the-badge" alt="Open with VS Code" />
</a>
<a href="https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/atulkamble/template">
<img src="https://img.shields.io/badge/Dev%20Containers-Ready-blue?logo=docker&style=for-the-badge" />
</a>
<a href="https://desktop.github.com/">
<img src="https://img.shields.io/badge/GitHub-Desktop-6f42c1?logo=github&style=for-the-badge" />
</a>
</p>

<p>
<a href="https://github.com/atulkamble">
<img src="https://img.shields.io/badge/GitHub-atulkamble-181717?logo=github&style=flat-square" />
</a>
<a href="https://www.linkedin.com/in/atuljkamble/">
<img src="https://img.shields.io/badge/LinkedIn-atuljkamble-0A66C2?logo=linkedin&style=flat-square" />
</a>
<a href="https://x.com/atul_kamble">
<img src="https://img.shields.io/badge/X-@atul_kamble-000000?logo=x&style=flat-square" />
</a>
</p>

<strong>Version 1.0.0</strong> | <strong>Last Updated:</strong> January 2026
</div>

Here are **very basic Helm chart commands** 👇
Perfect for **beginners / first Helm session / AKS–EKS–GKE** 👍

---

## 🔹 Helm Basics (Verify & Help)

```bash
helm version
helm help
```

---

## 🔹 Add & Manage Helm Repositories

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo list
helm repo update
```

---

## 🔹 Search Charts

```bash
helm search repo nginx
helm search repo mysql
```

---

## 🔹 Create a New Helm Chart (Scaffold)

```bash
helm create mychart
```

📁 This creates:

```text
mychart/
 ├── Chart.yaml
 ├── values.yaml
 └── templates/
```

---

## 🔹 Install a Chart

### Install from repo

```bash
helm install my-nginx bitnami/nginx
```

### Install from local chart

```bash
helm install myapp ./mychart
```

---

## 🔹 List Installed Releases

```bash
helm list
helm list -A
```

---

## 🔹 Get Release Information

```bash
helm status myapp
helm get values myapp
helm get manifest myapp
```

---

## 🔹 Upgrade a Release

```bash
helm upgrade myapp ./mychart
```

With custom values:

```bash
helm upgrade myapp ./mychart -f values.yaml
```

---

## 🔹 Uninstall (Delete) Release

```bash
helm uninstall myapp
```

---

## 🔹 Dry Run & Debug (Very Important)

```bash
helm install myapp ./mychart --dry-run
helm install myapp ./mychart --debug
```

---

## 🔹 Template Rendering (Without Installing)

```bash
helm template myapp ./mychart
```

---

## 🔹 Values Override (One-line)

```bash
helm install myapp ./mychart --set image.tag=1.0
```

---

## 🔹 Check Chart Lint (Validate)

```bash
helm lint ./mychart
```

---

## 🔹 Namespace Usage

```bash
helm install myapp ./mychart -n dev --create-namespace
helm list -n dev
```

---

## 🔹 Helm Rollback (Production Safe)

```bash
helm history myapp
helm rollback myapp 1
```

---

## 🔹 Quick Helm Cheat Sheet (One View)

```bash
helm repo add
helm search repo
helm create
helm install
helm list
helm upgrade
helm uninstall
helm rollback
```

---
