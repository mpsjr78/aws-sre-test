# Estágio 1: Build (Usando o espelho público da AWS para evitar limites)
FROM public.ecr.aws/docker/library/node:12-stretch AS builder

WORKDIR /app

# 1. Baixar a "fundação" (o template original da VMware)
RUN git clone https://github.com/vmware/clarity-seed.git

# 2. Entrar na pasta do template
WORKDIR /app/clarity-seed

# 3. Copiar o nosso código local (o "patch" do Yelb) por cima da fundação
# Isso vai mesclar os nossos arquivos com os originais, fornecendo o tsconfig.json que faltava!
COPY . .

# 4. Instalar as dependências e compilar
RUN npm install --unsafe-perm
RUN npm install -g @angular/cli@8.3.29 --unsafe-perm
RUN ng build --prod

# Estágio 2: Servidor Web (Nginx super leve)
FROM public.ecr.aws/docker/library/nginx:stable-alpine
LABEL maintainer="sre-lab@exemplo.com"

# 5. Copiar os arquivos finais gerados
COPY --from=builder /app/clarity-seed/dist/ /usr/share/nginx/html/

EXPOSE 80