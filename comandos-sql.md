# Comandos SQL - Referência

 ## Modelagem Física

 ### Criar banco de dados

 ```sql
 CREATE DATABASE vendas CHARACTER SET utf8mb4;
 ```

 ### Criar tabela fabricantes

 ```sql
 CREATE TABLE fabricantes(
     id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
     nome VARCHAR(45) NOT NULL
 );
 ```

### Visualizar detalhes estruturais da tabela
```sql
DESC fabricantes;
```

```sql
CREATE TABLE produtos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(1000) NOT NULL,
    preco DECIMAL(6,2) NOT NULL,
    fabricante_id INT NOT NULL
);
```

### Criação da chave estrangeira (relacionamento entre as tabelas)
```sql
ALTER TABLE produtos
    # CONSTRAINT é uma restrição definida no relacionamento
    ADD CONSTRAINT fk_produtos_fabricantes
        # A chave estrangeira deve fazer referência à chave primária
    FOREIGN KEY (fabricante_id) REFERENCES fabricantes(id);
```

### Comando de SQL para adicionar mais um campo/coluna em uma tabela com esse comando é possivel manipular com comandos (ADD, REMOVE, RENAME, CHANGE)
```sql
ALTER TABLE produtos ADD fabricante_id INT NOT NULL AFTER preco;
```



ALTER TABLE professores
    # CONSTRAINT é uma restrição definida no relacionamento
    ADD CONSTRAINT fk_professores_cursos
        # A chave estrangeira deve fazer referência à chave primária
    FOREIGN KEY (cursos_id) REFERENCES cursos(id);