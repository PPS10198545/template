# 🛡️ Práctica 1: Content Security Policy (CSP)

En esta práctica hemos implementado **Content Security Policy (CSP)** en Apache para mitigar ataques de **Cross-Site Scripting (XSS)** y otras vulnerabilidades web relacionadas con la inyección de código.

## 📸 **Resultado del Análisis de Seguridad**
El sitio fue analizado y los encabezados de seguridad han sido correctamente configurados, como se muestra en la imagen:

![Security Check](https://github.com/PPS10198545/template/blob/main/RA3/RA3_1/assets/check.png?raw=true)

## 📌 **Descripción**
La cabecera **CSP** limita las fuentes desde las cuales el navegador puede cargar contenido, evitando la ejecución de scripts maliciosos y reduciendo el riesgo de ataques XSS.

Ejemplo de configuración utilizada:
```apache
Header set Content-Security-Policy "default-src 'self'; img-src *; media-src media1.com media2.com; script-src userscripts.example.com"
```

## 🐳 **Ejecutar esta Práctica en Docker**
La imagen Docker correspondiente a esta práctica está disponible en **Docker Hub** y puede ejecutarse fácilmente en cualquier entorno con Docker.

### 🔽 **Descargar la imagen**
```bash
docker pull pps10198545/ejercicio1-csp:latest
```

### 🚀 **Ejecutar el contenedor**
```bash
docker run -d -p 80:80 -p 443:443 --name practica1 pps10198545/ejercicio1-csp
```

Una vez iniciado el contenedor, el servidor Apache estará corriendo con la configuración de **CSP** aplicada.

## 🌍 **Pruebas en Vivo**
Puedes comprobar la configuración de CSP en funcionamiento visitando:
🔗 **[https://dev.tonihack.es/](https://dev.tonihack.es/)**

## 📖 **Detalles Técnicos**
- **Base de la imagen:** Ubuntu 22.04
- **Servidor Web:** Apache 2.4
- **Módulo de Seguridad:** `headers`
- **Encabezados implementados:**
  - `Content-Security-Policy`
  - `Strict-Transport-Security` (HSTS)

## 📢 **Contacto y Feedback**
info@tonihack.es - **[https://dev.tonihack.es/](https://dev.tonihack.es/)** para probarlo en vivo.

---
🚀 **Práctica 1 completada con éxito, protegiendo Apache con Content Security Policy (CSP).**
