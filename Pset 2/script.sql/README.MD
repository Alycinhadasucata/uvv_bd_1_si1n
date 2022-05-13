Relatório 1 

SELECT numero_departamento AS departamento, AVG(salario) AS media salarial 
FROM funcionario 
GROUP BY numero_departamento;


Relatório 2 

SELECT AVG(salario) , funcionario.sexo 
FROM funcionario
GROUP BY sexo;


Relatório 3

SELECT d.nome_departamento AS departamento , CONCAT(f.primeiro_nome,' ',f.nome_meio,'
',f.ultimo_nome) AS nome_completo, data_nascimento,
 TIMESTAMPDIFF(YEAR,data_nascimento,NOW()) AS idade
 FROM departamento d
INNER JOIN funcionario f on (f.numero_departamento = d.numero_deprtamanto)
ORDER BY d.nome_departamento;
       


Relatório 4 
SELECT CONCAT(f.primeiro_nome,' ',f.nome_meio,' ',f.ultimo_nome) EXTRACT( year from age 
(data_nascimento)) AS idade , salario AS salario_atual,
CASE WHEN salario > 35000.00 THEN salario * 1.2
WHEN salario <=35000.00 THEN salario * 1.15
END AS reajuste
FROM funcionario;

Relatório 5 

SELECT nome_departamento AS departamento, CONCACT(f.priemiro_nome,' ',f.nome_meio,' ',f.ultimo_nome) 
AS nome_completo, 
CASE WHEN d.numero_departamento = 1 THEN 'Jorge'
WHEN d.numero_departamento = 4 THEN 'Jennifer'
WHEN d.numero_departamento = 5 THEN ' Fernando'
FROM funcionario 
INNER JOIN departamento on (f.numero_departamento = d.numero_deparatamento);


Relatório 6 

SELECT CONCAT(f.primeiro_nome,' ',f.nome-meio,' ',f.ultimo_nome) AS nome completo,
d.nome_departamento AS departamento,
CONCAT(nome_dependente', ,'ultimo_nome) AS 'nome dependente',
TIMESTAMPDIFF(YEAR dp.data_nascimento NOW()) AS idade_dependente,
CASE WHEN dp.sexo ='m' THEN 'masculino
WHEN dp.sexo = 'f' THEN 'feminino'
END as sexo
FROM dependente AS de, funcionario AS f, dempartamento AS da
WHERE de.cpf_funcionario = f.cpf END f.numero_deprtamento = da.numero_departamento;

Relatório 7 

SELECT CONCAT(f.primeiro_nome', ,'f.nome_meio', ,'f.ultimo_nome) AS nome_completo,
FROM funcionario
WHEREcpf_surpevisor IS NULL;

Relatório 8 
SELECT nome_departamento, nome_projeto, primeiro_nome, 
noem_meio,ultimo_nome
FROM funcionario,departamento,projeto,trabalha_em
WHERE funcionario.cpf = trabalha_em.cpf_funcioanrio ENd
trabalha_em.numero_projeto = projeto.numero_projeto


Relatório 9

SELECT nome_projeto,nome_departamento, SUM(horas) AS toal_horas
FROM deprtamento,trabalha_em, projeto

Relatório 10

SELECT f.numero_departamento AS departamento,
AVG(f.salario) AS salario_medio
FROM funcioanrio f
WHERE f.numero_depratamento = f.numero_departamento
GROUP BY departamento;

Relatório 11
CONCAT primeiro_nome, nome_meio, ultimo_nome, p.nome_projeto, horas * 50
AS valor_total_ das_horas
FROM funcionario JOIN projeto AS p
JOIN trabalha_em AS t ON (p.numero_projeto = t.numero_projeto)
WHERE funcionario.cpf = t.cpf_funcioanrio;

Relatório 12 

SELECT nome_projeto, primeiro_nome, nome_departamento
FROM projeto, trabalha_em, funcionario, departamento
WHERE trabalha_em.horas is null and trabalha_em.numero_projeto = projeto.numero_projeto and departamento.numero_departamento
= projeto.numero_departamento;

Relatório 13

SELECT CONCAT(primeiro_nome', ,'nome_meio', ,'ultimo_nome) AS nome, sexo
TIMESTAMPDIFF(YEAR,data_nascimento,NOW()) AS idade
FROM funcionario
UNION
SELECT CONCAT(noem_dependente', ,'ultimo_nome), dpdt sexo
TIMESTAMPDIFF(YEAR, dpdt.data_nascimento,NOW())
FROM dependente dpdt
INNER JOIN funcioanrio func ON func.cpf = dpdt.cpf_funcionario
ORDER BY idade;

Relatório 14 

SELECT departamento.nomenome_departamento, funcionario.numero_departamento, COUNT(cpf)
AS qtde_por_departamento
FROM departamento JOIN funcioanrio ON (funcionario.numero_departamento = departamento.numero_departamento
)
GOUP BY numero_departamento

Relatório 15

SELECT f.primeiro_nome, f.nome_meio, f.ultimo_nome, d.nome_departamento, p.nome_projeto
FROM funcionario f 
INNER JOIN departamento d ON (d.cpf_gerente = f.cpf)
INNER JOIN trabalha_em t ON (t.cpf_funcionario = f.cpf)
INNER JOIN projeto p ON (p.numero_projeto = numero_projeto);
