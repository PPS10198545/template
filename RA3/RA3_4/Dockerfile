### Dockerfile para la Práctica 4 (DDoS - mod_evasive) - Basado en la imagen de OWASP
# Instala mod_evasive para proteger Apache contra ataques DoS/DDoS
FROM pps10198545/practica3-owasp:latest

# Instalar mod_evasive
RUN apt update && apt install -y libapache2-mod-evasive

# Configurar mod_evasive
RUN mkdir -p /var/log/mod_evasive && chmod 777 /var/log/mod_evasive && \
    echo '<IfModule mod_evasive20.c>\n    DOSHashTableSize 3097\n    DOSPageCount 5\n    DOSSiteCount 50\n    DOSPageInterval 1\n    DOSSiteInterval 1\n    DOSBlockingPeriod 10\n    DOSEmailNotify admin@localhost\n    DOSLogDir "/var/log/mod_evasive"\n</IfModule>' > /etc/apache2/mods-available/evasive.conf && \
    a2enmod evasive

# Reiniciar Apache
CMD ["apachectl", "-D", "FOREGROUND"]
