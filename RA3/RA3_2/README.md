# 🔥 Práctica 2: Web Application Firewall (WAF) - ModSecurity

En esta práctica hemos configurado **ModSecurity** en Apache para mitigar ataques como **inyección de código malicioso (XSS, SQLi)** y otras vulnerabilidades web. ModSecurity actúa como un **Web Application Firewall (WAF)**, analizando y bloqueando solicitudes maliciosas en tiempo real.

## 📸 **Prueba de Protección en Acción**

Cuando se intenta enviar un payload malicioso en un formulario, ModSecurity **detecta el ataque y bloquea la solicitud**, devolviendo un error `403 Forbidden`.

### **Intento de Ataque XSS**
Se intentó ejecutar un ataque **Cross-Site Scripting (XSS)**, pero ModSecurity lo bloqueó.

![XSS Attempt](https://github.com/PPS10198545/template/blob/main/RA3/RA3_2/assets/XSS.png)

### **Bloqueo de Acceso**
Cualquier intento de acceder a recursos restringidos o con parámetros sospechosos es denegado por ModSecurity.

![Forbidden Access](https://github.com/PPS10198545/template/blob/main/RA3/RA3_2/assets/Forbidden.png)

## 📌 **Descripción**
ModSecurity se ha configurado en modo **activo (SecRuleEngine On)** y se han aplicado reglas básicas para mitigar ataques web.

Ejemplo de configuración utilizada:
```apache
SecRuleEngine On
SecRule ARGS:testparam "@contains test" "id:1234,deny,status:403,msg:'Cazado por Ciberseguridad'"
```

## 🐳 **Ejecutar esta Práctica en Docker**
La imagen Docker correspondiente a esta práctica está disponible en **Docker Hub** y puede ejecutarse fácilmente en cualquier entorno con Docker.

### 🔽 **Descargar la imagen**
```bash
docker pull pps10198545/practica2-waf:latest
```

### 🚀 **Ejecutar el contenedor**
```bash
docker run -d -p 80:80 -p 443:443 --name practica2 pps10198545/practica2-waf
```

Una vez iniciado el contenedor, Apache estará corriendo con **ModSecurity** activado y las reglas configuradas para proteger contra ataques web.

## 🌍 **Pruebas en Vivo**
Puedes comprobar la configuración del WAF en funcionamiento visitando:
🔗 **[https://dev.tonihack.es/](https://dev.tonihack.es/)**

## 📖 **Detalles Técnicos**
- **Base de la imagen:** pps10198545/ejercicio1-csp
- **Servidor Web:** Apache 2.4
- **Módulo de Seguridad:** `mod_security`
- **Reglas Implementadas:**
  - Protección contra **XSS**
  - Protección contra **inyección SQL**
  - Bloqueo de **acceso no autorizado** (`403 Forbidden`)

## 📢 **Contacto y Feedback**
Si tienes dudas o sugerencias, info@tonihack.es o visita **[https://dev.tonihack.es/](https://dev.tonihack.es/)** para probarlo en vivo.

---
🚀 **Práctica 2 completada con éxito, protegiendo Apache con un Web Application Firewall (WAF).**
