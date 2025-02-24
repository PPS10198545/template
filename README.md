# 🚀 Seguridad en Apache - RA3

Este repositorio contiene una serie de prácticas enfocadas en la **seguridad en servidores Apache**, incluyendo la implementación de **Content Security Policy (CSP)**, **Web Application Firewall (WAF)**, **Reglas OWASP para ModSecurity**, y **protección contra ataques DDoS**.

Todas las pruebas pueden ser ejecutadas en vivo en: 🔗 [**https://dev.tonihack.es/**](https://dev.tonihack.es/)

## 📂 Estructura del Repositorio

```
.
├── RA3
│   ├── RA3_1   # Práctica 1 - Content Security Policy (CSP)
│   │   ├── assets
│   │   ├── README.md
│   │   ├── Dockerfile # Aquí puedes ver los pasos que he realizado para la implementación.
│   ├── RA3_2   # Práctica 2 - Web Application Firewall (WAF)
│   │   ├── assets
│   │   ├── README.md
│   │   ├── Dockerfile # Aquí puedes ver los pasos que he realizado para la implementación.
│   ├── RA3_3   # Práctica 3 - Reglas OWASP para ModSecurity
│   │   ├── assets
│   │   ├── README.md
│   │   ├── Dockerfile # Aquí puedes ver los pasos que he realizado para la implementación.
│   ├── RA3_4   # Práctica 4 - Protección contra ataques DoS
│   │   ├── assets
│   │   ├── README.md
│   │   ├── Dockerfile # Aquí puedes ver los pasos que he realizado para la implementación.
│   ├── RA3_5   # Práctica Extra 5: Protección Avanzada con doble WAF DNS (Cloudflare + Imperva)
│   │   ├── assets
│   │   ├── README.md
├── README.md  # Este archivo principal
```

## 🛠️ Pruebas en Vivo

Puedes probar todas las configuraciones en vivo desde: 🔗 [**https://dev.tonihack.es/**](https://dev.tonihack.es/)

Cada una de las prácticas tiene un contenedor Docker específico que se está ejecutando en el servidor.

## 🐳 Imágenes Docker

Las imágenes Docker de cada práctica están disponibles en Docker Hub:

- **Práctica 1 (CSP):** [pps10198545/ejercicio1-csp](https://hub.docker.com/r/pps10198545/ejercicio1-csp)
- **Práctica 2 (WAF):** [pps10198545/practica2-waf](https://hub.docker.com/r/pps10198545/practica2-waf)
- **Práctica 3 (OWASP ModSecurity):** [pps10198545/practica3-owasp](https://hub.docker.com/r/pps10198545/practica3-owasp)
- **Práctica 4 (DDoS Mitigation):** [pps10198545/practica4-ddos](https://hub.docker.com/r/pps10198545/practica4-ddos)

## 📖 Descripción de las Prácticas

### 🛡️ **Práctica 1: Content Security Policy (CSP)**

Implementación de **CSP** en Apache para mitigar ataques **XSS y otros vectores de inyección**.

### 🔥 **Práctica 2: Web Application Firewall (WAF)**

Configuración de **ModSecurity** como WAF con reglas básicas para bloquear ataques como **SQL Injection y XSS**.

### 🛠️ **Práctica 3: Reglas OWASP para ModSecurity**

Instalación y configuración del **OWASP Core Rule Set (CRS)** para una protección avanzada en Apache.

### 🚀 **Práctica 4: Protección contra ataques DDoS**

Implementación del módulo **mod\_evasive** para mitigar ataques de **Denegación de Servicio (DoS/DDoS)** en Apache.

## ⚡ Cómo Ejecutar las Imágenes Docker

Si quieres ejecutar las pruebas en tu propio entorno Docker, simplemente descarga las imágenes con:

```bash
docker pull pps10198545/ejercicio1-csp
```

Y ejecuta el contenedor:

```bash
docker run -d -p 80:80 -p 443:443 --name csp-server pps10198545/ejercicio1-csp
```

Repite esto para cada una de las imágenes.

## 📢 Contacto

info@tonihack.es
