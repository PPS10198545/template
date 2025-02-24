### Dockerfile para la Práctica 3 (OWASP CRS) - Basado en la imagen del WAF
# Descarga y configura las reglas OWASP para ModSecurity
FROM pps10198545/practica2-waf:latest

# Clonar el OWASP CRS
RUN apt update && apt install -y git && \
    git clone https://github.com/SpiderLabs/owasp-modsecurity-crs.git /opt/owasp-modsecurity-crs && \
    cp /opt/owasp-modsecurity-crs/crs-setup.conf.example /etc/modsecurity/crs-setup.conf && \
    mkdir -p /etc/modsecurity/rules && \
    cp /opt/owasp-modsecurity-crs/rules/* /etc/modsecurity/rules/ && \
    touch /etc/modsecurity/rules/scanners-user-agents.data

# Configurar ModSecurity para cargar las reglas OWASP
RUN echo 'IncludeOptional /etc/modsecurity/*.conf\nInclude /etc/modsecurity/rules/*.conf' >> /etc/apache2/mods-enabled/security2.conf

# Reiniciar Apache
CMD ["apachectl", "-D", "FOREGROUND"]
