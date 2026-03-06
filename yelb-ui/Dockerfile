FROM mreferre/yelb-ui:0.10

LABEL maintainer="sre-lab@exemplo.com"
LABEL description="Yelb UI - Migrated to AWS ECR"

# Truque SRE infalível: Injetando antes do fechamento do body e forçando a posição no topo
RUN sed -i 's/<\/body>/<div style="background-color: #ff9900; color: white; text-align: center; padding: 15px; font-size: 24px; font-weight: bold; z-index: 9999; position: fixed; top: 0; left: 0; width: 100%;">\🚀 AWS SRE Lab - Pipeline CI\/CD 100% Automatizado! \🚀<\/div><\/body>/g' /usr/share/nginx/html/index.html