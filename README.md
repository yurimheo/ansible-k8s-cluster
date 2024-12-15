## 설치 방법

### 1. 기본 초기 세팅 설치

Navigate to the `ansible` folder and execute the setup playbook
'ansible' 폴더로 이동하여 설정 플레이북 실행

```bash
cd ansible
ansible-playbook setup.yml
```

### 2. Deploy the Kubernetes Cluster

Navigate to the `k8s-cluster` folder and run the cluster deployment playbook
'k8s-cluster' 폴더로 이동하여 클러스터 배포 플레이북 실행

```bash
cd ../k8s-cluster
ansible-playbook -i inventory site.yml
```

### 3. Helm 설치 및 Nginx-ingress 설정

```bash
ansible-playbook -i inventory install-helm-ingress-nginx.yml
```


### 4. ArgoCD 설치하기

```bash
ansible-playbook -i inventory install_argocd.yml
```
