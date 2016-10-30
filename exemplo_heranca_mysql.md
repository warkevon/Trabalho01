# Exemplo de herança em Mysql

##Contexto
Tabela pai:
1. Pessoa (representa a tabela pai)

Tabelas filhas:
1. motorista 
2. especialista

CREATE TABLE pessoa (
nome varchar(100),
rg int,
cod_pessoa int PRIMARY KEY
);

CREATE TABLE motorista (
cnh varchar(100),
cod_pessoa int,
FOREIGN KEY(cod_pessoa) REFERENCES pessoa (cod_pessoa)
);

CREATE TABLE especialista (
especializacao varchar(100),
cod_pessoa int,
FOREIGN KEY(cod_pessoa) REFERENCES pessoa (cod_pessoa)
)


select * from pessoa inner join especialista
on (pessoa.cod_pessoa=especialista.cod_pessoa);

insert into pessoa values ('pedro',1213,1);
insert into motorista values ('cnhpessoa1',1)

insert into pessoa values ('marcos',1245,2);
insert into especialista values ('DBA',2)

insert into pessoa values ('Ana',1545,3);
insert into especialista values ('Programadora',3)

