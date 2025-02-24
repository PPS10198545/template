# 🔥 Práctica Extra 5: Protección Avanzada con WAF DNS (Cloudflare + Imperva) 🔥

## 🚀 **Objetivo**
En esta práctica hemos implementado una protección **ultra avanzada** para nuestro servidor mediante la combinación de **dos de los mejores Web Application Firewalls (WAFs) DNS del mercado: Cloudflare e Imperva**. Con esta configuración, conseguimos un **doble blindaje** ante ataques web, asegurando que solo tráfico legítimo llegue a nuestro servidor.

> 🛡️ **Cloudflare** nos protege contra ataques de **DDoS, bots maliciosos y tráfico sospechoso**.
>
> 🔥 **Imperva** nos brinda una **defensa avanzada contra exploits, inyecciones y tráfico de alta criticidad**, además de ofrecer reglas **personalizadas** de mitigación.

---

## 📸 **Estructura de la Configuración**

### 1️⃣ **Añadir nuestro sitio a Imperva**
Lo primero que hicimos fue registrar nuestro dominio en **Imperva** para que su firewall empiece a analizar el tráfico entrante y bloquear amenazas en tiempo real.

![Añadir Sitio en Imperva](https://github.com/PPS10198545/template/blob/main/RA3/RA3_5/assets/AddWebsite-Imperva.png?raw=true)

### 2️⃣ **Configuración de Reglas WAF en Imperva**
Implementamos reglas **personalizadas** para bloquear **XSS, SQL Injection, RFI y acceso ilegal a recursos**. Estas reglas aseguran que cualquier intento de ataque sea detenido antes de llegar a la infraestructura.

![Reglas WAF Imperva](https://github.com/PPS10198545/template/blob/main/RA3/RA3_5/assets/WAFRules-Imperva.png?raw=true)

### 3️⃣ **Filtrado de Bots y Protección contra Scrapers**
Imperva nos permite bloquear bots **maliciosos y scrapers**, asegurando que solo los bots legítimos (Google, Bing, etc.) puedan acceder a nuestra web.

![Control de Bots Imperva](https://github.com/PPS10198545/template/blob/main/RA3/RA3_5/assets/BotAccessControl-Imperva.png?raw=true)

### 4️⃣ **Protección de Páginas Críticas**
Hemos asegurado rutas sensibles como `/admin`, requiriendo **autenticación multifactor (MFA)** para acceder, evitando accesos no autorizados.

![Protección de Páginas Sensibles](https://github.com/PPS10198545/template/blob/main/RA3/RA3_5/assets/ProtectedPages-Imperva.png?raw=true)

### 5️⃣ **Cambio de Registros DNS para Pasar el Tráfico por Imperva**
Para que Imperva pueda filtrar correctamente el tráfico, cambiamos nuestro registro DNS a **CNAME**, apuntando nuestro dominio hacia su infraestructura.

![Cambio de DNS en Imperva](https://github.com/PPS10198545/template/blob/main/RA3/RA3_5/assets/ChangeCNAME-Imperva.png?raw=true)

### 6️⃣ **Configuración de Cloudflare: Seguridad Adicional**
Una vez que el tráfico pasa por Imperva, **lo protegemos aún más con Cloudflare**, activando:
- 🚀 **Modo "Under Attack"** para mitigar ataques masivos.
- 🛡️ **Protección contra DDoS automática**.
- 🔥 **Desafíos JS y validaciones de tráfico sospechoso**.

![Cloudflare Under Attack Mode](https://github.com/PPS10198545/template/blob/main/RA3/RA3_5/assets/cloudflare_UAM.png?raw=true)

### 7️⃣ **Configuración de CNAME en Cloudflare**
Modificamos Cloudflare para que también actúe como **proxy**, mejorando la latencia y seguridad de las conexiones.

![Configuración DNS en Cloudflare](https://github.com/PPS10198545/template/blob/main/RA3/RA3_5/assets/CloudflareCNAME-Add.png?raw=true)

### 8️⃣ **Comprobación de la Configuración**
Después de aplicar todos los cambios, verificamos que el tráfico pasara correctamente por Imperva y Cloudflare, asegurándonos de que los ataques sean bloqueados antes de tocar el servidor.

![DNS Correcto en Imperva](https://github.com/PPS10198545/template/blob/main/RA3/RA3_5/assets/DNSOK-Imperva.png?raw=true)

### 9️⃣ **Detección de Ataques y Respuesta de Imperva**
Cuando un atacante intenta realizar un ataque como **Path Traversal**, **SQL Injection**, o cualquier otro vector, Imperva responde con un **bloqueo inmediato**, generando un **Error 15**.

![Error 15 - Bloqueo de Imperva](https://github.com/PPS10198545/template/blob/main/RA3/RA3_5/assets/AccessDenied-Imperva.png?raw=true)

---

## 🔥 **Beneficios de esta Implementación**
✅ **Doble capa de seguridad** con Cloudflare + Imperva.  
✅ **Protección en tiempo real** contra XSS, SQLi, RFI, DoS/DDoS y scraping.  
✅ **Optimización del rendimiento** gracias a Cloudflare.  
✅ **Filtrado avanzado de bots** y prevención de ataques automatizados.  
✅ **Mitigación proactiva de ataques** con Firewalls de última generación.  

---

## 🌍 **Pruebas en Vivo**
Puedes comprobar la seguridad en acción visitando:
🔗 **[https://dev.tonihack.es/](https://dev.tonihack.es/)**

## 📢 **Contacto y Feedback**
📩 **info@tonihack.es**  
🌍 **[https://dev.tonihack.es/](https://dev.tonihack.es/)**

---
🚀 **Práctica 5 completada con éxito: Configuración de un WAF DNS avanzado con Cloudflare + Imperva.**

