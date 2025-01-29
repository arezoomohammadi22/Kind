# KIND (Kubernetes IN Docker)

[KIND](https://kind.sigs.k8s.io/) is a tool for running Kubernetes clusters locally using Docker containers instead of virtual machines. It is designed for testing and development purposes.

## 📌 Prerequisites
Before installing KIND, ensure you have the following installed on your system:
- [Docker](https://docs.docker.com/get-docker/) (Required)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) (Optional, but recommended)

## 🚀 Installation

### **Linux**
```bash
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/
```

### **macOS (Intel & Apple Silicon)**
```bash
brew install kind
```

### **Windows (via Chocolatey)**
```powershell
choco install kind
```

### **Windows (via Scoop)**
```powershell
scoop install kind
```

## 🎯 Verify Installation
After installing, verify that KIND is installed correctly by running:
```bash
kind version
```
You should see an output like:
```
kind v0.20.0
```

## 🔥 Creating a Kubernetes Cluster
To create a local Kubernetes cluster, simply run:
```bash
kind create cluster --name my-cluster
```
This will spin up a Kubernetes cluster inside a Docker container.

## 🔍 Listing Clusters
```bash
kind get clusters
```

## ❌ Deleting a Cluster
```bash
kind delete cluster --name my-cluster
```

## 📄 Useful Commands
| Command | Description |
|---------|-------------|
| `kind create cluster` | Creates a Kubernetes cluster |
| `kind get clusters` | Lists available clusters |
| `kind delete cluster` | Deletes a cluster |
| `kubectl cluster-info --context kind-my-cluster` | Shows cluster info |

## 🛠 Advanced Configuration
To customize the cluster, you can use a configuration file.
Example:
```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
  - role: control-plane
  - role: worker
  - role: worker
```
Create a cluster with:
```bash
kind create cluster --config kind-config.yaml
```

## 🏁 Conclusion
KIND is a powerful and lightweight tool for running Kubernetes clusters locally. It is ideal for testing and CI/CD workflows.

For more details, visit the [official documentation](https://kind.sigs.k8s.io/). 🚀
