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
  `EqNum` int(4),
  PRIMARY KEY (`PNum`),
  FOREIGN KEY (`EqNum`) references equipe (`EqNum`))
