## 1- Faça uma consulta que mostre os alunos que nasceram antes do ano 2009

```sql
SELECT nome, data_nascimento
FROM alunos
WHERE data_nascimento < 2009-01-01;
```


## 2- Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.
```sql
SELECT
    nome AS Nome,
    CAST(((primeira_nota + segunda_nota) / 2) AS DEC(6, 2)) AS Média
FROM alunos;
```

### 3- Faça uma consulta que calcule o limite de faltas de cada curso de acordo com a carga horária. Considere o limite como 25% da carga horária. Classifique em ordem crescente pelo título do curso.

```sql
SELECT titulo, cargaHoraria, 0.25 * cargaHoraria AS 'Limite faltas'
FROM cursos
ORDER BY titulo ASC;
```

### 4) Faça uma consulta que mostre os nomes dos professores que são somente da área "desenvolvimento".

```sql
SELECT nome, area_atuacao
FROM professores
WHERE area_atuacao = 2;
```

### 5) Faça uma consulta que mostre a quantidade de professores que cada área ("design", "infra", "desenvolvimento") possui.


```sql
SELECT area_atuacao,
COUNT(*)
FROM professores
GROUP BY area_atuacao;
```

### 6) Faça uma consulta que mostre o nome dos alunos, o título e a carga horária dos cursos que fazem.

```sql
SELECT alunos.nome, cursos.titulo, cursos.cargaHoraria
FROM alunos
INNER JOIN cursos ON alunos.curso_id = cursos.id
```

### 7) Faça uma consulta que mostre o nome dos professores e o título do curso que lecionam. Classifique pelo nome do professor.


```sql
SELECT professores.nome, cursos.titulo
FROM professores
INNER JOIN cursos ON professores.curso_id = cursos.id
ORDEM by professores.nome;
```

### 8) Faça uma consulta que mostre o nome dos alunos, o título dos cursos que fazem, e o professor de cada curso.

```sql
SELECT alunos.nome, cursos.titulo, professores.nome
FROM alunos
INNER JOIN cursos ON alunos.curso_id = cursos.id
INNER JOIN professores ON professores.curso_id = cursos.id;
```

### 9) Faça uma consulta que mostre a quantidade de alunos que cada curso possui. Classifique os resultados em ordem descrecente de acordo com a quantidade de alunos.

```sql

```

### 10) Faça uma consulta que mostre o nome dos alunos, suas notas, médias, e o título dos cursos que fazem. Devem ser considerados somente os alunos de Front-End e Back-End. Mostre os resultados classificados pelo nome do aluno.

```sql

```

### 11) Faça uma consulta que altere o nome do curso de Figma para Adobe XD e sua carga horária de 10 para 15.

```sql

```

### 12) Faça uma consulta que exclua um aluno do curso de Redes de Computadores e um aluno do curso de UX/UI.

```sql

```

### 13) Faça uma consulta que mostre a lista de alunos atualizada e o título dos cursos que fazem, classificados pelo nome do aluno.

```sql

```