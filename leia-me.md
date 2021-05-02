# Cria a imagem 
docker image build -t hcinf/api-conversao:v1 .

# Subir a imagem para o repositório 
docker push hcinf/api-conversao:v1

# Subir a última versão
docker tag hcinf/api-conversao:v1  hcinf/api-conversao:latest
docker push hcinf/api-conversao:latest

# Rodando local 
docker container run -d -p 8085:8080 hcinf/api-conversao:v1


# Testando a API no Browser 
http://localhost:8086/fahrenheit/50/celsius
http://localhost:8086/celsius/10/fahrenheit

# Testando com Swagger 
http://localhost:8086/api-docs/