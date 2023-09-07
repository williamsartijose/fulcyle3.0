# Criando primeira imagem com Dockerfile

Passo 1: Crie um diretório de trabalho

Primeiro, crie um diretório para o seu projeto Docker. Isso ajudará a manter todos os arquivos relacionados em um só lugar.

mkdir meu-primeiro-docker-image
cd meu-primeiro-docker-image


Passo 2: Crie um arquivo Dockerfile

Dentro do diretório, crie um arquivo chamado "Dockerfile" (sem extensão) com o seguinte conteúdo:


# Use uma imagem base como ponto de partida
FROM nginx:alpine

# Copie um arquivo HTML simples para a pasta de documentos padrão do Nginx
COPY index.html /usr/share/nginx/html

# Exponha a porta 80 para que possamos acessar o conteúdo web
EXPOSE 80



Passo 3: Crie o arquivo HTML

Crie um arquivo HTML simples chamado "index.html" no mesmo diretório e adicione algum conteúdo a ele. Por exemplo:

<!DOCTYPE html>
<html>
<head>
    <title>Minha Primeira Imagem Docker</title>
</head>
<body>
    <h1>Olá, Mundo!</h1>
</body>
</html>


Passo 4: Construa a imagem

Agora, você pode construir a imagem Docker executando o seguinte comando dentro do diretório do projeto:

docker build -t minha-primeira-imagem-docker .

docker build -t williamsartijoseaccenture/nginx-com-vim:later .

Onde "minha-primeira-imagem-docker" é o nome que você deseja dar à sua imagem. Certifique-se de incluir o ponto (.) no final do comando para indicar que o Dockerfile está no diretório atual.

Passo 5: Execute um contêiner com a imagem
docker run -it williamsartijoseaccenture/nginx-com-vim:later bash para entrar no container no modo root 
Agora que você construiu sua imagem Docker, pode criar e executar um contêiner com ela usando o seguinte comando:
docker run -d -p 8080:80 minha-primeira-imagem-docker

sso criará um contêiner com base na sua imagem e mapeará a porta 8080 do host para a porta 80 do contêiner. Você pode acessar seu aplicativo em um navegador digitando "http://localhost:8080" no seu computador.

Passo 6: Pare e remova o contêiner (opcional)

Se você desejar parar e remover o contêiner, use os seguintes comandos:

docker stop <container_id>
docker rm <container_id>

Substitua "<container_id>" pelo ID do contêiner que você obteve ao executar o contêiner.

Isso é tudo! Você criou com sucesso sua primeira imagem Docker e a executou em um contêiner. Agora você pode experimentar criando imagens mais complexas e personalizadas para suas necessidades específicas.


# Autor

William Sarti José

https://www.linkedin.com/in/william-analistadesistema/
