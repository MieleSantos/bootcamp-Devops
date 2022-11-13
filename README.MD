# Docker fundamentos/Comandos

### Executando um contêiner

- ```docker pull ubuntu```
- ```docker run ubuntu```
- ```docker run ubuntu sleep 10```
- ```docker run ubuntu sleep 1500```
- ```docker stop [id]```
- ```docker run --help```
- ```docker run -it ubuntu```

### Executando aplicações no contêiner

- ```docker run -dti  ubuntu``` 
- ```docker exec -it [id ou nome]  /bin/bash```

### Excluindo contêineres

- ```docker stop [id]```
- ```docker rm [id]```
- ```docker rmi [imagem]```

### Nomeando contêineres
- ```docker run -dti --name Ubuntu-A ubuntu```

### Copiando arquivos para o contêiner e fora
- ```docker exec -ti Ubuntu-A /bin/bash```
- ```docker exec Ubuntu-A mkdir /destino/```
- ```docker exec Ubuntu-A mkdir ls -l /```
- ```nano Arquivo.txt```
- ```docker cp arquivo.txt Ubuntu-A:/aula/```

- ```docker cp Ubuntu-A:/destino/Meuzip.zip  Zipcopia.zip```

### Criando um contêiner Mysql 

- ```docker pull mysql```
- ```docker run -e MYSQL_ROOT_PASSWORD=Senha123 --name mysql-A -d -p 3306:3306 mysql```
- ```docker exec -it mysql-A bash```


- ```mysql -u root -p --protocol=tcp```

- ```CREATE DATABASE aula;```
- ```show databases;```

- ```docker inspect mysql-A```
- ```mysql -u root -p --protocol=tcp```


### Acessando um container externamente

- ```docker run -e MYSQL_ROOT_PASSWORD=Senha123 --name mysql-A -d -p 3306:3306 --volume=/data:/var/lib/mysql mysql- ```<br>

- ```mysql -u root -p --protocol=tcp --port=3306```
```
    CREATE TABLE alunos (
        AlunoID int,
        Nome varchar(50),
        Sobrenome varchar(50),
        Endereco varchar(150),
        Cidade varchar(50)
    );


    INSERT INTO alunos (AlunoID, Nome, Sobrenome, Endereco, Cidade) VALUES (1, 'Carlos Alberto', 'da Silva', 'Av. que sobe e desce que ninguém conhece', 'Manaus');
```