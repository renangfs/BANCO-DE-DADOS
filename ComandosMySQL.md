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
  
