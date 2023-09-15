# Comandos SQL - Referência
<!-- ________________________ -->
## Modelagem fisíca

### Criar banco de dados

```sql

CREATE DATABASE vendas CHARACTER SET utf8mb4;

```       
     <!-- ________________________ -->                     
### Criar a tabela fabricante

```sql
CREATE TABLE fabricantes (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL 
)
```
     <!-- ________________________ -->                     
### Criar a tabela produtos

```sql
CREATE TABLE produtos (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL, 
    descricao TEXT (1000) NOT NULL,
    preco DECIMAL (6,2) NOT NULL,
    quantidade TINYINT (4) NOT NULL
)
```
     <!-- ________________________ -->                     
### Criação da chave estrangeira (realcionamento entre tabelas)

```sql
ALTER TABLE produtos 
    # CONSTRANT é uma restrição definida no relacionamneto
    ADD CONSTRAINt fk_produtos_fabricantes

    # A chave estrangeira deve ser referÊncia a chave primaria
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id)

```
### Adicionar campo/coluna em uma tabela 

```sql

ALTER TABLE produtos ADD fabricante_id INT NOT NULL
AFTER quantidade;