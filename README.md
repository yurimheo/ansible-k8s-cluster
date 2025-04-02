<h1 align="center">⚙️ ansible-k8s-cluster</h1>

<p align="center">
  Kubespray 없이 Ansible만으로 Kubernetes 클러스터를 구축하는 자동화 프로젝트입니다.<br/>
  Helm, Ingress, ArgoCD, MetalLB까지 온프레미스 환경을 코드로 완벽 구성합니다.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/ansible-automation-blue?style=flat-square"/>
  <img src="https://img.shields.io/github/license/yurimheo/ansible-k8s-cluster?style=flat-square"/>
  <img src="https://img.shields.io/github/last-commit/yurimheo/ansible-k8s-cluster?style=flat-square"/>
</p>

---

## 🚀 소개

이 프로젝트는 Kubespray와 같은 외부 도구 없이, Ansible만으로 Kubernetes 클러스터를 설치하고  
운영 도구(Helm, Ingress, ArgoCD, MetalLB)를 함께 자동화하는 인프라 구성 템플릿입니다.

---

## 🧰 주요 구성 요소

- ✅ Kubeadm 기반 Kubernetes 설치
- ✅ Helm + Ingress Nginx 설치
- ✅ ArgoCD GitOps 배포 환경 구성
- ✅ MetalLB 외부 IP LoadBalancer 설정
- ✅ SSH 키 자동화, DNS 설정, 네트워크 구성
- ✅ 서버 초기화 및 반복 작업 자동화

---

## 📦 사용 기술 스택

| 기술 | 설명 |
|------|------|
| ![Ansible](https://img.shields.io/badge/-Ansible-E0503A?logo=ansible&logoColor=white) | 서버 초기 설정, Kubernetes 설치, Helm, ArgoCD 등 자동화 |
| ![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?logo=kubernetes&logoColor=white) | kubeadm을 통한 클러스터 설치 및 구성 대상 |
| ![Helm](https://img.shields.io/badge/-Helm-0F1689?logo=helm&logoColor=white) | Ingress Nginx 설치 및 K8s 리소스 배포 자동화 |
| ![ArgoCD](https://img.shields.io/badge/-ArgoCD-FE7B72?logo=argo&logoColor=white) | GitOps 기반 배포 도구, Ansible로 설치 |
| ![Nginx](https://img.shields.io/badge/-Nginx-009639?logo=nginx&logoColor=white) | Ingress Controller 및 Reverse Proxy로 구성 |
| ![Ubuntu](https://img.shields.io/badge/-Ubuntu-E95420?logo=ubuntu&logoColor=white) | 대상 서버 OS, 패키지 설치 및 네트워크 설정 |
| ![YAML](https://img.shields.io/badge/-YAML-CCCCCC?logo=yaml&logoColor=black) | 모든 Playbook 및 인프라 설정 작성 포맷 |
| ![SSH](https://img.shields.io/badge/-SSH-000000?logo=openssh&logoColor=white) | 원격 접속 및 키 기반 인증 자동화 |


---

<details>
<summary>🛠️ 설치 방법 (클릭해서 열기)</summary>

```bash
# 1. 초기 서버 설정
cd ansible
ansible-playbook setup.yml

# 2. Kubernetes 클러스터 설치
cd ../k8s-cluster
ansible-playbook -i inventory site.yml

# 3. Helm + Ingress Nginx 설치
ansible-playbook -i inventory install-helm-ingress-nginx.yml

# 4. ArgoCD 설치
ansible-playbook -i inventory install_argocd.yml
</details>
