# 🛡️ Home Lab de Ciberseguridad — Blue Team / Respuesta a Incidentes

Laboratorio virtualizado para practicar detección, análisis y respuesta a incidentes
de seguridad, documentado paso a paso como referencia de aprendizaje y portfolio.

## 🎯 Objetivo

Construir un entorno controlado donde poder:
- Simular ataques comunes contra un servidor Linux (fuerza bruta, escaneo de puertos, etc.)
- Detectar esos ataques a través del análisis de logs y herramientas de monitoreo
- Documentar el proceso completo como lo haría un analista SOC / de respuesta a incidentes:
  detección → análisis → contención → lecciones aprendidas

## 🖥️ Topología actual

| Máquina | Rol | SO | Red |
|---|---|---|---|
| Kali Linux | Atacante / Red Team | Kali Linux | NatNetwork (VirtualBox) |
| Ubuntu Server | Objetivo / Blue Team | Ubuntu Server 24.04 LTS | NatNetwork (VirtualBox) |

Ambas VMs corren sobre Oracle VirtualBox, conectadas a la misma **Red NAT**
(`NatNetwork`, `10.0.2.0/24`) para poder verse entre sí y compartir salida a internet
para actualizaciones.

Ver diagrama detallado en [`docs/01-topologia-red.md`](docs/01-topologia-red.md).

## 🧰 Herramientas usadas

- **Oracle VirtualBox** — virtualización
- **Kali Linux** — herramientas ofensivas (hydra, nmap, etc.)
- **Ubuntu Server 24.04 LTS** — sistema objetivo
- *(se irán agregando: fail2ban, auditd, ufw, Wazuh/Suricata, etc.)*

## 📂 Estructura del repositorio

```
├── README.md                  # Este archivo
├── docs/                      # Informes y documentación de cada práctica
│   ├── 00-plantilla-informe.md
│   ├── 01-topologia-red.md
│   └── ...
└── evidence/                  # Capturas de pantalla y logs de cada ejercicio
```

## 📑 Índice de prácticas

| # | Práctica | Estado |
|---|---|---|
| 01 | Armado de la topología de red | ✅ |
| 02 | Hardening básico del servidor | ✅ |
| 03 | Configuración de logging y visibilidad | ✅ |
| 04 | Simulación de ataque de fuerza bruta SSH | 🔜 |
| 05 | Detección y contención con fail2ban | 🔜 |

Cada práctica tiene su propio informe dentro de `/docs`, siguiendo la
[plantilla estándar](docs/00-plantilla-informe.md).

## 👤 Sobre este proyecto

Este lab forma parte de mi proceso de aprendizaje autodidacta en ciberseguridad,
con foco en blue team / respuesta a incidentes. La documentación busca reflejar
el mismo criterio y estructura que se usaría en un entorno profesional real.
