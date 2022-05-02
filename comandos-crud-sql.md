# Comandos SQL para CRUD - Referência

## Resumo 
- C -> Create (Inserir dados)
- R -> Read (Ler dados)
- U -> Update (atualizar dados)
- D -> Delete (excluir Dados)


## INSERT 
### Fabricantes
```sql
o comando pode ser maíusculo ou não. Já os campos precisam ser iguais como foram criados
INSERT INTO fabricantes (nome) VALUES('Asus'); - aceito em aspas simples e crase
INSERT INTO fabricantes (nome) VALUES('Dell');
INSERT INTO fabricantes (nome) 
VALUES ('Apple'), ('LG'), ('Samsung'), ('Brastemp');
```

### Produtos
```sql 
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'Ultrabook', 
    'Ultrabook Asus com processador Intel Core i12
    memória RAN de 16GB e Windows 11', 
    6500.99,
    7, 
    1 
);
```

```sql 
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'Tablet Android', 
   'Tablet com a versão 12 do sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64 GB.', 
    4999,
    3, 
    5 # Samsung 
);
```

```sql
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'Geladeira', 
    'Refrigerador Frost-Free com acesso à internet das Coisas e bla bla bla',
    1500,
    10,
    6 # Brastemp 
),
(
    'iPhone 13 Pro Max',
    'Alta durabilidade, processador Bionic 14, 128 GB de 
    armazenamento, 6 GB de RAM e caro pra caramba', 
    6999.99,
    3,
    3 # Apple
),
(
     'iPad Mini',
    'Tablet Apple com tela retina display de 4k, 
    memória interna de 64GB, acesso ao iCloud.', 
    5000,
    8,
    3 # Apple
);
```







```sql
INSERT INTO fabricantes (nome) VALUES ('Positivo'), ('Microsoft');
```

```sql
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'Xbox',
    'Console de última geração com acesso aos melhores jogos e bla bla',
    2500,
    6,
    8
),
(
    'Ultrabook',
    'Equipamento com processador AMD Ryzen 5, 12GB de RAM, placa de vídeo RTX',
    4500.68,
    12,
    7
);
```


## Select

### Ler dados da tabela produtos
```sql
SELECT * FROM produtos;
SELECT nome, preco FROM produtos;
SELECT preco, nome FROM produtos WHERE preco < 5000;
SELECT nome, descricao FROM produtos WHERE fabricante_id = 3;
```


### Operadores Lógicos: E OU NÃO
```sql
-- Podemos usar também operadores lógicos 
SELECT * FROM produtos
WHERE preco >= 5000 AND preco < 8000;

SELECT nome, preco FROM produtos
-- dos fabricantes apple ou microsoft
WHERE fabricante_id = 3 OR fabricante_id = 8;

-- Monte uma consulta que traga nome, preco e quantidade de todos os produtos excetos da fabricante APPLE

SELECT nome, preco, quantidade FROM produtos WHERE NOT fabricante_id = 3;
```

