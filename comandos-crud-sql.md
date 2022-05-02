# Comandos SQL para CRUD - Referência

## Resumo
C -> Create (insere dados)
R -> Read (ler dados)
U -> Update (atualizar dados)
D -> Delete (excluir dados)

## Insert
### Fabricantes

```sql
INSERT INTO fabricantes (nome) VALUES('Asus');
INSERT INTO fabricantes (nome) VALUES('Dell');
INSERT INTO fabricantes (nome) 
VALUES('Apple'), ('LG'), ('Samsung'), ('Brastemp');
```

### Produtos

```sql
INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id) VALUES(
'Ultrabook',
'Ultrabook Asus com preocessador Intel Core i12, memoria RAM de 16Gb e Windows 11',
6500.99,
7,
1
);

INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'Tablet Android',
    'Tablet com a versão 12 do sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64 GB',
    4999,
    3,
    5 #Samsung
);

INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'Geladeira',
    'Refrigerador Frost-free com acesso à Internet das Coisas e bla bla bla',
    1500,
    10,
    6 -- Brastemp
    ),
(
    'iPhone 13 Pro Max',
    'Alta durabilidade, processador Bionic 14, 128 GB de armazenamento, 6GB de RAM e caro pra caramba',
    6999.99,
    3,
    3 -- Apple
    ),
(
    'iPad Mini',
    'Tablet Apple com tela retina display de 4k, memória interna de 64GB,acesso ai iCloud',
    5000,
    8,
    3 -- Apple
);
-- ___________________________________________________________________
```

### Continua exercício adicionando (Fabricantes)

```sql
INSERT INTO fabricantes (nome) 
VALUES('Positivo'), ('Microsoft');
```
### Continua exercício adicionando (Produtos)

```sql

INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'Xbox',
    'Console de última geração com acesso aos melhores jogos e bla bla',
    2500,
    6,
    8 -- Microsoft
    ),
(
    'Ultrabook',
    'Equipamento com processamento AMD Ryzen5, 12GB de RAM, placa de vídeo RTX',
    4500.68,
    12,
    7 -- Positivo
);

```
<!-- ___________________________________________________________ -->
## Resumo (SELECT)
### Ler dados da tabela produtos
```sql
SELECT * FROM produtos;
SELECT nome, preco FROM produtos;
SELECT nome FROM produtos WHERE preco < 5000;
SELECT nome, descricao FROM produtos WHERE fabricante_id = 3; #Apple
```
### Operadores lógicos: E OU NÂO

```sql
SELECT * FROM produtos WHERE preco >=5000 AND preco < 8000;

-- Consulta nome, preco de produtos da Apple ou Microsoft
SELECT nome, preco FROM produtos WHERE fabricante_id = 3 OR fabricante_id = 8;

-- Monte uma consulta que traga nome, preco, e quantidade
-- de todos os produtos exceto os do fabricante apple
SELECT nome, preco, quantidade FROM produtos WHERE NOT fabricante_id = 3 ;


```