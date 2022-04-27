# Comandos SQL - Referência
<!-- ____________________________________________________________________ -->
## Modelagem física

### Criar banco de dados
```sql
CREATE DATABASE vendas CHARACTER SET utf8mb4;
```
<!-- ____________________________________________________________________ -->

### Criar tabela fabricantes
```sql
CREATE TABLE fabricantes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
);
```
<!-- ____________________________________________________________________ -->

### Visualizar detalhes estruturais da tabela
```sql
DESC fabricantes;
```

<!-- ____________________________________________________________________ -->

### Criar tabela produtos
```sql
CREATE TABLE produtos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL, 
    descricao TEXT(1000) NOT NULL,
    preco DECIMAL(6,2) NOT NULL,
    fabricante_id INT NOT NULL
);
```
<!-- ____________________________________________________________________ -->
<!-- Obs: # é comentário em SQL -->

### Criação da chave estrangeira (relacionamento entre as tabelas)
```sql
ALTER TABLE produtos
    # CONSTRAINT é uma restrição definida no relacionamento
    ADD CONSTRAINT fk_produtos_fabricantes

    # A chave estrangeira deve fazer referência à chave primaria
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id)
```
<!-- ____________________________________________________________________ -->
<!-- Apagar tabela -->

### Apagar tabela
```sql
DROP TABLE fabricantes;
```
