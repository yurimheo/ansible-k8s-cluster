## Setup Instructions

### 1. Initial Setup

Navigate to the `ansible` folder and execute the setup playbook:

```bash
cd ansible
ansible-playbook setup.yml

### 2. Deploy the Kubernetes Cluster
Navigate to the k8s-cluster folder and run the cluster deployment playbook:

```bash
cd ../k8s-cluster
ansible-playbook -i inventory site.yml
