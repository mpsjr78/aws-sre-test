FROM public.ecr.aws/docker/library/node:12-stretch AS builder
WORKDIR /app
COPY package.json .
RUN npm install --unsafe-perm
RUN npm install -g @angular/cli@8.3.29 --unsafe-perm
COPY . .
RUN ng build --prod

FROM public.ecr.aws/docker/library/nginx:stable-alpine
LABEL maintainer="voce@exemplo.com"
# Copia da raiz da dist, pois nesta versão do Angular o build cai ali
COPY --from=builder /app/dist/ /usr/share/nginx/html/
EXPOSE 80