# 🚀 Práctica 4: Protección contra Ataques DoS/DDoS (mod_evasive)

En esta práctica hemos configurado el módulo **mod_evasive** en Apache para detectar y mitigar ataques de **Denegación de Servicio (DoS/DDoS)**, limitando el número de solicitudes repetitivas desde una misma IP.

## 📸 **Prueba de Protección en Acción**

Al ejecutar un ataque de prueba con **Apache Bench (ab)** simulando una gran cantidad de peticiones concurrentes, mod_evasive bloqueó la mayoría de las solicitudes, resultando en múltiples fallos.

### **Simulación de Ataque con Apache Bench**

En esta prueba, se enviaron **1000 solicitudes con 100 conexiones concurrentes**:

![DDoS Attempt](https://github.com/PPS10198545/template/blob/main/RA3/RA3_4/assets/ddos.png?raw=true)

El resultado muestra que **970 solicitudes fueron bloqueadas**, lo que confirma que el módulo está funcionando correctamente.

### **Registros de Apache Bloqueando Solicitudes**

Los intentos de ataque quedaron reflejados en los logs de Apache:

![Blocked Logs](https://github.com/PPS10198545/template/blob/main/RA3/RA3_4/assets/logs.png?raw=true)

Cada vez que un cliente excede el umbral permitido de solicitudes, mod_evasive lo bloquea automáticamente.

## 📌 **Descripción**
`mod_evasive` protege Apache detectando múltiples solicitudes sospechosas y bloqueando IPs temporalmente.

Ejemplo de configuración utilizada:
```apache
<IfModule mod_evasive20.c>
    DOSHashTableSize 3097
    DOSPageCount 5
    DOSSiteCount 50
    DOSPageInterval 1
    DOSSiteInterval 1
    DOSBlockingPeriod 10
    DOSEmailNotify admin@localhost
    DOSLogDir "/var/log/mod_evasive"
</IfModule>
```

## 🐳 **Ejecutar esta Práctica en Docker**
La imagen Docker correspondiente a esta práctica está disponible en **Docker Hub** y puede ejecutarse fácilmente en cualquier entorno con Docker.

### 🔽 **Descargar la imagen**
```bash
docker pull pps10198545/practica4-ddos:latest
```

### 🚀 **Ejecutar el contenedor**
```bash
docker run -d -p 80:80 -p 443:443 --name practica4 pps10198545/practica4-ddos
```

Una vez iniciado el contenedor, Apache estará corriendo con `mod_evasive` activado para mitigar ataques de **Denegación de Servicio (DoS/DDoS)**.

## 🌍 **Pruebas en Vivo**
Puedes comprobar la protección de mod_evasive en funcionamiento visitando:
🔗 **[https://dev.tonihack.es/](https://dev.tonihack.es/)**

## 📖 **Detalles Técnicos**
- **Base de la imagen:** pps10198545/practica3-owasp
- **Servidor Web:** Apache 2.4
- **Módulo de Seguridad:** `mod_evasive`
- **Protecciones Implementadas:**
  - Bloqueo de IPs con múltiples solicitudes en corto tiempo.
  - Registro de intentos de ataque en `/var/log/apache2/error.log`.
  - Protección contra herramientas de escaneo y bots agresivos.

## 📢 **Contacto y Feedback**
Si tienes dudas o sugerencias, puedes contactarnos en:
📩 **info@tonihack.es**  
🌍 **[https://dev.tonihack.es/](https://dev.tonihack.es/)**

---
🚀 **Práctica 4 completada con éxito, protegiendo Apache contra ataques de Denegación de Servicio (DoS/DDoS).**
