# Envelopando a imagem oficial
FROM mreferre/yelb-ui:0.10

LABEL maintainer="sre-lab@exemplo.com"
LABEL description="Yelb UI - Migrated to AWS ECR"

# Truque SRE: Injetando um banner visível diretamente no HTML compilado do Nginx
RUN sed -i 's/<body>/<body><div style="background-color: #ff9900; color: white; text-align: center; padding: 15px; font-size: 24px; font-weight: bold; z-index: 9999; position: relative;">\🚀 AWS SRE Lab - Pipeline CI\/CD 100% Automatizado! \🚀<\/div>/g' /usr/share/nginx/html/index.html