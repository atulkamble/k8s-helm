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

Here’s a **clean, hands-on Helm basic practice guide** you can directly use for **training, labs, or interviews** 🚀
(Designed for Kubernetes beginners → DevOps practitioners)

---

## 🧭 What is Helm? (Quick Recall)

* Helm is a **package manager for Kubernetes**
* A **Helm Chart** = collection of Kubernetes YAML files
* Helps with **install, upgrade, rollback, versioning**

---

## 🧱 Helm Architecture (High Level)

![Image](https://miro.medium.com/1%2AdV7Kec1af1Y1W250Z9FtIA.jpeg)

![Image](https://www.simplyblock.io/wp-content/media/Helam-chart.png?ver=70d5e0ceb27be4033da21fe5e99f47d42c58b68d)

![Image](https://www.devopsschool.com/blog/wp-content/uploads/2023/06/helm-workflow-2-1024x632.png)

| Component      | Purpose                       |
| -------------- | ----------------------------- |
| Helm CLI       | Command-line tool             |
| Chart          | Application package           |
| Release        | Installed instance of a chart |
| Values         | Configuration input           |
| Kubernetes API | Actual deployment             |

---

## 🔹 Step 1: Install Helm

### Linux / macOS

```bash
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
```

### Verify

```bash
helm version
```

---

## 🔹 Step 2: Helm Repository Practice

### Add official repo

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```

### List repos

```bash
helm repo list
```

### Update repo

```bash
helm repo update
```

### Search charts

```bash
helm search repo nginx
```

---

## 🔹 Step 3: Install a Helm Chart (Hands-on)

### Install NGINX

```bash
helm install my-nginx bitnami/nginx
```

### Verify

```bash
helm list
kubectl get pods
kubectl get svc
```

---

## 🔹 Step 4: Helm Chart Lifecycle Commands

| Command          | Purpose                     |
| ---------------- | --------------------------- |
| `helm install`   | Install application         |
| `helm upgrade`   | Update release              |
| `helm rollback`  | Go back to previous version |
| `helm uninstall` | Remove release              |
| `helm list`      | View releases               |
| `helm history`   | Release versions            |

---

## 🔹 Step 5: Custom Values (Most Important Practice)

### View default values

```bash
helm show values bitnami/nginx
```

### Create `values.yaml`

```yaml
service:
  type: NodePort

replicaCount: 2
```

### Install using custom values

```bash
helm install my-nginx bitnami/nginx -f values.yaml
```

---

## 🔹 Step 6: Upgrade & Rollback Practice

### Upgrade

```bash
helm upgrade my-nginx bitnami/nginx -f values.yaml
```

### Check history

```bash
helm history my-nginx
```

### Rollback

```bash
helm rollback my-nginx 1
```

---

## 🔹 Step 7: Create Your Own Helm Chart (Must Practice)

### Create chart

```bash
helm create myapp
```

### Chart structure

```text
myapp/
├── Chart.yaml
├── values.yaml
├── templates/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── _helpers.tpl
```

---

## 🔹 Step 8: Install Your Custom Chart

```bash
helm install myapp-release ./myapp
```

Verify:

```bash
helm list
kubectl get all
```

---

## 🔹 Step 9: Template & Debug (Interview Favorite)

### Render YAML without deploying

```bash
helm template myapp ./myapp
```

### Dry run

```bash
helm install myapp ./myapp --dry-run --debug
```

---

## 🔹 Step 10: Helm Uninstall & Cleanup

```bash
helm uninstall my-nginx
helm uninstall myapp-release
```

---

## 🧠 Important Interview Points (Remember)

* Helm does **not replace kubectl**, it complements it
* Helm uses **Go templating**
* Values hierarchy:

  ```
  --set > values.yaml > chart defaults
  ```
* One chart → many environments (dev, test, prod)

---

## 🎯 Practice Mini-Labs (Try These)

1. Deploy NGINX with **3 replicas**
2. Change service to **LoadBalancer**
3. Rollback after a failed upgrade
4. Create chart for **Hello World app**
5. Use `--set image.tag=v2`

---

## 📌 When to Use Helm?

| Scenario      | Why Helm              |
| ------------- | --------------------- |
| Microservices | Easy version control  |
| CI/CD         | Automated deployments |
| Multi-env     | Reusable charts       |
| Rollbacks     | One-command recovery  |

---

## 1️⃣ Helm Introduction 

### What is Helm?

* Helm is the **package manager for Kubernetes**
* Helps you **define, install, upgrade, rollback, and manage Kubernetes applications**
* Uses **Helm Charts** (pre-configured Kubernetes resources)

### Why Helm is Needed?

* Kubernetes YAML files become **complex and repetitive**
* Managing versions, updates, and rollbacks manually is difficult
* Helm solves:

  * Reusability
  * Versioning
  * Configuration management
  * Easy upgrades & rollbacks

### Key Benefits

* 🚀 Faster application deployments
* 📦 Application packaging with charts
* 🔁 Rollback to previous versions easily
* ⚙️ Environment-specific configurations (dev, test, prod)
* 🔄 Simplifies CI/CD pipelines

### Helm Architecture

* **Helm Client** – CLI tool
* **Helm Charts** – Application packages
* **Release** – Deployed instance of a chart
* **Repository** – Storage for Helm charts

### Helm vs Plain Kubernetes YAML

| Kubernetes YAML    | Helm                  |
| ------------------ | --------------------- |
| Manual deployments | Automated deployments |
| No version control | Versioned releases    |
| Hard to rollback   | Easy rollback         |
| Repetition         | Templating & values   |

---

## 2️⃣ Helm Core Concepts

* **Chart** – Package of Kubernetes resources
* **Release** – Installed chart instance
* **Values** – Configuration input for charts
* **Templates** – Go-templated Kubernetes YAML
* **Repository** – Chart storage location

---

## 3️⃣ Helm Installation (Quick)

```bash
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
helm version
```

---

## 4️⃣ Helm Commands List (Must-Know)

### Helm Help & Version

```bash
helm help
helm version
```

### Helm Repository Commands

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo list
helm repo update
helm repo remove bitnami
```

### Helm Search

```bash
helm search repo nginx
helm search hub mysql
```

### Helm Chart Management

```bash
helm create mychart
helm lint mychart
helm package mychart
helm dependency update
```

### Helm Install / Upgrade / Delete

```bash
helm install myapp mychart
helm install myapp mychart -f values.yaml
helm upgrade myapp mychart
helm uninstall myapp
```

### Helm Release Management

```bash
helm list
helm list -A
helm status myapp
helm history myapp
helm rollback myapp 1
```

### Helm Debug & Dry Run

```bash
helm install myapp mychart --dry-run
helm template mychart
```

---

## 5️⃣ Helm Chart Directory Structure (Basic)

```text
mychart/
├── Chart.yaml
├── values.yaml
├── charts/
├── templates/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── _helpers.tpl
└── README.md
```

---

## 6️⃣ Basic Helm Kubernetes Project (Hands-on)

### 🎯 Project: Deploy NGINX using Helm

---

### Step 1: Create Helm Chart

```bash
helm create nginx-app
cd nginx-app
```

---

### Step 2: Update `values.yaml`

```yaml
replicaCount: 2

image:
  repository: nginx
  tag: latest

service:
  type: NodePort
  port: 80
```

---

### Step 3: Deployment Template (`templates/deployment.yaml`)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: {{ .Release.Name }}-nginx
spec:
  replicas: {{ .Values.replicaCount }}
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: "{{ .Values.image.repository }}:{{ .Values.image.tag }}"
          ports:
            - containerPort: 80
```

---

### Step 4: Service Template (`templates/service.yaml`)

```yaml
apiVersion: v1
kind: Service
metadata:
  name: {{ .Release.Name }}-service
spec:
  type: {{ .Values.service.type }}
  selector:
    app: nginx
  ports:
    - port: {{ .Values.service.port }}
      targetPort: 80
```

---

### Step 5: Install Helm Chart

```bash
helm install nginx-release .
```

---

### Step 6: Verify

```bash
helm list
kubectl get pods
kubectl get svc
```

---

## 7️⃣ Upgrade & Rollback Demo

### Upgrade

```bash
helm upgrade nginx-release . --set replicaCount=3
```

### Rollback

```bash
helm history nginx-release
helm rollback nginx-release 1
```

---

## 8️⃣ Helm with CI/CD (Talking Points)

* Used in **GitHub Actions**, **Azure DevOps**, **Jenkins**
* Helm values injected per environment
* Common pattern:

  * Build image → Push to registry → Helm upgrade

---

## 9️⃣ Common Helm Interview / Training Points

* Difference between **chart** and **release**
* Role of `values.yaml`
* How rollback works in Helm
* Helm vs Kustomize
* Helm templating basics (`{{ .Values }}`, `{{ .Release.Name }}`)

---

## 🔚 Summary

* Helm simplifies Kubernetes deployments
* Ideal for **production-grade workloads**
* Widely used in DevOps & Cloud projects
* Must-know skill for **Kubernetes, AKS, EKS, GKE**


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
