# docker-study
Comandos Docker:
    Comando completo: docker run --name nginx -d -p 8080:80 nginx

        -d => evitar travar o terminal da execução do docker
        --name => nomear a imagem
        docker run -> rodar a iamgem docker
        nginx -> nome da imagem docker a ser provisionada
        -p 8080:80 => passando o valor da portar que o serviço nginx deve rodar

    docker ps => listar imagens docker em execução

    docker rm nginx -f: forçar a remoção da imagem de nome nginx

    docker exec: executta um comando no container
        docker exec nginx ls: listaráa os diretórios da pasta root do container
        docker exec -t nginx bash: vai executar o bash de forma iterativa


BIND MOUNTS
docker run -d --name nginx -p 8080:80 -v D:\Personal Work\docker-study\html:/usr/share/nginx/html nginx

-v: montar um volume *forma antiga de fazer
docker run -d --name nginx -p 8080:80 --mount type=bind,source="$(pwd)"/html,target=/usr/share/nginx/html nginx

docker rmi $(docker images -a -q) -f
docker rm $docker ps -a -q) -f