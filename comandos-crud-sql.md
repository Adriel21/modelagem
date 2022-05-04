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

SELECT nome, preco FROM produtos WHERE fabricante_id IN(3, 8); -- Usando função lista
```

 ### Filtros 
 ```sql
 -- Para fazer busca de valores na tabela
 SELECT nome, preco FROM produtos ORDER BY nome; -- Padrão do order by é ordem crescente ASC
 SELECT nome, preco FROM produtos ORDER BY nome DESC; -- Ordem Descrecente
 SELECT nome, descricao FROM produtos WHERE descricao LIKE '%processador%'; -- Like (COMO) e operador coringa % *Pesquisar sobre operador curinga

 -- % Operador coringa (Significa QUALQUER TEXTO)
 ```


 ### Operações e Funções de agregação
 ```sql
 SELECT SUM(preco) FROM produtos; -- SOMA - Traz o resultado da soma de todos os textos
 SELECT SUM(preco) AS TOTAL FROM produtos; -- ALIAS (APELIDO)

 SELECT SUM(quantidade) AS "Quantidade em Estoque" FROM produtos; -- se for mais de uma palavra, é necessário aspas

 *CTRL + SHIFT + ENTER PARA EXECUTAR DIRETO O COMANDO SQL* - Anotação aleatória

 SELECT SUM(quantidade) AS "Quantidade em Estoque" FROM produtos WHERE fabricante_id = 3; -- APPLE

 SELECT AVG(preco) AS "Média dos Preços" FROM produtos; -- AVG (AVERAGE) MÉDIA
  SELECT ROUND(AVG(preco), 3) AS "Média dos Preços" FROM produtos; -- ROUND - para arredondar. Podemos também passar o parâmetro para identificar a quantidade de casas decimais

-- COUNT (Contagem)
 SELECT COUNT(id) AS "Quantidade de Produtos" FROM produtos; -- Conta quantas informações há de acordo com o parâmetro
 SELECT COUNT(fabricante_id) AS "Quantidade de Fabricantes" FROM produtos;

  SELECT COUNT(DISTINCT fabricante_id) AS "Quantidade de Fabricantes" FROM produtos; -- Comando DISTINCT identifica quais resultados se repetem e retorna somente os valores que não assumem repetição. Comando para evitar duplicidade de contagem de campos que não são chave-primária
 ```




 -- anotação aleatória de código de inserção que fora feita manualmente no php admin

 INSERT INTO `produtos` (`id`, `nome`, `descricao`, `preco`, `quantidade`, `fabricante_id`) VALUES (NULL, 'Teclado Gamer ', 'Teclado de última geração com teclas quânticas e mecânicas ótimo tempo de resposta e led embutido.', '380', '8', '8'), (NULL, 'Placa mãe ', 'Placa com diversos slots de memória RAM DDR6, suporte a processadores modernos Intel linha CORE i5 e i7 e também AMD.', '1200', '5', '1') 
 --


