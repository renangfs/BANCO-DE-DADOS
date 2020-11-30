Seja o esquema lógico relacional abaixo:
Equipe (EqNum, EqNome, EqNacionalidade)
Tabela contendo os dados sobre as equipes de fórmula 1, identificadas por números distintos, contendo um nome e uma nacionalidade.
Exemplo: (E13, Ferrari, Italiana).
Piloto (PNum, PNome, Psexo, PDtNascimento, Pnacionalidade, EqNum)
Tabela contendo os dados sobre pilotos de fórmula 1, identificados por números distintos, contendo um nome, sexo, data de nascimento, uma nacionalidade e a equipe pela qual o piloto está correndo na temporada.
Exemplo: (P072, ‘Rubens Barrichello’, M, ‘13/09/72’, Brasileira, E13).
Autódromo (ANum, ANome, ACidade, APaís)
Tabela contendo os dados sobre os autódromos, identificados por números distintos, contendo um nome, a cidade e o país onde está localizado.
Exemplo: (A09, Interlagos, São Paulo, Brasil).
Corrida (CNum, ANum, Pnum, Data, Colocação, TempoTotal)
Tabela contendo os dados sobre as corridas, identificados pelo número da corrida, pelo número do autódromo e pelo número do piloto, contendo a data da corrida, a colocação do piloto e o tempo total gasto na corrida (em minutos).
Exemplo: (99, A09, P072, ‘13/03/2000’, 03, 97).

Especifique as consultas usando a linguagem SQL.
1. Liste as diferentes nacionalidades das equipes (sem repeti-las).
2. Liste o nome dos pilotos que já conquistaram em algum momento já venceram uma corrida (primeira colocação).
3. Liste o nome do piloto e o nome de sua respectiva equipe.
4. Liste o nome dos autódromos da Austrália.
5. Liste o nome do piloto cuja nacionalidade é Italiana.
6. Liste os Pilotos que pertencem a equipe Ferrari.
7. Qual foi o tempo de corrida mais longa?
8. Quantos pilotos são do sexo masculino?
9. Liste o nome e nacionalidade dos pilotos cujo nome começam com a Letra R.
10. Liste o nome do Autódromo da corrida realizada no dia 29/07/2018.

CREATE TABLE equipe (<br>
  EqNum int(4) NOT NULL AUTO_INCREMENT,<br>
  EqNome varchar(50) NOT NULL,<br>
  EqNacionalidade varchar(70) NOT NULL,<br>
  PRIMARY KEY (EqNum)<br>
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=latin1


CREATE TABLE piloto (<br>
  PNum int(6) NOT NULL AUTO_INCREMENT,<br>
  PNome varchar(30) NOT NULL,<br>
  Psexo char(1),<br>
  PDtNascimento varchar(10) NOT NULL,<br>
  Pnacionalidade varchar(70) NOT NULL,<br>
  EqNum int(4) NOT NULL ,<br>
  PRIMARY KEY (PNum),<br>
  FOREIGN KEY (EqNum) references equipe (EqNum))
  
  
  CREATE TABLE autodromo (<br>
  ANum int(6) NOT NULL ,<br>
  ANome varchar(30) NOT NULL,<br>
  ACidade varchar(30) NOT NULL,<br>
  APais varchar(30) NOT NULL,<br>
  PRIMARY KEY (ANum))
  
  
  CREATE TABLE corrida <br>
  CNum int(6) NOT NULL,<br>
  ANum int(6) NOT NULL,<br>
  PNum int(6) NOT NULL,<br>
  Data VARCHAR(10) NOT NULL,<br>
  Colocacao int(100) NOT NULL,<br>
  TempoTotal int(30) NOT NULL,<br>
  PRIMARY KEY (CNum),<br>
  FOREIGN KEY (ANum) REFERENCES autodromo (ANum),<br>
  FOREIGN KEY (PNum) REFERENCES piloto (PNum)v
) ENGINE=InnoDB DEFAULT CHARSET=latin1




