# 🛠️ Práctica 3: Reglas OWASP para ModSecurity

En esta práctica hemos configurado **ModSecurity** con el **OWASP Core Rule Set (CRS)**, un conjunto avanzado de reglas diseñadas para proteger aplicaciones web contra ataques como **inyección SQL, XSS, ejecución remota de comandos y traversal path**.

## 📸 **Prueba de Protección en Acción**

El firewall detectó y bloqueó intentos de ataques, devolviendo un **error 403 Forbidden** ante solicitudes maliciosas.

![OWASP CRS Protection](https://github.com/PPS10198545/template/blob/main/RA3/RA3_3/assets/curl.png?raw=true)

## 📌 **Descripción**
El OWASP CRS se ha configurado en **modo estricto**, filtrando y bloqueando peticiones sospechosas.

Ejemplo de reglas bloqueadas:
```bash
curl -I http://localhost/index.html?testparam=test   # Bloqueado por filtrado de parámetros sospechosos
curl -I http://localhost/index.html?exec=/bin/bash  # Bloqueado por intento de ejecución remota de comandos
curl -I http://localhost/index.html?exec=/../../    # Bloqueado por ataque de traversal path
```

## 🐳 **Ejecutar esta Práctica en Docker**
La imagen Docker correspondiente a esta práctica está disponible en **Docker Hub** y puede ejecutarse fácilmente en cualquier entorno con Docker.

### 🔽 **Descargar la imagen**
```bash
docker pull pps10198545/practica3-owasp:latest
```

### 🚀 **Ejecutar el contenedor**
```bash
docker run -d -p 80:80 -p 443:443 --name practica3 pps10198545/practica3-owasp
```

Una vez iniciado el contenedor, Apache estará corriendo con **ModSecurity + OWASP CRS** para filtrar tráfico malicioso.

## 🌍 **Pruebas en Vivo**
Puedes comprobar la configuración del OWASP CRS en funcionamiento visitando:
🔗 **[https://dev.tonihack.es/](https://dev.tonihack.es/)**

## 📖 **Detalles Técnicos**
- **Base de la imagen:** pps10198545/practica2-waf
- **Servidor Web:** Apache 2.4
- **Módulo de Seguridad:** `mod_security`
- **Reglas Implementadas:**
  - Protección contra **XSS**
  - Protección contra **inyección SQL**
  - Bloqueo de **command injection**
  - Mitigación de **traversal path attacks**

## 📢 **Contacto y Feedback**
Si tienes dudas o sugerencias, puedes contactarnos en:
📩 **info@tonihack.es**  
🌍 **[https://dev.tonihack.es/](https://dev.tonihack.es/)**

---
🚀 **Práctica 3 completada con éxito, protegiendo Apache con OWASP Core Rule Set (CRS).**

