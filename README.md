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

![Image](https://helm.sh/img/helm.svg)

![Image](https://devopscube.com/content/images/2025/03/helm-chart-drawio-1.png)

![Image](https://miro.medium.com/1%2A7P1QVEv8kxIlvalCvx_jkQ.png)

![Image](https://glasskube.dev/assets/images/helm-workflow-diagram-73ec11046f99e2e990ce3cabc5b6105c.png)

## What is **Helm**? ⛵

**Helm** is a **package manager for Kubernetes**.
Just like:

* **APT** for Ubuntu
* **YUM** for RHEL
* **npm** for Node.js

👉 **Helm manages Kubernetes applications** using reusable packages called **Helm Charts**.

---

## Why Helm is Needed (Problem It Solves)

Without Helm, deploying an app in **Kubernetes** means managing **many YAML files**:

* Deployment
* Service
* ConfigMap
* Secret
* Ingress
* HPA

This becomes **hard to manage, version, upgrade, and rollback**.

👉 **Helm simplifies this** by bundling everything into **one chart**.

---

## Key Concepts in Helm

### 1️⃣ Helm Chart

A **Helm Chart** is a package that contains:

* Kubernetes YAML templates
* Default configuration values
* Metadata

Think of it as:

> **A reusable Kubernetes application package**

---

### 2️⃣ Release

A **Release** is:

* A **running instance of a Helm chart** in a Kubernetes cluster

Example:

```bash
helm install myapp nginx
```

* `nginx` → chart
* `myapp` → release name

---

### 3️⃣ Values

Helm uses a file called `values.yaml` to customize deployments.

Example:

```yaml
replicaCount: 3
image:
  repository: nginx
  tag: 1.25
```

You can override values during install:

```bash
helm install myapp nginx --set replicaCount=5
```

---

### 4️⃣ Templates

Helm charts use **Go templating** to generate Kubernetes YAML.

Example:

```yaml
replicas: {{ .Values.replicaCount }}
```

This allows **dynamic and reusable YAML**.

---

## Helm Architecture

![Image](https://cdn.hashnode.com/res/hashnode/image/upload/v1707833110987/2162228d-44a9-49e1-a7b2-79d499eff59e.png)

![Image](https://developers.redhat.com/sites/default/files/2022_HelmJKube_graphic.png)

![Image](https://craftech.io/wp-content/uploads/2021/07/Help-blog.png)

* **Helm CLI** runs on your machine
* Talks directly to **Kubernetes API Server**
* Stores release metadata inside the cluster (Secrets/ConfigMaps)

---

## What Helm Can Do

| Feature          | Benefit                          |
| ---------------- | -------------------------------- |
| Install apps     | One command deployment           |
| Upgrade apps     | Zero-downtime updates            |
| Rollback         | Go back to previous version      |
| Version control  | Track application history        |
| Reusability      | Same chart across dev/stage/prod |
| Parameterization | Environment-specific configs     |

---

## Example: Without Helm vs With Helm

### ❌ Without Helm

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f configmap.yaml
kubectl apply -f ingress.yaml
```

### ✅ With Helm

```bash
helm install myapp ./mychart
```

---

## Real-World Usage Examples

* Deploy **NGINX**, **MySQL**, **Redis**
* Install **Prometheus + Grafana**
* Package **microservices**
* Manage **production-grade Kubernetes apps**

Popular charts:

* `nginx`
* `mysql`
* `redis`
* `prometheus`
* `grafana`

---

## When to Use Helm

✅ Use Helm when:

* App has **multiple Kubernetes resources**
* You need **upgrade & rollback**
* You manage **multiple environments**
* You want **standardization**

❌ Avoid Helm if:

* Very small one-pod YAML
* Learning Kubernetes basics only

---

## One-Line Definition (Interview Ready)

> **Helm is a Kubernetes package manager that simplifies application deployment, configuration, upgrades, and rollback using reusable charts.**

---

**very basic Helm chart commands** 👇
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
