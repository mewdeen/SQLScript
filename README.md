# SQLScript
CREATE TABLE `student` (
  `StudentID` varchar(20) NOT NULL,
  `LastName` varchar(20) DEFAULT NULL,
  `FirstName` varchar(20) DEFAULT NULL,
  `Age` int(11) DEFAULT NULL,
  `Address` varchar(255) DEFAULT NULL,
  `Gender` varchar(255) DEFAULT NULL,
  `Tel` varchar(30) DEFAULT NULL,
  PRIMARY KEY (`StudentID`)
);
INSERT INTO `student` VALUES 
('M00987695','Ross','Malonda',27,'46 High Road, London','F','02084112345'),
('M00987696','Jaspreet','Kullar',29,'45 The Limes, Stanstead','F','02084113987'),
('M00987697','Ahmed','Ibrahim',34,'56 Callenger Road, London','M','02084114578'),
('M00987698','Uzodinma','Ibenye',26,'35 The Palace, London','F','0208411345'),
('M00987699','Omair','Hussain',40,'67 The Leys, Cambridge','M','02084113456'),
('M00987700','Fathima','Hussain',22,'34 The Burroughs, London','M','0208414567'),
('M00987701','Mohammad','Hresha',20,'45 Reepham Rd, Norfolk','M','0208414538'),
('M00987702','Tamsyn','Hearn',25,'34 stone Road, London','F','0208415678'),
('M00987703','Abdullahi','Hassan',18,'14 York Road, York','M','0120841345'),
('M00987704','Henock','Hailu',37,'24 High Road, London','F','02084113467'),
('M00987705','Begum','Dilara',27,'24 Hills Road, London','F','0208411345'),
('M00987767','Hailu','Henock',45,'','M','');


CREATE TABLE `module` (
  `ModuleID` varchar(7) NOT NULL,
  `ModuleName` varchar(100) DEFAULT NULL,
  `Credit` int(11) DEFAULT NULL,
  `TutorID` varchar(50) DEFAULT NULL,
  PRIMARY KEY (`ModuleID`)
);


INSERT INTO `module` VALUES ('BIS0010','Introduction to Computers in Business',30,'T001'),
('BIS0111','Computer Science Intensive Entry Course',30,'T001'),
('BIS1200','Database Management Systems',30,'T003'),
('BIS1212','Introduction to Business Computing',30,'T003'),
('BIS2111','Computer Science Year 2 English Progress',30,'T004'),
('BIS2212','Database Systems: Design and Online',30,'T004'),
('BIS2216','Forensic Computer Analysis',30,'T005'),
('BIS2218','Decision Support Systems',30,'T005'),
('BIS2311','Object Oriented Analysis and Design',30,'T001'),
('BIS3000','Information Systems and Strategic Management',30,'T005'),
('BIS3051','Commercial Web Design',30,'T002'),
('BIS4435','Data Management for Decision Support',20,'T002'),
('BIS4992','Postgraduate Computing Project',60,'T002');

CREATE TABLE `tutor` (
  `TutorID` varchar(9) NOT NULL,
  `TutorName` text,
  `Campus` text,
  `Gender` text,
  `Salary` double DEFAULT NULL,
  `Tel` varchar(30) DEFAULT NULL,
  `DOB` date DEFAULT NULL,
  `SchoolID` text,
  PRIMARY KEY (`TutorID`)
);

INSERT INTO `tutor` VALUES ('T001','James Brown','Hendon','M',50000,'3456','1979-09-01','S100'),
('T002     ','John Smith','Hendon','M',60000,'6543','1961-05-11','S100'),
('T003     ','Joan Rix','Hendon','F',40000,'6743','1980-01-23','S100'),
('T004     ','Janet Green','Hendon','F',70000,'1298','1960-06-13','S100'),
('T005     ','Brian Francis','Hendon','M',45000,'5612','1980-04-26','S100'),
('T006     ','Siri Bavan','Hendon','M',65000,'8976','1950-02-15','S110'),
('T007     ','Vincent McFadden','Trent Park','M',55000,'7854','1980-10-14','S120'),
('T008     ','Roman Sadler','Hendon','M',55000,'4526','1967-11-29','S130'),
('T009     ','Elli Thome','Hendon','F',65000,'1298','1985-08-23','S130'),
('T010     ','Tami Tuck','Trent Park','F',75000,'4321','1990-03-24','S120');

CREATE TABLE `school` (
  `SchoolID` varchar(4) NOT NULL,
  `SchoolName` varchar(100) DEFAULT NULL,
  `Campus` varchar(20) DEFAULT NULL,
  PRIMARY KEY (`SchoolID`)
) ;
INSERT INTO `school` VALUES ('S100','EIS','Hendon'),
('S110','HSSC','Hendon'),
('S120','Art and Design','Trent Park'),
('S130','Business School','Hendon');
CREATE TABLE `grade` (
  `StudentID` varchar(10) NOT NULL,
  `ModuleID` varchar(50) NOT NULL,
  `Mark` int(11) DEFAULT NULL,
  PRIMARY KEY (`StudentID`,`ModuleID`)
) ;
INSERT INTO `grade` VALUES ('M00987700','BIS0010',60),
('M00987700','BIS0111',50),
('M00987700','BIS1200',90),
('M00987704','BIS0010',80),
('M00987704','BIS0111',10),
('M00987704','BIS1200',90),
('M00987705','BIS0010',60),
('M00987705','BIS1200',70);

Insert into grade (StudentID, ModuleID) values ('M00987699','BIS0010'),
('M00987699','BIS1200'),
('M00987699','BIS0111');
