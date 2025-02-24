### Dockerfile para la Práctica 1 (CSP) - Basado en Ubuntu 22.04
# Esta imagen instala Apache y configura Content Security Policy (CSP)
FROM ubuntu:22.04

# Instalar Apache
RUN apt update && apt install -y apache2

# Configurar CSP
RUN echo 'Header set Content-Security-Policy "default-src \"self\"; img-src *; media-src media1.com media2.com; script-src userscripts.example.com"' > /etc/apache2/conf-available/csp.conf && \
    a2enconf csp && a2enmod headers

# Exponer puertos y ejecutar Apache
EXPOSE 80 443
CMD ["apachectl", "-D", "FOREGROUND"]
