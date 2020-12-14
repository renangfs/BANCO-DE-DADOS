CREATE DATABASE NOME_DO_BANCO_DE_DADOS

SELECT * FROM trabalho_av2.equipe

SELECT * FROM EQUIPE<br>
WHERE EQNUM>2


CREATE TABLE `equipe` (
  `EqNum` int(4) NOT NULL AUTO_INCREMENT,
  `EqNome` varchar(50) NOT NULL,
  `EqNacionalidade` varchar(70) NOT NULL,
  PRIMARY KEY (`EqNum`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=latin1


CREATE TABLE `piloto` (
  `PNum` int(6) NOT NULL AUTO_INCREMENT,
  `PNome` varchar(30) NOT NULL,
  `Psexo` char(1),
  `PDtNascimento` varchar(10) NOT NULL,
  `Pnacionalidade` varchar(70) NOT NULL,
  `EqNum` int(4) NOT NULL ,
  PRIMARY KEY (`PNum`),
  FOREIGN KEY (`EqNum`) references equipe (`EqNum`))
  
  
  CREATE TABLE `autodromo` (
  `ANum` int(6) NOT NULL ,
  `ANome` varchar(30) NOT NULL,
  `ACidade` varchar(30) NOT NULL,
  `APais` varchar(30) NOT NULL,
  PRIMARY KEY (`ANum`))
  
  
  CREATE TABLE `corrida` (
  `CNum` int(6) NOT NULL,
  `ANum` int(6) NOT NULL,
  `PNum` int(6) NOT NULL,
  `Data` VARCHAR(10) NOT NULL,
  `Colocacao` int(100) NOT NULL,
  `TempoTotal` int(30) NOT NULL,
  PRIMARY KEY (`CNum`),
  FOREIGN KEY (`ANum`) REFERENCES `autodromo` (`ANum`),
  FOREIGN KEY (`PNum`) REFERENCES `piloto` (`PNum`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1


_______________________________________________________________________
insert into equipe values (4,"SPEED","Egito")

select * from equipe

select Anum,Acidade from autodromo
order by ANum desc

<img src="https://user-images.githubusercontent.com/61218420/101342232-07df7400-3861-11eb-8f44-6783e2a0878c.png" width="500">

<hr>

alter table pessoas<br>
add column profissao varchar(10) AFTER nome;<br>

alter table pessoas<br>
modify column profissao varchar(30);<br>

alter table pessoas<br>
drop column profissao;<br>

desc pessoas<br>

insert into pessoas values <br>
(default,'Ana', '1975-12-22', 'F', '52.3', '1.45', 'EUA'),<br>
(default,'Pedro', '2000-07-15', 'M', '52.3', '1.45', 'Brasil'),<br>
(default,'Maria', '1999-05-30', 'F', '75.9', '1.70', 'Portugal');<br>

select * from pessoas<br>

create database cadastro<br>
default character set utf8<br>
default collate utf8_general_ci;<br>

create table pessoas(<br>
id int not null auto_increment,<br>
nome varchar(30) not null,<br>
nascimento date,<br>
sexo enum('M','F'),<br>
peso decimal(5,2),<br>
altura decimal(3,2),<br>
nacionalidade varchar(20) default 'Brasil',<br>
primary key (id)<br>
)default charset= utf8;<br>
  
