# PonderadaSemana3

O banco de dados pode ser definido como uma série de dados armazenados e relacionados entre si. Em um banco de dados relacional, cada linha em uma tabela é como um registro único que possui seu próprio número de identificação. Para a construção do banco de dados da atividade ponderada e da entregue no projeto, foi utilizada a ferramenta "SQL Design", segue a imagem:

<div align="center">
<sub>Modelo Relacional Individual</sub>
<img src="/assets/ModeloRelacionalIndividual.png" width="100%" >
</div>
<br>
O arquivo gerado em XML é utilizado para estruturar e armazenar dados em um formato legível por máquina, que pode ser visualizado abaixo:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<!-- SQL XML created by WWW SQL Designer, https://github.com/ondras/wwwsqldesigner/ -->
<!-- Active URL: https://sql.toad.cz/ -->
<sql>
<datatypes db="mysql">
	<group label="Numeric" color="rgb(238,238,170)">
		<type label="Integer" length="0" sql="INTEGER" quote=""/>
	 	<type label="TINYINT" length="0" sql="TINYINT" quote=""/>
	 	<type label="SMALLINT" length="0" sql="SMALLINT" quote=""/>
	 	<type label="MEDIUMINT" length="0" sql="MEDIUMINT" quote=""/>
	 	<type label="INT" length="0" sql="INT" quote=""/>
		<type label="BIGINT" length="0" sql="BIGINT" quote=""/>
		<type label="Decimal" length="1" sql="DECIMAL" re="DEC" quote=""/>
		<type label="Single precision" length="0" sql="FLOAT" quote=""/>
		<type label="Double precision" length="0" sql="DOUBLE" re="DOUBLE" quote=""/>
	</group>

	<group label="Character" color="rgb(255,200,200)">
		<type label="Char" length="1" sql="CHAR" quote="'"/>
		<type label="Varchar" length="1" sql="VARCHAR" quote="'"/>
		<type label="Text" length="0" sql="MEDIUMTEXT" re="TEXT" quote="'"/>
		<type label="Binary" length="1" sql="BINARY" quote="'"/>
		<type label="Varbinary" length="1" sql="VARBINARY" quote="'"/>
		<type label="BLOB" length="0" sql="BLOB" re="BLOB" quote="'"/>
	</group>

	<group label="Date &amp; Time" color="rgb(200,255,200)">
		<type label="Date" length="0" sql="DATE" quote="'"/>
		<type label="Time" length="0" sql="TIME" quote="'"/>
		<type label="Datetime" length="0" sql="DATETIME" quote="'"/>
		<type label="Year" length="0" sql="YEAR" quote=""/>
		<type label="Timestamp" length="0" sql="TIMESTAMP" quote="'"/>
	</group>
	
	<group label="Miscellaneous" color="rgb(200,200,255)">
		<type label="ENUM" length="1" sql="ENUM" quote=""/>
		<type label="SET" length="1" sql="SET" quote=""/>
		<type label="Bit" length="0" sql="bit" quote=""/>
	</group>
</datatypes><table x="642" y="787" name="User">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="firstname" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="surname" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="email" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="password" null="1" autoincrement="0">
<datatype>CHAR</datatype>
<default>NULL</default></row>
<row name="nationality" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="323" y="812" name="Student">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="age" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="gender" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="country_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="phonenumber" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_University" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="University" row="id" />
</row>
<row name="id_User" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="User" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="448" y="618" name="Tutor">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="education_id" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_User" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="User" row="id" />
</row>
<row name="id_University" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="University" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="504" y="997" name="Team">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="teamname" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="id_Student" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Student" row="id" />
</row>
<row name="id_Tutor" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Tutor" row="id" />
</row>
<row name="id_Game" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Game" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="154" y="705" name="University">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="100" y="975" name="Student_Team">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_Student" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Student" row="id" />
</row>
<row name="id_Team" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Team" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="858" y="756" name="Round">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="startdate" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="enddate" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="roundnumber" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_Game" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Game" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1001" y="666" name="Questions">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_Round" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Round" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="792" y="966" name="Game">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="startdate" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="enddate" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="799" y="577" name="Answers">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_Questions" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Questions" row="id" />
</row>
<row name="id_User" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="User" row="id" />
</row>
<row name="Answer" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
</sql>
```

1. Entidade “User”
* “id”(Chave primária da tabela): Identificador único do usuário;
* “firstname”: Primeiro nome do usuário;
* “surname”: Nome completo do usuário;
* “nationality”: Nacionalidade do usuário;
* “email”: Endereço de email do usuário;
* “password”: Senha de acesso definida pelo usuário.


2. Entidade “Student”
* “id”(Chave primária da tabela): Identificador único do estudante;
* “name”: Nome do estudante;
* “age”: Idade do estudante;
* “gender”: Gênero do estudante;
* “country_id”: Id do país do estudante;
* “phonenumber”: Numero de telefone do estudante;
* “id_Univerity” (chave estrangeira da tabela “User”): Referência ao usuário correspondente na tabela “University”;
* “id_User” (chave estrangeira da tabela “User”): Referência ao usuário correspondente na tabela “User”;

3. Entidade “Tutor”
* “id” (Chave Primária da tabela): Identificador único do tutor;
* “education_id”: Referência ao id de educação do tutor;
* “id_user” (chave estrangeira da tabela “User”): Referência ao usuário correspondente na tabela “User”.
* “id_Univerity” (chave estrangeira da tabela “User”): Referência ao usuário correspondente na tabela “University”;


4. Entidade “University”
* “id” (Chave primária da tabela): Identificador único da universidade;
* “name”: Nome da universidade;

5. Entidade “Team”
* “id” (Chave primária da tabela): Identificador único do grupo;
* “teamname”: Nome do time;
* “id_game” (chave estrangeira da tabela “Game”): Referência ao jogo Cesim associado ao grupo;
* “id_student” (chave estrangeira da tabela “Student”): Referência aos estudantes que compõem o grupo;
* “id_tutor” (chave estrangeira da tabela “Tutor”): Referência ao tutor responsável pelo grupo.

6. Entidade “Student_team”
* “id” (Chave primária da tabela): Identificador único da tabela;
* “id_student” (chave estrangeira da tabela “Student”): Referência ao estudante associado ao grupo que está sendo referenciado;
* “id_team” (chave estrangeira da tabela “Team”): Referência à equipe à qual o  estudante está associado.

7. Entidade “Game” 
* “id” (chave primária da tabela): Identificador único do jogo;
* “startdate”: Data de início do jogo;
* “enddate”: Data de término do jogo.

8. Entidade “Round”
* “id” (chave primária da tabela): Identificador único da rodada.
* “startdate”: Data de início da rodada;
* “enddate”: Data de término da rodada;
* “round_number”: Número da rodada;
* “id_Game” (chave estrangeira da tabela “Game”): Referência ao jogo Cesim associado à rodada.

9. Entidade "Questions"
* "id" (chave primária da tabela): Identificador único da pergunta.
* “id_round” (chave estrangeira da tabela “round”): Referência round do jogo.

10. Entidade "Answers"
* "id" (chave primária da tabela): Identificador único da resposta do usuário.
* "answer": Respostas armazenadas
* "id_questions" (chave estrangeira da tabela "Questions"): Referência à pergunta à qual a resposta está associada.
* “id_User” (chave estrangeira da tabela “User”): Referência ao usuário correspondente na tabela “User”;

Para criar todas as entidades e estabelecer suas relações no banco de dados foram empregados comandos SQL. Segue abaixo os comando utilizados:


```sql
-- ---
-- Globals
-- ---

-- SET SQL_MODE="NO_AUTO_VALUE_ON_ZERO";
-- SET FOREIGN_KEY_CHECKS=0;

-- ---
-- Table 'User'
-- 
-- ---

DROP TABLE IF EXISTS `User`;
		
CREATE TABLE `User` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `firstname` MEDIUMTEXT NULL DEFAULT NULL,
  `surname` MEDIUMTEXT NULL DEFAULT NULL,
  `email` MEDIUMTEXT NULL DEFAULT NULL,
  `password` CHAR NULL DEFAULT NULL,
  `nationality` MEDIUMTEXT NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'Student'
-- 
-- ---

DROP TABLE IF EXISTS `Student`;
		
CREATE TABLE `Student` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `name` MEDIUMTEXT NULL DEFAULT NULL,
  `age` INTEGER NULL DEFAULT NULL,
  `gender` MEDIUMTEXT NULL DEFAULT NULL,
  `country_id` INTEGER NULL DEFAULT NULL,
  `phonenumber` INTEGER NULL DEFAULT NULL,
  `id_University` INTEGER NULL DEFAULT NULL,
  `id_User` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'Tutor'
-- 
-- ---

DROP TABLE IF EXISTS `Tutor`;
		
CREATE TABLE `Tutor` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `education_id` INTEGER NULL DEFAULT NULL,
  `id_User` INTEGER NULL DEFAULT NULL,
  `id_University` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'Team'
-- 
-- ---

DROP TABLE IF EXISTS `Team`;
		
CREATE TABLE `Team` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `teamname` MEDIUMTEXT NULL DEFAULT NULL,
  `id_Student` INTEGER NULL DEFAULT NULL,
  `id_Tutor` INTEGER NULL DEFAULT NULL,
  `id_Game` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'University'
-- 
-- ---

DROP TABLE IF EXISTS `University`;
		
CREATE TABLE `University` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `name` MEDIUMTEXT NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'Student_Team'
-- 
-- ---

DROP TABLE IF EXISTS `Student_Team`;
		
CREATE TABLE `Student_Team` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `id_Student` INTEGER NULL DEFAULT NULL,
  `id_Team` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'Round'
-- 
-- ---

DROP TABLE IF EXISTS `Round`;
		
CREATE TABLE `Round` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `startdate` INTEGER NULL DEFAULT NULL,
  `enddate` INTEGER NULL DEFAULT NULL,
  `roundnumber` INTEGER NULL DEFAULT NULL,
  `id_Game` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'Questions'
-- 
-- ---

DROP TABLE IF EXISTS `Questions`;
		
CREATE TABLE `Questions` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `id_Round` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'Game'
-- 
-- ---

DROP TABLE IF EXISTS `Game`;
		
CREATE TABLE `Game` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `startdate` INTEGER NULL DEFAULT NULL,
  `enddate` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'Answers'
-- 
-- ---

DROP TABLE IF EXISTS `Answers`;
		
CREATE TABLE `Answers` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `id_Questions` INTEGER NULL DEFAULT NULL,
  `id_User` INTEGER NULL DEFAULT NULL,
  `Answer` MEDIUMTEXT NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Foreign Keys 
-- ---

ALTER TABLE `Student` ADD FOREIGN KEY (id_University) REFERENCES `University` (`id`);
ALTER TABLE `Student` ADD FOREIGN KEY (id_User) REFERENCES `User` (`id`);
ALTER TABLE `Tutor` ADD FOREIGN KEY (id_User) REFERENCES `User` (`id`);
ALTER TABLE `Tutor` ADD FOREIGN KEY (id_University) REFERENCES `University` (`id`);
ALTER TABLE `Team` ADD FOREIGN KEY (id_Student) REFERENCES `Student` (`id`);
ALTER TABLE `Team` ADD FOREIGN KEY (id_Tutor) REFERENCES `Tutor` (`id`);
ALTER TABLE `Team` ADD FOREIGN KEY (id_Game) REFERENCES `Game` (`id`);
ALTER TABLE `Student_Team` ADD FOREIGN KEY (id_Student) REFERENCES `Student` (`id`);
ALTER TABLE `Student_Team` ADD FOREIGN KEY (id_Team) REFERENCES `Team` (`id`);
ALTER TABLE `Round` ADD FOREIGN KEY (id_Game) REFERENCES `Game` (`id`);
ALTER TABLE `Questions` ADD FOREIGN KEY (id_Round) REFERENCES `Round` (`id`);
ALTER TABLE `Answers` ADD FOREIGN KEY (id_Questions) REFERENCES `Questions` (`id`);
ALTER TABLE `Answers` ADD FOREIGN KEY (id_User) REFERENCES `User` (`id`);

-- ---
-- Table Properties
-- ---

-- ALTER TABLE `User` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `Student` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `Tutor` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `Team` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `University` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `Student_Team` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `Round` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `Questions` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `Game` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `Answers` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;

-- ---
-- Test Data
-- ---

-- INSERT INTO `User` (`id`,`firstname`,`surname`,`email`,`password`,`nationality`) VALUES
-- ('','','','','','');
-- INSERT INTO `Student` (`id`,`name`,`age`,`gender`,`country_id`,`phonenumber`,`id_University`,`id_User`) VALUES
-- ('','','','','','','','');
-- INSERT INTO `Tutor` (`id`,`education_id`,`id_User`,`id_University`) VALUES
-- ('','','','');
-- INSERT INTO `Team` (`id`,`teamname`,`id_Student`,`id_Tutor`,`id_Game`) VALUES
-- ('','','','','');
-- INSERT INTO `University` (`id`,`name`) VALUES
-- ('','');
-- INSERT INTO `Student_Team` (`id`,`id_Student`,`id_Team`) VALUES
-- ('','','');
-- INSERT INTO `Round` (`id`,`startdate`,`enddate`,`roundnumber`,`id_Game`) VALUES
-- ('','','','','');
-- INSERT INTO `Questions` (`id`,`id_Round`) VALUES
-- ('','');
-- INSERT INTO `Game` (`id`,`startdate`,`enddate`) VALUES
-- ('','','');
-- INSERT INTO `Answers` (`id`,`id_Questions`,`id_User`,`Answer`) VALUES
-- ('','','','');
```