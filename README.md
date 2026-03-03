# Taller Servidores Linux 2026  
Infraestructura mínima reproducible con Ansible

## 🎯 Objetivo

Construcción de una infraestructura automatizada y reproducible utilizando Ansible, que integra:

- Servidor NFS en CentOS Stream 9
- Cliente Ubuntu 24.04 con automount (autofs)
- Servicio systemd que publica el directorio NFS mediante python3 http.server
- Versionado en GitHub

---

## 🧱 Arquitectura

| Nodo    | Sistema Operativo     | IP              | Rol |
|----------|----------------------|-----------------|------|
| nfs01   | CentOS Stream 9      | 192.168.10.10   | Servidor NFS |
| app01   | Ubuntu 24.04         | 192.168.10.12   | Cliente NFS + HTTP |
| bastion | Linux                | 192.168.10.11   | Nodo de control Ansible |

Red del laboratorio: 192.168.10.0/24

---

## ⚙️ Requisitos previos

- Ansible instalado en bastion
- Acceso SSH a los nodos
- Usuario con privilegios sudo sin password
- Conectividad entre nodos

---

## 🚀 Ejecución

Desde bastion:

```bash
ansible-playbook -i inventory/hosts.ini site.yml
