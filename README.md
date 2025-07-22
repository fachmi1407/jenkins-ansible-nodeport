# 🚀 Jenkins Kubernetes Deploy via Ansible (NodePort)

## ✅ Struktur
- `inventory`: daftar master dan node2
- `jenkins-full-deploy.yaml`: playbook utama
- `files/`: semua manifest YAML template

## 🧪 Cara Jalankan

1. Pastikan public key SSH kamu sudah terpasang di node master & node2 (`quadrant`)
2. Jalankan playbook:
```bash
ansible-playbook -i inventory jenkins-full-deploy.yaml --ask-become-pass
```

## 🌐 Akses Jenkins
Setelah selesai, akses Jenkins di:

```
http://<IP-node2>:30080
```

Contoh:
```
http://192.168.50.22:30080
```

Dapatkan initial admin password:

```bash
kubectl exec -n jenkins deploy/jenkins -- cat /var/jenkins_home/secrets/initialAdminPassword
```
