# README.md

Este é um exemplo simples para subir um site em PHP utilizando Apache e Docker

## Comando

Criar um container para validar o apache rodando
```
docker container run -d -p 80:80 --name php-example php:8.1.18-apache-buster
```

Criar um novo container chamado `php-example2` agora mapeando a pasta `www` do Docker Host para dentro do container.
```
docker container run -d -p 81:80 --name php-example2 -v $(pwd)/www/:/var/www/html/ php:8.1.18-apache-buster 
```

Acesse pelo navegador e valide.