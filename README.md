# Filtragem e Classificacao MySQL 🐬

https://github.com/luishenriquebk/mysql_filtragem_classificacao/assets/102004702/3cfabdfa-25e2-4363-9b56-90e7a0f9d32b

Este repositório contém atividades realizadas no MySQL para praticar conceitos de classificação e filtragem entre os registros de uma banco de dados no MySQL.
#### Link do projeto: 
https://drive.google.com/drive/folders/1ENTqYL57y2Qi_HIz-sIPysClmgLHHxaw?usp=sharing

## Atividades Realizadas:

Antes de iniciar as atividades devemos criar o DATABASE ao qual vamos usar nesse projeto introdutório:

```sql
CREATE DATABASE IF NOT EXISTS filtragem_classficacao;
USE filtragem_classficacao;
```

Agora vamos criar e preencher nossa tabela com alguns registros?

```sql
CREATE TABLE EMPREGADOS(
	ID_EMPREGADO INT PRIMARY KEY AUTO_INCREMENT,
    NOME_EMPREGADO VARCHAR(100) NOT NULL,
    SEXO VARCHAR(1),
    ENDERECO VARCHAR(100) NOT NULL,
    NUMERO INT
);

INSERT INTO EMPREGADOS(NOME_EMPREGADO, SEXO, ENDERECO, NUMERO)
VALUES
('ALVARO', 'M', 'AEROPORTO', 50),
('ARTHUR', 'M', 'BUZIOS', 112),
('ANNA LARA', 'F', 'RIO GRANDE DO SUL', 120),
('LUIS HENRIQUE', 'M', 'RIO GRANDE DO NORTE', 130),
('ROBERTO', 'M', 'BUZIOS', 70),
('BRUNA', 'F', 'PRAIA DA COSTA', 65),
('RAFAELA', 'F', 'ITAPUA', 72),
('GILBERTO', 'M', 'ITAPUA', 130);

| id_empregado | nome_empregado | sexo | endereco            | numero |
| 1            | ALVARO         | M    | AEROPORTO           | 50     |
| 2            | ARTHUR         | M    | BUZIOS              | 100    |
| 3            | ANNA LARA      | F    | RIO GRANDE DO SUL   | 120    |
| 4            | LUIS HENRIQUE  | M    | RIO GRANDE DO NORTE | 130    |
| 5            | ROBERTO        | M    | BUZIOS              | 70     |
| 6            | BRUNA          | F    | PRAIA DA COSTA      | 65     |
| 7            | RAFAELA        | F    | ITAPUA              | 72     |
| 8            | GILBERTO       | M    | ITAPUA              | 130    |
```
### 1. Selecione todos os registros onde uma coluna específica tem um valor específico:

Para selecionar todos os registro de uma coluna específica que contenha um valor específico da tabela `EMPREGADOS`, foi feita a seguinte consulta:

```sql
SELECT * FROM EMPREGADOS -- SELECIONANDO TODOS OS EMPREGADOS DE GENERO MASCULINO;
WHERE SEXO = 'M';

| id_empregado | nome_empregado | sexo | endereco            | numero |
| 1            | ALVARO         | M    | AEROPORTO           | 50     |
| 2            | ARTHUR         | M    | BUZIOS              | 100    |
| 4            | LUIS HENRIQUE  | M    | RIO GRANDE DO NORTE | 130    |
| 5            | ROBERTO        | M    | BUZIOS              | 70     |
| 8            | GILBERTO       | M    | ITAPUA              | 130    |
```

### 2. Selecione os registros que correspondem a uma condição envolvendo operadores lógicos:

Para selecionar esses registros utilizando operadores lógicos para a consulta foi usado o seguinte comando:

```sql
SELECT * FROM EMPREGADOS -- SELECIONANDO TODOS OS EMPREGADOS SÃO DO GENERO 'M' E QUE MORAM EM 'BUZIOS';
WHERE SEXO = 'M' AND ENDERECO = 'BUZIOS';

| id_empregado | nome_empregado | sexo | endereco | numero |
| 2            | ARTHUR         | M    | BUZIOS   | 100    |
| 5            | ROBERTO        | M    | BUZIOS   | 70     |
```

### 3. Selecione registros ordenados por uma coluna específica em ordem ascendente:

Para realizar essa conusulta foram realizados os seguintes comandos:

```sql
SELECT * FROM EMPREGADOS -- SELECIONANDO TODOS OS EMPREGADOS DE ACORDO COM O NUMERO DE RESINDECIA NA ORDEM ASCENDENTE DE NUMEROS;
ORDER BY NUMERO ASC;

| id_empregado | nome_empregado | sexo | endereco            | numero |
| 1            | ALVARO         | M    | AEROPORTO           | 50     |
| 6            | BRUNA          | F    | PRAIA DA COSTA      | 65     |
| 7            | RAFAELA        | F    | ITAPUA              | 72     |
| 5            | ROBERTO        | M    | BUZIOS              | 70     |
| 2            | ARTHUR         | M    | BUZIOS              | 100    |
| 3            | ANNA LARA      | F    | RIO GRANDE DO SUL   | 120    |
| 4            | LUIS HENRIQUE  | M    | RIO GRANDE DO NORTE | 130    |
| 8            | GILBERTO       | M    | ITAPUA              | 130    |
```

### 4. Faça uma consulta com uma condição utilizando operadores lógicos e realizando uma classificação decrescente:

Para realizar esse tipo de consulta foi executado o seguinte comando:

```sql
SELECT * FROM EMPREGADOS -- SELECIONANDO TODOS OS EMPREGADOS COM A CONDICAO DE SEREM DO SEXO 'F' ORDENANDO DE FORMA DESCENDEMTE O NUMERO RESINDECIAL;
WHERE SEXO = 'F'
ORDER BY NUMERO DESC;

| id_empregado | nome_empregado | sexo | endereco           | numero |
| 3            | ANNA LARA      | F    | RIO GRANDE DO SUL  | 120    |
| 7            | RAFAELA        | F    | ITAPUA             | 72     |
| 6            | BRUNA          | F    | PRAIA DA COSTA     | 65     |
```
