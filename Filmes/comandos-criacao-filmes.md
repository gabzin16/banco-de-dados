# Comandos SQL - Referência
<!-- __________________________________________ -->
## Modelagem física

### Criar banco de dados

```sql

CREATE DATABASE filmes CHARACTER SET utf8mb4;

```

<!-- __________________________________________ -->

### Criar a tabela generos

```sql
CREATE TABLE generos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    genero VARCHAR(45) NOT NULL
)

```
<!-- __________________________________________ -->

### Criar a tabela filmes

```sql
CREATE TABLE filmes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(45) NOT NULL,
    lancamento YEAR(4) NOT NULL,
    genero_id INT NOT NULL
)

```

<!-- __________________________________________ -->

### Criação da chave estrangeira (relacionamento entre tabelas)

```sql

ALTER TABLE filmes
    ADD CONSTRAINT fk_filmes_generos
    FOREIGN KEY(genero_id) REFERENCES generos(id)

```
