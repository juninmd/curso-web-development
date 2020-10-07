https://www.w3schools.com/sql/sql_join.asp
https://i.pinimg.com/originals/c3/33/f5/c333f500174ce2a5b412db86bcd701be.png


create table carro(
	codCarro int(11),
	modelo varchar(40) NOT NULL,
	placa varchar(10),
	cor varchar(30),
	ano datetime 
)

create table seguro(
	codSeguro int(11),
	nroApolice int(11),
	dtValidade datetime,
	codCarro int(11)
)

create table roubo(
	codRoubo int(11),
	dtRoubo datetime,
	localRoubo varchar(30),
	cidadeRoubo varchar(30),
	codCarro int(11)
)

create table recuperacao(
	codRecuperacao int(11),
	dtRecuperacao varchar(30),
	responsavel varchar(50),
	observacao varchar(100),
	codRoubo int(11)
)

--2.	Faça cadastros de 8 Carros
INSERT INTO carro
VALUES
	(null, 'ONIX','GHQ1256','PRATA','2017'),
	(null, 'PALIO','DUI5874','PRETO','2017'),
	(null, 'CIVIC','KZJ8547','CHUMBO','2019'),
	(null, 'COROLA','PDF2563','BRANCO','2008'),
	(null, 'CORSA','KZL8796','VERDE','2000'),
	(null, 'FUSCA','MTK3695','AZUL','1980'),
	(null, 'TEMPRA','NCJ6978','AMARELO','1998')

	

--Faça cadastros de 4 Seguros
set dateformat dmy
INSERT INTO seguro
VALUES
	(null, 1002,'03/09/2020',1),
	(null, 1050,'03/01/2025',2),
	(null, 1095,'20/05/2020',3),
	(null, 1002,'16/03/2021',4)

-- Faça o cadastro de 3 recuperações
insert into recuperacao
values
	(null, '2019-11-19', 'MARIA', 'NENHUMA', 3),
	(null, '2019-10-18', 'MADALENA', 'NENHUMA', 2),
	(null, '2019-08-15', 'MAX', 'NENHUMA', 5)


-- Crie um select que liste os modelos dos carros que foram roubados e não tinham seguro.
select C.codCarro, C.modelo, R.codRoubo, S.codSeguro 
from carro C
	left join seguro S
		on C.codCarro = S.codCarro
		inner join roubo R
		on C.codCarro = R.codCarro where S.codCarro is NULL

-- Crie um select que liste os carros que nunca foram roubados com as informações de seguro para aqueles que tem seguro.
select C.codCarro, C.placa, S.codSeguro, R.codCarro
from carro C
	left join roubo R
    on C.codCarro = R.codCarro 
    inner join seguro S 
    on C.codCarro = S.codCarro 
    where R.codCarro IS NULL

-- Crie uma view que liste os carros que foram roubados em Franca e foram 
-- recuperados. Liste também as observações da recuperação
select C.codCarro, C.placa, R.codroubo, RE.codRecuperacao, RE.observacao
from carro C
	inner join roubo R
    on C.codCarro = R.codCarro
		inner join recuperacao RE