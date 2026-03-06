# Estágio 1: Build (Usando o ambiente base oficial que já contém a fundação do Angular)
FROM mreferre/yelb-ui-env:0.4 AS builder

# O template original vive nesta pasta dentro da imagem
WORKDIR /clarity-seed

# Copiamos o nosso código local (o "patch" do Yelb) para sobrescrever a base
COPY . .

# Instalamos as dependências e compilamos
RUN npm install --unsafe-perm
RUN ng build --prod

# Estágio 2: Servidor Web (Leve e rápido usando o espelho da AWS)
FROM public.ecr.aws/docker/library/nginx:stable-alpine
LABEL maintainer="sre-lab@exemplo.com"

# Copiamos os arquivos finais compilados para o Nginx
COPY --from=builder /clarity-seed/dist/ /usr/share/nginx/html/

EXPOSE 80