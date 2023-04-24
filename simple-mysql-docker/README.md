# README.md

Exemplo de como subir um MySQL usando Docker

```
docker container run -d --name mysql-example -p 3306:3306 -e MYSQL_ROOT_PASSWORD=example -e MYSQL_DATABASE=lab -e MYSQL_USER=lab_user -e MYSQL_PASSWORD=P455w0RD mysql:8
```

NOTA: Utilize o DBeaver para se conectar no banco de dados  
Problemas conhecidos:  
- Public Key Retrieval is not allowed: https://smarttechways.com/2022/07/22/mysql-public-key-retrieval-is-not-allowed/

Criar tabela no MySQL

```
CREATE TABLE IF NOT EXISTS product (
    product_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    status TINYINT NOT NULL,
    description TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
)  ENGINE=INNODB;
```

Inserir dados

```
INSERT INTO 
    product(name, status, description)
VALUES
	('Teclado', true, 'Teclado com cabo'),
	('Mouse', true, 'Mouse com cabo'),
	('Mouse pad preto' , false, 'Mouse pad pequeno preto'),
    ('Mouse pad personagem' , false, 'Mouse pad pequeno personagem');
```

Praticar selects

```
select * from product
select * from product where status is true
select from product where status is false
select status, count(1) from product group by 1
```




