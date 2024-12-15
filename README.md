## 설치 방법

### 1. 기본 초기 세팅 설치
'ansible' 폴더로 이동하여 설정 플레이북 실행

```bash
cd ansible
ansible-playbook setup.yml
```

### 2. Deploy the Kubernetes Cluster
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
