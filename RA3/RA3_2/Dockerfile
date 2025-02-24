### Dockerfile para la Práctica 2 (WAF - ModSecurity) - Basado en la imagen de CSP
# Esta imagen instala ModSecurity y configura un WAF básico
FROM pps10198545/ejercicio1-csp:latest

# Instalar ModSecurity
RUN apt update && apt install -y libapache2-mod-security2

# Configurar ModSecurity con reglas básicas
RUN cp /etc/modsecurity/modsecurity.conf-recommended /etc/modsecurity/modsecurity.conf && \
    sed -i 's/SecRuleEngine DetectionOnly/SecRuleEngine On/' /etc/modsecurity/modsecurity.conf && \
    a2enmod security2

# Reiniciar Apache
CMD ["apachectl", "-D", "FOREGROUND"]
