# ⚡ Agent CyberSec

<div align="center">

![CyberSec Agent Banner](https://img.shields.io/badge/CyberSec-Agent-00e5ff?style=for-the-badge&logo=hackthebox&logoColor=white)
![Version](https://img.shields.io/badge/version-2.0-ff3c3c?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-39ff14?style=for-the-badge)
![Claude](https://img.shields.io/badge/Powered_by-Claude_AI-blueviolet?style=for-the-badge&logo=anthropic)

**Agente de IA especializado en ciberseguridad ofensiva para entornos educativos y CTFs**

[Ver Demo](#demo) · [Instalación](#instalación) · [Prompts Disponibles](#prompts-disponibles) · [Uso](#uso)

</div>

---

## 📌 ¿Qué es Agent CyberSec ?

Agent CyberSec es una herramienta de asistencia técnica impulsada por la API de Claude, diseñada para guiar a estudiantes y profesionales de ciberseguridad en la resolución de máquinas CTF y entornos de laboratorio controlados.

Incluye una biblioteca de **20+ prompts especializados** organizados por categoría (reconocimiento, explotación web, Active Directory, escalada de privilegios y más), junto con un chat integrado con un modelo de IA configurado específicamente para el contexto de pentesting ético.

> ⚠️ **Uso ético:** Esta herramienta está diseñada exclusivamente para entornos autorizados como HackTheBox, TryHackMe, Dockerlabs, VulnHub o laboratorios propios. No uses estas técnicas en sistemas sin autorización explícita.

---

## ✨ Características

- 🗂️ **Biblioteca de prompts** organizada por categorías de pentesting
- 🤖 **Chat con IA** especializado en ciberseguridad (Claude API)
- 📋 **Copy al portapapeles** de cualquier prompt con un clic
- 💡 **Tips contextuales** por cada prompt para maximizar resultados
- 🎨 **Interfaz hacker-themed** con estética terminal/cyberpunk
- 📄 **100% client-side** — un solo archivo HTML, sin dependencias ni servidor
- 🌐 **En español** — prompts y respuestas en español

---

## 🗂️ Prompts Disponibles

### 🔵 Reconocimiento
| Prompt | Descripción |
|---|---|
| Nmap Full Scan | Escaneo completo con interpretación de resultados |
| Enumeración Web | Directorios, subdominios, tecnologías y parámetros |
| DNS Enumeration | Zone transfers, subdomain enum, takeover |
| OSINT Target | Reconocimiento pasivo con herramientas públicas |

### 🔴 Explotación Web
| Prompt | Descripción |
|---|---|
| SQL Injection | Detección, extracción manual y SQLMap |
| XSS Hunting | Reflected, Stored, DOM-based y bypass de filtros |
| SSRF Bypass | Enumeración interna, metadata cloud, gopher |
| LFI / Path Traversal | Log poisoning, PHP wrappers, escalada a RCE |
| SSTI Detection | Fingerprint de motor y payloads de RCE |

### 🟠 Active Directory
| Prompt | Descripción |
|---|---|
| Kerberoasting | Extracción de TGS y cracking offline |
| AS-REP Roasting | Ataque a cuentas sin pre-autenticación |
| BloodHound AD | Recolección, queries Cypher y análisis de rutas |
| Pass-the-Hash | Movimiento lateral con hashes NTLM |

### 🟢 Escalada de Privilegios
| Prompt | Descripción |
|---|---|
| Linux PrivEsc | LinPEAS, sudo, cron, capabilities, kernel |
| Windows PrivEsc | Tokens, servicios, registry, WinPEAS |
| SUID Abuse | GTFOBins, shared library hijacking |

### 🔵 CTF & Aprendizaje
| Prompt | Descripción |
|---|---|
| Resolver Máquina HTB | Guía paso a paso adaptada a tu progreso |
| Generar Writeup | Writeup técnico y educativo automático |
| Pistas Progresivas | Sistema de hints sin spoilers directos |

### 🟡 Herramientas
| Prompt | Descripción |
|---|---|
| Metasploit Framework | Módulos, payloads y post-explotación |
| Burp Suite Workflow | Proxy, Intruder, Repeater y extensiones |
| Shell Upgrade | Estabilización de reverse shells |

---

## 🚀 Instalación

No requiere instalación. Es un único archivo HTML.

### Opción 1 — Descarga directa

```bash
# Clona el repositorio
git clone https://github.com/CipherWall-Mz/agent-cybersec.git
cd agent-cybersec

# Abre el archivo en tu navegador
open agent-cybersec.html        # macOS
xdg-open agent-cybersec.html   # Linux
start agent-cybersec.html      # Windows
```

### Opción 2 — GitHub Pages

Haz fork del repositorio y activa GitHub Pages apuntando al archivo `agent-cybersec.html` en la rama `main`.

---

## ⚙️ Configuración

El agente usa la **API de Anthropic (Claude)**. Para habilitar el chat:

1. Obtén tu API key en [console.anthropic.com](https://console.anthropic.com)
2. El archivo HTML está configurado para recibir la key a través del mecanismo estándar de la API de Anthropic en claude.ai

> 💡 Si lo corres desde claude.ai como artifact, la autenticación es automática. Si lo despliegas por tu cuenta, necesitas un backend proxy para no exponer tu API key en el frontend.

---

## 🖥️ Uso

### Flujo básico

```
1. Selecciona un prompt en el panel izquierdo
2. Lee la descripción y tips contextuales
3. Copia el template con [ COPIAR ] o cárgalo directamente con ▶ USAR ESTE PROMPT
4. Rellena los campos [EN_CORCHETES] con tu información concreta
5. Envía y recibe guía técnica especializada
```

### Ejemplo de uso — Kerberoasting

```
Seleccionar: Active Directory → Kerberoasting
Rellenar:
  - [DOMAIN.LOCAL] → corp.empresa.local
  - [IP_DEL_DC]    → 10.10.10.1
  - Herramientas   → Impacket
Enviar → El agente te guía paso a paso desde enumeración de SPNs hasta cracking con hashcat
```

### Chat libre

También puedes escribir directamente en el chat sin usar templates:

```
"Encontré un puerto 8080 con Jenkins. ¿Cómo lo ataco?"
"Tengo SeImpersonatePrivilege en Windows. ¿Qué exploit uso?"
"Explícame cómo funciona DCSync y qué requiere"
```

---

## 🧱 Stack técnico

```
Frontend     → HTML5 + CSS3 + Vanilla JavaScript
Fuentes      → Share Tech Mono + Rajdhani (Google Fonts)
IA Backend   → Anthropic Claude API (claude-sonnet)
Dependencias → Ninguna (zero dependencies)
Tamaño       → ~1 archivo HTML (~25KB)
```

---

## 📁 Estructura del proyecto

```
angent-cybersec/
├── agent-cybersec.html    # Aplicación completa (single file)
└── README.md              # Este archivo
```

---

## 🤝 Contribuir

¿Tienes prompts de ciberseguridad que añadir? Pull requests bienvenidos.

1. Fork del repositorio
2. Crea tu rama: `git checkout -b feat/nuevo-prompt`
3. Añade el prompt en el objeto `PROMPTS` del JS siguiendo la estructura existente
4. Commit: `git commit -m 'feat: añadir prompt para [TÉCNICA]'`
5. Push y abre un Pull Request

### Estructura de un prompt

```javascript
nombre_prompt: {
  title: "Título del Prompt",
  tags: [['ETIQUETA', 'red|cyan|green|yellow']],
  desc: "Descripción breve de lo que hace el prompt.",
  text: `Contenido del prompt con campos [A_RELLENAR]...`,
  tips: [
    ['NOMBRE_TIP', 'Descripción del tip de uso'],
  ]
}
```

---

## ⚖️ Disclaimer

Este proyecto es exclusivamente para fines **educativos y de investigación en seguridad**. El autor no se hace responsable del uso indebido de las técnicas descritas. Úsalo únicamente en:

- Plataformas CTF: HackTheBox, TryHackMe, Dockerlabs, VulnHub, Vulnyx
- Laboratorios propios y máquinas virtuales controladas
- Entornos con autorización expresa por escrito

El uso de estas técnicas contra sistemas sin autorización es **ilegal** en la mayoría de jurisdicciones.

---

## 📄 Licencia

MIT License — libre para usar, modificar y distribuir con atribución al creador.
- Autor: Cipherwallmz
---

<div align="center">

Hecho para la comunidad de hacking ético 🔐

</div>
