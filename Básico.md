# DOCKER - MYSQL

## COMANDOS DOCKER:

### 1) docker pull mysql

- Baixa a imagem do mysql para dentro do Docker.

### 2) docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=root -d -p 3306:3306 mysql:latest

- Criar um container com a imagem do mysql

### 3) docker exec -it mysql-container mysql -u root -p

- Acessar o banco de dados via linha de comando.


## COMANDOS MYSQL:
	
### Criar banco de dados
`CREATE DATABASE meubanco;`

### Mostrar bancos de dados criados.
`SHOW DATABASES;`


### Selecionar banco e criar tabela:

	USE meubanco;  -- Mudar para o banco que você acabou de criar

	CREATE TABLE usuarios (
	    id INT AUTO_INCREMENT PRIMARY KEY,
	    nome VARCHAR(255) NOT NULL,
	    email VARCHAR(255) NOT NULL UNIQUE
	);

	INSERT INTO usuarios (nome, email) VALUES ('Fulano', 'fulano@example.com');

## COMANDOS MAIS USADOS NO DOCKER

### 1. **Gerenciamento de Imagens**

-   **Listar Imagens**    
    `docker images` 
    
-   **Baixar uma Imagem**
    `docker pull <nome-da-imagem>` 
    
    Exemplo: `docker pull mysql:latest`
    
-   **Remover uma Imagem**
    `docker rmi <nome-da-imagem>` 
    
    Exemplo: `docker rmi mysql:latest`
    

### 2. **Gerenciamento de Containers**

-   **Listar Containers em Execução**
 `docker ps` 
    
-   **Listar Todos os Containers (incluindo parados)**
    `docker ps -a` 
    
-   **Iniciar um Container**
   `docker start <nome-ou-id-do-container>` 
    
-   **Parar um Container**
  `docker stop <nome-ou-id-do-container>` 
    
-   **Reiniciar um Container**
 `docker restart <nome-ou-id-do-container>` 
    
-   **Remover um Container**
  `docker rm <nome-ou-id-do-container>` 
    
-   **Executar um Comando em um Container em Execução**
  `docker exec -it <nome-ou-id-do-container> <comando>` 
    
    Exemplo: `docker exec -it mysql-container mysql -u root -p`
    

### 3. **Gerenciamento de Volumes**

-   **Listar Volumes**
 `docker volume ls` 
    
-   **Criar um Volume**
 `docker volume create <nome-do-volume>` 
    
-   **Remover um Volume**
`docker volume rm <nome-do-volume>` 
    

### 4. **Gerenciamento de Redes**

-   **Listar Redes**
 `docker network ls` 
    
-   **Criar uma Rede**
 `docker network create <nome-da-rede>` 
    
-   **Remover uma Rede**
 `docker network rm <nome-da-rede>` 
    

### 5. **Docker Compose**

Se você estiver usando o <u>Docker Compose</u>, aqui estão alguns comandos úteis:

-   **Iniciar Serviços Definidos em um `docker-compose.yml`**
`docker-compose up` 
    
-   **Iniciar em Modo Detachado**
 `docker-compose up -d` 
    
-   **Parar Serviços**
`docker-compose down` 
    
-   **Recriar Containers (usando as novas configurações do Compose)**
 `docker-compose up --force-recreate` 
    

### 6. **Outros Comandos Úteis**

-   **Visualizar Logs de um Container**
  `docker logs <nome-ou-id-do-container>` 
    
-   **Visualizar o Estado de um Container em Execução**
`docker inspect <nome-ou-id-do-container>` 
    
-   **Acessar o Terminal de um Container em Execução**
 `docker exec -it <nome-ou-id-do-container> /bin/bash`
