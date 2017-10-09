# Skeleton
## Instalação

Clone o repositório e acesse o diretório:
```sh
git clone git@gitlab.com:siworks/slim3-doctrine-skeleton.git && cd slim3-doctrine-skeleton
```
Caso você não tenha o container `docker-hosts-updater` rodando, você pode executá-lo assim: 
```sh
docker run -d --restart=always --name docker-hosts-updater -v /var/run/docker.sock:/var/run/docker.sock -v /etc/hosts:/opt/hosts grachev/docker-hosts-updater
```
Ele irá mapear automaticamento os hostnames dos containers para os IP's correspondentes. Este mapeamento pode ser feito manualmente através dos hosts da máquina.

Execute o composer:
```sh
docker-compose run --rm composer
```

Suba o serviço WEB com o docker-compose:
```sh
docker-compose up -d web
```

Crie o schema do mysql:
```sh
docker exec -t dev-skeleton-web vendor/bin/doctrine orm:schema-tool:create
```

Acesse o endereço http://dev.skeleton.siworks.com.br
