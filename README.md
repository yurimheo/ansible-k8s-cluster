# ⚙️ ansible-k8s-cluster

> Ansible을 사용해 Kubespray 없이 구성한 경량화 Kubernetes 클러스터 자동화 프로젝트입니다.

![Ansible](https://img.shields.io/badge/ansible-automation-blue)
![License](https://img.shields.io/github/license/yurimheo/ansible-k8s-cluster)
![Last Commit](https://img.shields.io/github/last-commit/yurimheo/ansible-k8s-cluster)

---

## 📦 구성 요소

- Kubernetes 클러스터 설치 (Kubeadm 기반)
- Helm + Ingress Nginx 설치
- ArgoCD 설치 및 초기 설정
- MetalLB + 외부 IP 설정
- Google DNS 및 네트워크 기본 설정
- SSH 키 자동화, 계정 생성, 네트워크 세팅 등 서버 초기화 작업

---

## 🛠️ 사용 기술

| 분류 | 기술 |
|------|------|
| Language | YAML (Ansible Playbook) |
| Infra | Kubernetes, Helm, ArgoCD, MetalLB |
| Tooling | Ansible, SSH, Ubuntu Server |
| 구조 | 역할 기반 디렉토리(`roles/`) + 환경 분리(`inventory/`) |

---

<details>
<summary>🧾 설치 방법 보기</summary>

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

