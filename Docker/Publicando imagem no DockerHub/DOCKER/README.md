# Publicando imagem no Docker HUb 

Para publicar uma imagem no Docker Hub, siga os passos abaixo. Certifique-se de que você já tenha uma conta no Docker Hub e tenha o Docker instalado em sua máquina. 

1. **Crie uma imagem Docker:**
   Você precisará criar uma imagem Docker antes de publicá-la no Docker Hub. Para fazer isso, crie um Dockerfile que descreva sua imagem e use o comando `docker build` para construir a imagem. Certifique-se de que sua imagem esteja funcionando corretamente antes de prosseguir.

   no Dockerfile colocar isso para criar imagem 
   FROM nginx:latest


COPY html/ /usr/share/nginx/html 
ENTRYPOINT [ "/docker-entrypoint.sh" ]
CMD ["nginx", "-g", "daemon off;"]

em seguida rodar o comando 

docker build -t williamsartijose/nginx-fullcycle .

depois colocar a imagem para rodar para testar localmente 
docker run --rm -d -p 8282:80 williamsartijose/nginx-fullcycle

2. **Logue na sua conta Docker Hub:**
   Use o comando `docker login` para fazer login na sua conta Docker Hub. Isso solicitará suas credenciais (nome de usuário e senha) para autenticar sua sessão.

   ```
   docker login
   ```

3. **Tag da imagem:**
   Para que o Docker Hub saiba para qual repositório e tag enviar sua imagem, você deve nomear sua imagem de acordo com o padrão correto: `nome_do_seu_usuario/nome_do_repositorio:tag`. Por exemplo:

   ```
   docker tag nome_da_sua_imagem:tag nome_do_seu_usuario/nome_do_repositorio:tag
   ```

4. **Envie a imagem para o Docker Hub:**
   Use o comando `docker push` para enviar sua imagem para o Docker Hub. Certifique-se de usar o nome correto da imagem que você acabou de criar.

   ```
   docker push nome_do_seu_usuario/nome_do_repositorio:tag
   docker push williamsartijose/nginx-fullcycle
   ```

5. **Aguarde o upload:**
   O Docker irá enviar a imagem para o Docker Hub. Dependendo do tamanho da imagem e da velocidade da sua conexão, isso pode levar algum tempo. O progresso será exibido no terminal.

6. **Verifique a imagem no Docker Hub:**
   Após o upload ser concluído com sucesso, você pode visitar o Docker Hub no seu navegador e verificar se sua imagem está disponível no seu repositório.

Lembre-se de substituir `nome_do_seu_usuario`, `nome_do_repositorio` e `tag` pelos valores apropriados que você deseja usar. Certifique-se também de que sua imagem esteja configurada corretamente no Dockerfile antes de enviá-la.

Observe que para enviar imagens privadas, você deve configurar as permissões corretas no Docker Hub para permitir que outras pessoas acessem a imagem, se necessário.

## Imagem do meu Terminal 
![Web 0](https://github.com/williamsartijose/fulcyle3.0/blob/main/Docker/Publicando%20imagem%20no%20DockerHub/DOCKER/html/img2.png)
## A Imagem no DockerHUB
![Web 0](https://github.com/williamsartijose/fulcyle3.0/blob/main/Docker/Publicando%20imagem%20no%20DockerHub/DOCKER/html/Img3.png)
## Link da Imagem  da imagem publicada no DockerHUB 

https://hub.docker.com/repository/docker/williamsartijose/nginx-fullcycle/general


# Autor

William Sarti José

https://www.linkedin.com/in/william-analistadesistema/
