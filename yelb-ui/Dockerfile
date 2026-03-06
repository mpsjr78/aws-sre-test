FROM mreferre/yelb-ui:0.10

COPY index.html /usr/share/nginx/html/index.html

# Garante que o Nginx tenha permissão de ler o arquivo
RUN chmod 644 /usr/share/nginx/html/index.html

LABEL maintainer="sre-lab@exemplo.com"