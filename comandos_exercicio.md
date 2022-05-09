## Comandos CRUD Etapa 2 

```sql
-- Comando para inserção dos cursos e carga horária
INSERT INTO cursos (titulo, cargaHoraria) 
VALUES ('Front-End',
40), 
('Back-End',
80), 
('UX/UI Design',
30), 
('Figma',
10), 
('Redes de Computadores',
100);
```

<!-- INSERT INTO cursos (cargaHoraria) 
VALUES ('40h'), ('80h'), ('30h'), ('10h'), ('100h'); -->

```sql
-- Comando para inserção dos professores na tabela professores
INSERT INTO professores(nome, area_de_atuacao, cursos_id) VALUES ('Jon Oliva',
'Infra',
15
),
('Lemmy Kilmiste',
'Design',
14
),
('Neil Peart'
'Design',
13),
('Ozzy Osbourne',
'Desenvolvimento',
12),
('David Gilmour',
'Desenvolvimento',
11);
```


```sql
INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Marquinhos',
'2001-07-06',
10,
9,
12
);

INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Ricardo',
'1998-07-06',
10,
10,
11
);

INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Ronald',
'1991-05-04',
7,
6,
14
);

INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Leonardo',
'1991-05-04',
3,
4,
13
);

INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Amanda',
'2002-04-01',
8,
7,
11
);

INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Brenda',
'2001-11-18',
10,
10,
12
);

INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Larissa',
'1995-11-05',
8.85,
4.45,
15
);

INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Fernando',
'2003-07-30',
5.50,
7.75,
11
);

INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Washington',
'1998-05-15',
8.35,
7.60,
12
);

INSERT INTO alunos(nome, data_de_nascimento, primeira_nota, segunda_nota,cursos_id) VALUES ('Vinicius',
'1997-08-22',
9.95,
3.75,
14
);
```

