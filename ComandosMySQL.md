SELECT * FROM trabalho_av2.equipe

SELECT * FROM EQUIPE<br>
WHERE EQNUM>2

CREATE TABLE PILOTO(
PNum int(6) not null auto_increment,
PNome varchar(30),
Psexo varchar(1),
PDtNascimento varchar(10),
Pnacionalidade(70)
primary key (PNum)
foreign key (EqNum)
)
