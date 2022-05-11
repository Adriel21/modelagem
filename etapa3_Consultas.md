## Comandos de consulta 

```sql
-- 1)Para consulta de alunos que nasceram antes de data x (usei 2001 porque na minha tabela não há ninguém que nasceu antes em 2009)
SELECT nome, nascimento FROM alunos WHERE nascimento < '2001-01-01';

-- 2)Consulta que demonstra média de cada aluno
SELECT nome, primeira_nota, segunda_nota, (primeira_nota + segunda_nota)/2 AS Média FROM alunos;

-- 3)Consulta de limite de faltas de cada curso de acordo com carga horária. Considerando o limite de como 25%. Ordenado pelo titulo do curso
SELECT titulo, cargaHoraria, (cargaHoraria*0.25) AS 'Limite de faltas' from cursos ORDER BY cursos.titulo;

-- 4) Consulta para identificar nome de professores da área de desenvolvimento

SELECT nome, area_de_atuacao AS Área FROM professores WHERE area_de_atuacao = 'Desenvolvimento';

-- 5) Consulta que mostra a quantidade de professores por área de atuação
SELECT area_de_atuacao AS Área, COUNT(area_de_atuacao) AS 'Quantidade de professores por área' FROM professores GROUP BY area_de_atuacao;

-- 6) Consulta que mostra o nome dos alunos, o curso e a carga horária do curso
SELECT alunos.nome AS Aluno, cursos.titulo AS Curso, cursos.cargaHoraria AS 'Carga Horária' FROM alunos INNER JOIN cursos ON alunos.cursos_id = cursos.id ORDER BY alunos.nome;

-- 7) Consulta do nome do professo e o titulo do curso classificado pelo nome do professor
SELECT professores.nome AS Professores, cursos.titulo AS Curso FROM professores INNER JOIN cursos ON professores.cursos_id = cursos.id ORDER BY professores.nome;

-- 8) Consulta que mostra o nome dos alunos, titulo do cursos e o nome dos respectivos professoes
SELECT alunos.nome, cursos.titulo, professores.nome FROM alunos INNER JOIN cursos ON alunos.cursos_id = cursos.id INNER JOIN professores ON professores.cursos_id = cursos.id;

-- 9) Consulta que mostra quantidade de alunos que cada curso possui, classificando o resultado em ordem descrescente
SELECT COUNT(alunos.cursos_id) AS 'Qtd. de alunos por cursos', cursos.titulo AS Curso FROM alunos INNER JOIN cursos ON alunos.cursos_id = cursos.id GROUP BY cursos.titulo ORDER BY COUNT(alunos.cursos_id)DESC;

SELECT nome, primeira_nota, segunda_nota (primeira_nota+segunda_nota)/2 AS Media, cursos.titulo FROM alunos INNER JOIN cursos ON alunos.cursos_id = cursos.id WHERE alunos.cursos_id = 12 OR alunos.cursos_id = 11 ORDER BY nome;
```

