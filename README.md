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

## 🎯 작업 배경

Kubernetes 클러스터를 구성할 때는 보통 Kubespray 같은 도구를 사용하는 경우가 많습니다.
자동화가 잘 되어 있어서 편리하지만, 오히려 내부 동작을 이해하거나 직접 수정하기에는 다소 어려움이 있었습니다.

이번 프로젝트는 팀원들이 함께 사용할 공통 인프라 환경이 필요했고,  
이를 효율적으로 구성하기 위해 자동화된 설치 스크립트가 필수적이었습니다.
마침 Ansible을 학원에서 학습하였기 때문에, 배운 것을 토대로 적용해서 직접 자동화 구조를 만들어보기로 했습니다.

Kubernetes 설치부터 Helm, Ingress, ArgoCD까지 필요한 구성 요소들을 하나씩 플레이북에 담았고,  
서버 초기화, 네트워크 설정, SSH 키 배포 등의 작업도 함께 자동화해  
모든 팀원이 동일한 환경에서 개발을 시작할 수 있도록 구성하였습니다.

결과적으로는 단순한 설치를 넘어서,  
인프라 전체를 코드로 구성하고 관리하는 과정을 직접 경험해볼 수 있었던 의미 있는 작업이었습니다.

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
