# nestedproxmox-lab
 Virtual infraestructure environment based on nested virtualization using Proxmox VE, designed for system administration, networking, database and monitoring practice. 

# Infraestructura VPS con virtualización anidada

Proyecto de infraestructura completa desarrollado como portfolio técnico para el ciclo ASIR (Administración de Sistemas Informáticos en Red).

# Descripción
Este proyecto despliega una infraestructura VPS funcional sobre virtualización anidada, simulando un entorno de producción real. La arquitectura incluye servidores de bases de datos (PostgreSQL y MongoDB), servidor web (Nginx), panel de administración (Adminer), y un stack de monitorización completo (Prometheus + Grafana).
El objetivo es demostrar competencias en:

Virtualización con Proxmox VE (nested virtualization)
Administración de sistemas Linux (Debian/Ubuntu)
Gestión de bases de datos relacionales y NoSQL
Configuración de servidores web y proxies inversos
Monitorización de infraestructura con métricas y dashboards
Automatización mediante scripts Bash y configuraciones reproducibles
Conceptos de redes y seguridad (VLANs, firewall, SSH hardening)

# Inicio Rápido
Prerrequisitos

PC con al menos 16 GB RAM y CPU con soporte VT-x/AMD-V
VirtualBox 7.x o VMware Workstation Pro instalado
ISO de Proxmox VE 8.x (descarga oficial)
Conexión a Internet

# Pasos de despliegue
bash# 1. Clonar el repositorio
git clone https://github.com/TU_USUARIO/minicloud-asir.git
cd minicloud-asir

# 2. Seguir la guía de instalación de Proxmox
# Ver: docs/arquitectura/01-proxmox-nested.md

# 3. En cada VM, ejecutar el script de configuración base
sudo bash scripts/setup/base-config.sh

# 4. Configurar la VM de bases de datos
sudo bash scripts/bbdd/setup-postgresql.sh
sudo bash scripts/bbdd/setup-mongodb.sh

# 5. Configurar el servidor web
sudo bash scripts/setup/setup-nginx.sh

# 6. Levantar el stack de monitorización
sudo bash scripts/monitoring/setup-monitoring.sh

# Estructura del Repositorio
minicloud-asir/
├── README.md                          # Este archivo
├── docs/
│   ├── arquitectura/
│   │   ├── 01-proxmox-nested.md       # Instalación Proxmox en nested virt.
│   │   ├── 02-network-design.md       # Diseño de red y VLANs
│   │   └── 03-vm-creation.md          # Creación y configuración de VMs
│   ├── bbdd/
│   │   ├── 01-postgresql.md           # Instalación y administración PostgreSQL
│   │   └── 02-mongodb.md              # Instalación y administración MongoDB
│   ├── redes/
│   │   └── 01-firewall-ssh.md         # Hardening SSH y reglas de firewall
│   └── monitorizacion/
│       └── 01-prometheus-grafana.md   # Stack de monitorización
├── scripts/
│   ├── setup/
│   │   ├── base-config.sh             # Configuración base de cualquier VM
│   │   └── setup-nginx.sh             # Nginx + Adminer
│   ├── bbdd/
│   │   ├── setup-postgresql.sh        # Instalación automatizada PostgreSQL
│   │   ├── setup-mongodb.sh           # Instalación automatizada MongoDB
│   │   └── backup-bbdd.sh             # Script de backups automáticos
│   └── monitoring/
│       └── setup-monitoring.sh        # Prometheus + Grafana + exporters
├── configs/
│   ├── nginx/
│   │   └── default.conf               # Configuración Nginx + proxy inverso
│   ├── postgresql/
│   │   └── pg_hba.conf                # Control de acceso PostgreSQL
│   ├── mongodb/
│   │   └── mongod.conf                # Configuración MongoDB
│   └── prometheus/
│       └── prometheus.yml             # Targets de scraping
└── .github/
    └── workflows/
        └── lint.yml                   # Validación de scripts en CI

# Documentación
La documentación completa está en la carpeta /docs. Se recomienda seguir el orden:

Instalación de Proxmox en virtualización anidada
Diseño de red
Creación de VMs
PostgreSQL
MongoDB
Firewall y SSH Hardening
Monitorización


# Tecnologías Utilizadas
CategoríaTecnologíaVersiónHipervisor L1VirtualBox / VMware7.xHipervisor L2Proxmox VE8.xOS GuestsDebian GNU/Linux12 (Bookworm)BD RelacionalPostgreSQL16BD NoSQLMongoDB7.xServidor WebNginx1.24Panel Admin BDAdminer4.xMétricasPrometheus2.xDashboardsGrafana10.xAutomatizaciónBash-

# Autora
Proyecto desarrollado como portfolio técnico para prácticas ASIR.

Formación: Ingeniería Informática (2 años) + CFGS ASIR
Enfoque: Administración de sistemas, redes y virtualización
