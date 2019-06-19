# HappyFeet-MySQL-CommandLine-dB-
" Hungry ? Forgot to buy Groceries ? Need some medicines? Connect with HappyFeet and get your needs served!! Built using MySQL command-line.
# IMPLEMENTATION 
(In MySQL Command-line)

mysql: [Warning] C:\Program Files\MySQL\MySQL Server 5.7\bin\mysql.exe: ignoring option '--no-beep' due to invalid value ''
Enter password: *****
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 6
Server version: 5.7.21-log MySQL Community Server (GPL)

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| happyfeet          |
| kr_db              |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
6 rows in set (0.00 sec)

mysql> use happyfeet;
Database changed
mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| customers           |
+---------------------+
1 row in set (0.00 sec)

mysql> describe customersl
    -> describe customers;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'describe customers' at line 2
mysql> select * from customers;
Empty set (0.00 sec)

mysql> INSERT INTO `customers` (`cid`, `name`, `email`, `pwd`, `phno`, `address`) VALUES(1, 'kriti', 'kriti@gmail.com', 'pwd', 2147483647, 'street no 5, house no 81, ocean valley'),(2, 'sarita', 'sarita@gmail.com', 'pwd', 2147483647, 'street no 5, house no 81, ocean valley'),(3, 'ameya', 'ameya@gmail.com', 'pwd', 2147483647, 'street no 5, house no 81, ocean valley'),(4, 'tushali', 'tushali@gmail.com', 'pwd', 2147483647, 'street no 5, house no 81, ocean valley'),(5, 'zeel', 'zeel@gmail.com', 'pwd', 2147483647, 'street no 5, house no 81, ocean valley');
Query OK, 5 rows affected (0.00 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> describe customers;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| cid     | int(11)     | NO   |     | NULL    |       |
| name    | varchar(30) | YES  |     | NULL    |       |
| email   | varchar(30) | YES  |     | NULL    |       |
| pwd     | varchar(30) | YES  |     | NULL    |       |
| phno    | int(11)     | YES  |     | NULL    |       |
| address | text        | NO   |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
6 rows in set (0.00 sec)

mysql> select * from customers;
+-----+---------+-------------------+------+------------+----------------------------------------+
| cid | name    | email             | pwd  | phno       | address                                |
+-----+---------+-------------------+------+------------+----------------------------------------+
|   1 | kriti   | kriti@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   2 | sarita  | sarita@gmail.com  | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   3 | ameya   | ameya@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   4 | tushali | tushali@gmail.com | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   5 | zeel    | zeel@gmail.com    | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
+-----+---------+-------------------+------+------------+----------------------------------------+
5 rows in set (0.00 sec)

mysql> create table employee(
    -> eid int(11) NOT NULL,
    -> name varchar(30) default not null,
    -> phno int(15) default null
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'not null,
phno int(15) default null
)' at line 3
mysql> create table employee(
    -> eid int(11) NOT NULL,
    -> name varchar(30) DEFAULT NOT NULL,
    -> phno int(15) DEFAULT NULL
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'NOT NULL,
phno int(15) DEFAULT NULL
)' at line 3
mysql> create table employee(
    -> eid int(11) NOT NULL,
    -> name varchar(30) DEFAULT NULL,
    -> phno int(15) DEFAULT NULL
    -> );
Query OK, 0 rows affected (0.03 sec)

mysql> insert into employee(eid,name,phno)values
    -> (2, 'emp1', 987654321),(3, 'emp2', 987654321),(4, 'emp3', 987654321),(5, 'emp4', 987654321),(6, 'emp5', 987654321);
Query OK, 5 rows affected (0.02 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> create table orders(
    -> oid int(11) not null,
    -> pid int(11) default not null,
    -> cid int(11) default ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'not null,
cid int(11) default' at line 3
mysql> create table orders(
    -> oid int(11) not null,
    -> pid int(11) default null,
    -> cid int(11) default null,
    -> odate datetime default null,
    -> quantity int(11) default null,
    -> deliverystatus tinyint(1) not null
    -> );
Query OK, 0 rows affected (0.03 sec)

mysql> create table products(
    -> pid int(11) not null,
    -> name varchar(20) default not null,
    -> description text,
    -> price double(10,5) default null
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'not null,
description text,
price double(10,5) default null
)' at line 3
mysql> create table products(
    -> pid int(11) not null,
    -> name varchar(20) default null,
    -> price double(10,5) default null,
    -> description text;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 5
mysql> create table products(
    -> pid int(11) not null,
    -> name varchar(20) default null,
    -> description text;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 4
mysql> create table products(
    -> pid int(11) not null,
    -> name varchar(20) default null,
    -> description text,
    -> price float(10,5) default null
    -> );
Query OK, 0 rows affected (0.03 sec)

mysql> INSERT INTO `products` (`pid`, `name`, `description`, `price`) VALUES(1, 'dosa', 'dosa', 10.50000),(2, 'idly', 'idly', 12.50000),(3, 'vada', 'vada', 13.50000),(4, 'upma', 'upma', 14.50000),(5, 'chapati', 'chapati', 15.50000);
Query OK, 5 rows affected (0.03 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> create table vehicles(
    -> vid int(11) not null,
    -> vehiclenumber varchar(30) default null,
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ')' at line 4
mysql> create table vehicles(
    -> vid int(11) not null,
    -> vehiclenumber varchar(30) default null
    -> );
Query OK, 0 rows affected (0.03 sec)

mysql> ALTER TABLE `customers`  ADD PRIMARY KEY (`cid`);---- Indexes for table `employee`--ALTER TABLE `employee`  ADD PRIMARY KEY (`eid`);---- Indexes for table `orders`--ALTER TABLE `orders`  ADD PRIMARY KEY (`oid`);---- Indexes for table `products`--ALTER TABLE `products`  ADD PRIMARY KEY (`pid`);---- Indexes for table `vehicles`--ALTER TABLE `vehicles`  ADD PRIMARY KEY (`vid`);
Query OK, 0 rows affected (0.09 sec)
Records: 0  Duplicates: 0  Warnings: 0

    -> describe customers;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| cid     | int(11)     | NO   | PRI | NULL    |       |
| name    | varchar(30) | YES  |     | NULL    |       |
| email   | varchar(30) | YES  |     | NULL    |       |
| pwd     | varchar(30) | YES  |     | NULL    |       |
| phno    | int(11)     | YES  |     | NULL    |       |
| address | text        | NO   |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
6 rows in set (0.00 sec)

mysql> describe employee;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| eid   | int(11)     | NO   |     | NULL    |       |
| name  | varchar(30) | YES  |     | NULL    |       |
| phno  | int(15)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> describe orders;
+----------------+------------+------+-----+---------+-------+
| Field          | Type       | Null | Key | Default | Extra |
+----------------+------------+------+-----+---------+-------+
| oid            | int(11)    | NO   |     | NULL    |       |
| pid            | int(11)    | YES  |     | NULL    |       |
| cid            | int(11)    | YES  |     | NULL    |       |
| odate          | datetime   | YES  |     | NULL    |       |
| quantity       | int(11)    | YES  |     | NULL    |       |
| deliverystatus | tinyint(1) | NO   |     | NULL    |       |
+----------------+------------+------+-----+---------+-------+
6 rows in set (0.00 sec)

mysql> alter table employee
    -> add primary key(eid);
Query OK, 0 rows affected (0.09 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> alter table orders
    -> add primary key(oid);
Query OK, 0 rows affected (0.05 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> alter table products
    -> add primary key(pid);
Query OK, 0 rows affected (0.09 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> alter table vehicles
    -> add primary key(vid);
Query OK, 0 rows affected (0.04 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> ALTER TABLE `customers`  MODIFY `cid` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=6;
Query OK, 5 rows affected (0.06 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> ALTER TABLE `employee`  MODIFY `eid` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=7;
Query OK, 5 rows affected (0.31 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> ALTER TABLE `orders`  MODIFY `oid` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=20;
Query OK, 0 rows affected (0.05 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> ALTER TABLE `products`  MODIFY `pid` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=6;
Query OK, 5 rows affected (0.04 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> ALTER TABLE `vehicles`  MODIFY `vid` int(11) NOT NULL AUTO_INCREMENT;
Query OK, 0 rows affected (0.05 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> describe customers;
+---------+-------------+------+-----+---------+----------------+
| Field   | Type        | Null | Key | Default | Extra          |
+---------+-------------+------+-----+---------+----------------+
| cid     | int(11)     | NO   | PRI | NULL    | auto_increment |
| name    | varchar(30) | YES  |     | NULL    |                |
| email   | varchar(30) | YES  |     | NULL    |                |
| pwd     | varchar(30) | YES  |     | NULL    |                |
| phno    | int(11)     | YES  |     | NULL    |                |
| address | text        | NO   |     | NULL    |                |
+---------+-------------+------+-----+---------+----------------+
6 rows in set (0.00 sec)

mysql> describe employee;
+-------+-------------+------+-----+---------+----------------+
| Field | Type        | Null | Key | Default | Extra          |
+-------+-------------+------+-----+---------+----------------+
| eid   | int(11)     | NO   | PRI | NULL    | auto_increment |
| name  | varchar(30) | YES  |     | NULL    |                |
| phno  | int(15)     | YES  |     | NULL    |                |
+-------+-------------+------+-----+---------+----------------+
3 rows in set (0.00 sec)

mysql> describe orders;
+----------------+------------+------+-----+---------+----------------+
| Field          | Type       | Null | Key | Default | Extra          |
+----------------+------------+------+-----+---------+----------------+
| oid            | int(11)    | NO   | PRI | NULL    | auto_increment |
| pid            | int(11)    | YES  |     | NULL    |                |
| cid            | int(11)    | YES  |     | NULL    |                |
| odate          | datetime   | YES  |     | NULL    |                |
| quantity       | int(11)    | YES  |     | NULL    |                |
| deliverystatus | tinyint(1) | NO   |     | NULL    |                |
+----------------+------------+------+-----+---------+----------------+
6 rows in set (0.01 sec)

mysql> desscribe products;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'desscribe products' at line 1
mysql> describe products;
+-------------+-------------+------+-----+---------+----------------+
| Field       | Type        | Null | Key | Default | Extra          |
+-------------+-------------+------+-----+---------+----------------+
| pid         | int(11)     | NO   | PRI | NULL    | auto_increment |
| name        | varchar(20) | YES  |     | NULL    |                |
| description | text        | YES  |     | NULL    |                |
| price       | float(10,5) | YES  |     | NULL    |                |
+-------------+-------------+------+-----+---------+----------------+
4 rows in set (0.00 sec)

mysql> describe vehicles;
+---------------+-------------+------+-----+---------+----------------+
| Field         | Type        | Null | Key | Default | Extra          |
+---------------+-------------+------+-----+---------+----------------+
| vid           | int(11)     | NO   | PRI | NULL    | auto_increment |
| vehiclenumber | varchar(30) | YES  |     | NULL    |                |
+---------------+-------------+------+-----+---------+----------------+
2 rows in set (0.01 sec)
mysql> select * from customers;
+-----+---------+-------------------+------+------------+----------------------------------------+
| cid | name    | email             | pwd  | phno       | address                                |
+-----+---------+-------------------+------+------------+----------------------------------------+
|   1 | kriti   | kriti@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   2 | sarita  | sarita@gmail.com  | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   3 | ameya   | ameya@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   4 | tushali | tushali@gmail.com | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   5 | zeel    | zeel@gmail.com    | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
+-----+---------+-------------------+------+------------+----------------------------------------+
5 rows in set (0.00 sec)

mysql> select * from employee;
+-----+------+-----------+
| eid | name | phno      |
+-----+------+-----------+
|   2 | emp1 | 987654321 |
|   3 | emp2 | 987654321 |
|   4 | emp3 | 987654321 |
|   5 | emp4 | 987654321 |
|   6 | emp5 | 987654321 |
+-----+------+-----------+
5 rows in set (0.00 sec)

mysql> select * from products;
+-----+---------+-------------+----------+
| pid | name    | description | price    |
+-----+---------+-------------+----------+
|   1 | dosa    | dosa        | 10.50000 |
|   2 | idly    | idly        | 12.50000 |
|   3 | vada    | vada        | 13.50000 |
|   4 | upma    | upma        | 14.50000 |
|   5 | chapati | chapati     | 15.50000 |
+-----+---------+-------------+----------+
5 rows in set (0.00 sec)

mysql> select * from vehicles;





_____________________________
_______________________________
___________________________
Enter password: *****
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2
Server version: 5.7.21-log MySQL Community Server (GPL)

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| happyfeet          |
| kr_db              |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
6 rows in set (0.01 sec)

mysql> use happyfeet;
Database changed
mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| customers           |
| employee            |
| orders              |
| products            |
| vehicles            |
+---------------------+
5 rows in set (0.00 sec)

mysql> select * from customers;
+-----+---------+-------------------+------+------------+----------------------------------------+
| cid | name    | email             | pwd  | phno       | address                                |
+-----+---------+-------------------+------+------------+----------------------------------------+
|   1 | kriti   | kriti@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   2 | sarita  | sarita@gmail.com  | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   3 | ameya   | ameya@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   4 | tushali | tushali@gmail.com | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   5 | zeel    | zeel@gmail.com    | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
+-----+---------+-------------------+------+------------+----------------------------------------+
5 rows in set (0.02 sec)

mysql> select * from employee;
+-----+------+-----------+
| eid | name | phno      |
+-----+------+-----------+
|   2 | emp1 | 987654321 |
|   3 | emp2 | 987654321 |
|   4 | emp3 | 987654321 |
|   5 | emp4 | 987654321 |
|   6 | emp5 | 987654321 |
+-----+------+-----------+
5 rows in set (0.01 sec)

mysql> select * from orders;
Empty set (0.01 sec)

mysql> select * from products;
+-----+---------+-------------+----------+
| pid | name    | description | price    |
+-----+---------+-------------+----------+
|   1 | dosa    | dosa        | 10.50000 |
|   2 | idly    | idly        | 12.50000 |
|   3 | vada    | vada        | 13.50000 |
|   4 | upma    | upma        | 14.50000 |
|   5 | chapati | chapati     | 15.50000 |
+-----+---------+-------------+----------+
5 rows in set (0.01 sec)

mysql> select * from vehicles;
Empty set (0.01 sec)

mysql> drop table products;
Query OK, 0 rows affected (0.03 sec)

mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| customers           |
| employee            |
| orders              |
| vehicles            |
+---------------------+
4 rows in set (0.00 sec)

mysql> drop table employee;
Query OK, 0 rows affected (0.01 sec)

mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| customers           |
| orders              |
| vehicles            |
+---------------------+
3 rows in set (0.00 sec)

mysql> create table location(
    -> lid int not null,
    -> street varchar(30),
    -> city varchar(10));
Query OK, 0 rows affected (0.03 sec)

mysql> alter table location add primary key('lid');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''lid')' at line 1
mysql> ALTER TABLE 'location'  ADD PRIMARY KEY ('lid');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ''location'  ADD PRIMARY KEY ('lid')' at line 1
mysql> ALTER TABLE `location`  ADD PRIMARY KEY (`lid`);
Query OK, 0 rows affected (0.05 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> create table areas(
    -> aid int not null primary key,
    -> aname varchar(20) ,
    -> size varchar(20));
Query OK, 0 rows affected (0.03 sec)

mysql> describe areas;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| aid   | int(11)     | NO   | PRI | NULL    |       |
| aname | varchar(20) | YES  |     | NULL    |       |
| size  | varchar(20) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)

mysql> create table cart(
    -> cid int not null primary key,
    -> quantity int);
Query OK, 0 rows affected (0.03 sec)

mysql> drop orders;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'orders' at line 1
mysql> drop table orders;
Query OK, 0 rows affected (0.01 sec)

mysql> create table order(
    -> oid int primary key,
    -> type varchar(20),
    -> description varchar(40),
    -> quantity int);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'order(
oid int primary key,
type varchar(20),
description varchar(40),
quantity ' at line 1
mysql> create table order(
    -> oid int primary key not null,
    -> type varchar(20),
    -> description varchar(40),
    -> quantity int);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'order(
oid int primary key not null,
type varchar(20),
description varchar(40),
' at line 1
mysql> create table order(
    -> oid int primary key not null,
    ->
    -> type varchar(20),
    -> description varchar(22),
    -> quantity int);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'order(
oid int primary key not null,

type varchar(20),
description varchar(22),' at line 1
mysql> create table order(
    -> oid int not null primary key,
    -> type varchar(30),
    -> description varchar(30),
    -> quantity int(10) );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'order(
oid int not null primary key,
type varchar(30),
description varchar(30),
' at line 1
mysql> create table order(
    -> oid int not null primary key,
    -> type varchar(30) not null,
    -> description varchar(30) not null,
    -> quantity int not null);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'order(
oid int not null primary key,
type varchar(30) not null,
description varc' at line 1
mysql> create table order(
    -> oid int not null primary key,
    -> description varchar(30),
    -> type varchar(30),
    -> quantity int);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'order(
oid int not null primary key,
description varchar(30),
type varchar(30),
' at line 1
mysql> create table orders(
    -> oid int not null,
    -> type varchar(30),
    -> description varchar(20),
    -> quantity int(20)
    -> );
Query OK, 0 rows affected (0.03 sec)

mysql> update table `orders` add primary key `oid`;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'table `orders` add primary key `oid`' at line 1
mysql> update table `orders` add primary key (`oid`);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'table `orders` add primary key (`oid`)' at line 1
mysql> alter table `orders` add primary key (`oid`);
Query OK, 0 rows affected (0.05 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> create table tracks(
    -> cid int,
    -> track;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 3
mysql> create table tracks(
    -> cid int,
    -> trackid int not null primary key,
    -> pid int,
    -> foreign key (cid) references customers(cid)
    -> ,
    -> foreign key(pid) references products(pid) );
ERROR 1215 (HY000): Cannot add foreign key constraint
mysql> describe tracks;
ERROR 1146 (42S02): Table 'happyfeet.tracks' doesn't exist
mysql> create table food(
    -> ftype varchar(30),
    -> fdesc varchar(30));
Query OK, 0 rows affected (0.02 sec)

mysql> create table grocery(
    -> gtype varchar(30),
    -> gdesc varchar(30));
Query OK, 0 rows affected (0.04 sec)

mysql> create table medicines(
    -> mtype varchar(30),
    -> mdesc varchar(30));
Query OK, 0 rows affected (0.03 sec)

mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| areas               |
| cart                |
| customers           |
| food                |
| grocery             |
| location            |
| medicines           |
| orders              |
| vehicles            |
+---------------------+
9 rows in set (0.00 sec)

mysql>
mysql> create stores(
    -> stid int not null primary key
    -> ,
    -> sname varchar(30),
    -> stloc varchar(30));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'stores(
stid int not null primary key
,
sname varchar(30),
stloc varchar(30))' at line 1
mysql> create stores(
    -> stid int not null primary key,
    -> sname varchar(30),
    -> stloc varchar(30));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'stores(
stid int not null primary key,
sname varchar(30),
stloc varchar(30))' at line 1
mysql> create stores(
    -> stid int not null ,
    -> sname varchar(30),
    -> stloc varchar(30));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'stores(
stid int not null ,
sname varchar(30),
stloc varchar(30))' at line 1
mysql> create stores(
    -> stid int not null ,
    -> sname varchar(30),
    -> stloc varchar(30) );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'stores(
stid int not null ,
sname varchar(30),
stloc varchar(30) )' at line 1
mysql> create stores(
    -> stid int not null,
    -> sname varchar(30),
    -> stloc varchar(30));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'stores(
stid int not null,
sname varchar(30),
stloc varchar(30))' at line 1
mysql> create table store(
    -> stid int,
    -> sname varchar(30),
    -> stloc varchar(30));
Query OK, 0 rows affected (0.04 sec)

mysql>  alter table `store` add primary key (`stid`);
Query OK, 0 rows affected (0.05 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> create table menu(
    -> mid int not null primary key,
    -> metype varchar(30));
Query OK, 0 rows affected (0.03 sec)

mysql> create table payment(
    -> payid int not null primary key,
    -> pmode varchar(30),
    -> oid int,
    -> foreign key(oid) references orders(oid));
Query OK, 0 rows affected (0.03 sec)

mysql> create table cod(
    -> codid int not null primary key,
    -> amt float);
Query OK, 0 rows affected (0.03 sec)

mysql> create table card(
    -> cardno long int not null primary key,
    -> cardtype varchar(30),
    -> expdate date,
    -> cvv int not null );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'int not null primary key,
cardtype varchar(30),
expdate date,
cvv int not null ' at line 2
mysql> create table card(
    -> cardno long int not null primary key,
    -> cardtype varchar(30),
    -> cardtype varchar(30),
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'int not null primary key,
cardtype varchar(30),
cardtype varchar(30),' at line 2
mysql> create table card(
    -> cardno long int not null primary key,
    -> cardtype varchar(30),
    -> expdate date,
    -> cvv int );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'int not null primary key,
cardtype varchar(30),
expdate date,
cvv int )' at line 2
mysql> create table card(
    -> cardno bigint ,
    -> cardtype varchar(30),
    -> expdate date,
    -> cvv int not null );
Query OK, 0 rows affected (0.04 sec)

mysql> alter table `card` add primary key `cardno`;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql>  alter table `card` add primary key (`cardno`);
Query OK, 0 rows affected (0.06 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> create table ebanking(
    -> userbankid bigint primary key,
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 2
mysql> create table ebanking(
    -> userbankid bigint not null primary key,
    -> bname varchar(30),
    -> buname varchar(30),
    -> bpass int);
Query OK, 0 rows affected (0.03 sec)

mysql> create table partner(
    -> pname varchar(30),
    -> pcontact bigint,
    -> pid int not null primary key);
Query OK, 0 rows affected (0.02 sec)

mysql> describe vehicles;
+---------------+-------------+------+-----+---------+----------------+
| Field         | Type        | Null | Key | Default | Extra          |
+---------------+-------------+------+-----+---------+----------------+
| vid           | int(11)     | NO   | PRI | NULL    | auto_increment |
| vehiclenumber | varchar(30) | YES  |     | NULL    |                |
+---------------+-------------+------+-----+---------+----------------+
2 rows in set (0.00 sec)

mysql> alter table vehicles add vname varchar(30);
Query OK, 0 rows affected (0.06 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> describe vehicles;
+---------------+-------------+------+-----+---------+----------------+
| Field         | Type        | Null | Key | Default | Extra          |
+---------------+-------------+------+-----+---------+----------------+
| vid           | int(11)     | NO   | PRI | NULL    | auto_increment |
| vehiclenumber | varchar(30) | YES  |     | NULL    |                |
| vname         | varchar(30) | YES  |     | NULL    |                |
+---------------+-------------+------+-----+---------+----------------+
3 rows in set (0.00 sec)

mysql> create table support(
    -> sid int not null primary key,
    -> stype varchar(30));
Query OK, 0 rows affected (0.02 sec)

mysql> create table contact(
    -> contactno bigint,
    -> assistname varchar(30));
Query OK, 0 rows affected (0.02 sec)

mysql>
mysql> create table tracks(
    ->
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql> create table tracks(
    -> cid int,
    -> trackid int not null primary key,
    -> pid int,
    -> foreign key(cid) references customers(cid),
    -> foreign key(pid) references partner(pid));
Query OK, 0 rows affected (0.03 sec)

mysql> create table confirmation(
    -> cid int,
    ->
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 2
mysql> create table confirmation(
    -> cid int,
    -> pid int,
    -> foreign key(cid) references customers(cid),
    -> foreign key(pid) references partner(pid));
Query OK, 0 rows affected (0.03 sec)

mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| areas               |
| card                |
| cart                |
| cod                 |
| confirmation        |
| contact             |
| customers           |
| ebanking            |
| food                |
| grocery             |
| location            |
| medicines           |
| menu                |
| orders              |
| partner             |
| payment             |
| store               |
| support             |
| tracks              |
| vehicles            |
+---------------------+
20 rows in set (0.00 sec)

mysql> select * from customers;
+-----+---------+-------------------+------+------------+----------------------------------------+
| cid | name    | email             | pwd  | phno       | address                                |
+-----+---------+-------------------+------+------------+----------------------------------------+
|   1 | kriti   | kriti@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   2 | sarita  | sarita@gmail.com  | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   3 | ameya   | ameya@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   4 | tushali | tushali@gmail.com | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   5 | zeel    | zeel@gmail.com    | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
+-----+---------+-------------------+------+------------+----------------------------------------+
5 rows in set (0.00 sec)

mysql> alter table customers delete * from customers where cid=5;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'delete * from customers where cid=5' at line 1
mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| areas               |
| card                |
| cart                |
| cod                 |
| confirmation        |
| contact             |
| customers           |
| ebanking            |
| food                |
| grocery             |
| location            |
| medicines           |
| menu                |
| orders              |
| partner             |
| payment             |
| store               |
| support             |
| tracks              |
| vehicles            |
+---------------------+
20 rows in set (0.00 sec)

mysql> insert into location(lid,street,city)^C
mysql> ^C
mysql> ;
ERROR:
No query specified

mysql>  insert into location(lid,street,city)
    -> values(001,sus rd,pune);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'rd,pune)' at line 2
mysql>  insert into location(lid,street,city)
    -> values(001,sus,pune);
ERROR 1054 (42S22): Unknown column 'sus' in 'field list'
mysql> describe location
    -> ;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| lid    | int(11)     | NO   | PRI | NULL    |       |
| street | varchar(30) | YES  |     | NULL    |       |
| city   | varchar(10) | YES  |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql>  insert into location(lid,street,city)
    -> values(001,sus,pune);
ERROR 1054 (42S22): Unknown column 'sus' in 'field list'
mysql>  insert into location(lid,street,city)
    -> values (1,'sus','pune'),(2,'sb road','pune'),(3,'thakur','mumbai'),(4,'dataa','mumbai'),(5,'dwarka','delhi');
Query OK, 5 rows affected (0.00 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql>  insert into areas(aid,aname,asize)
    -> vlaues (101,'pune',300),(102,'mumbai,600),(103,'delhi',1484);
    '>
    '>
    '> ;
    '> ;
    '> ^D^D^D^C
mysql> ^C
mysql>  insert into areas(aid,aname,asize)
    -> values (101,'pune',300),(102,'mumbai,600),(103,'delhi',1484);
    '> ^D^D^X^C
mysql>  insert into areas(aid,aname,asize)
    -> values (101,'pune',300),(102,'mumbai,600),(103,'delhi',1484);
    '> values (101,'pune',300),(102,'mumbai,600),(103,'delhi',1484);^C
mysql>  insert into areas(aid,aname,asize)
    -> values (101,'pune',3),(102,'mumbai,6),(103,'delhi',14);
    '> ^C
mysql>  insert into areas(aid,aname,asize)
    -> values(101,'pune',3),(102,'mumbai,6),(103,'delhi',14);
    '> ^C
mysql>  insert into areas(aid,aname,asize)
    -> values (101,'pune',300),(102,'mumbai,600),(103,'delhi',1484);
    '> ^C
mysql>  insert into areas(aid,aname,asize)values
    -> (101,'pune',300),(102,'mumbai,600),(103,'delhi',1484);
    '> ;
    '>
    '> ^C
mysql> describe areas;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| aid   | int(11)     | NO   | PRI | NULL    |       |
| aname | varchar(20) | YES  |     | NULL    |       |
| size  | varchar(20) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> insert into areas(aid,aname,size)
    -> values(101,'pune','300'),(102,'mumbai','600'),(103,'delhi','1200');
Query OK, 3 rows affected (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> describe cart;
+----------+---------+------+-----+---------+-------+
| Field    | Type    | Null | Key | Default | Extra |
+----------+---------+------+-----+---------+-------+
| cid      | int(11) | NO   | PRI | NULL    |       |
| quantity | int(11) | YES  |     | NULL    |       |
+----------+---------+------+-----+---------+-------+
2 rows in set (0.00 sec)

mysql> insert into cart(cid,quantity)values
    -> (1,05),(2,05),(3,03),(4,03),(5,01);
Query OK, 5 rows affected (0.01 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> select *from orders;
Empty set (0.00 sec)

mysql> describe orders
    -> ;
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| oid         | int(11)     | NO   | PRI | NULL    |       |
| type        | varchar(30) | YES  |     | NULL    |       |
| description | varchar(20) | YES  |     | NULL    |       |
| quantity    | int(20)     | YES  |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> insert into orders(oid,type,description,quantity)values
    -> (201,'food','none',2),
    -> (201,'meds','none',3),
    -> (201,'meds','bring change',3),
    -> (201,'food','it should be hot!',1),
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 5
mysql> select * from orders;
Empty set (0.00 sec)

mysql> insert into orders(oid,type,description,quantity)values
    -> (201,'food','none',2),
    -> (202,'meds','none',3),
    -> (203,'meds','bring change',3),
    -> (204,'food','it should be hot!',1),
    -> (205,'grocs','should be fresh',7);
Query OK, 5 rows affected (0.00 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> select * from orders;
+-----+-------+-------------------+----------+
| oid | type  | description       | quantity |
+-----+-------+-------------------+----------+
| 201 | food  | none              |        2 |
| 202 | meds  | none              |        3 |
| 203 | meds  | bring change      |        3 |
| 204 | food  | it should be hot! |        1 |
| 205 | grocs | should be fresh   |        7 |
+-----+-------+-------------------+----------+
5 rows in set (0.00 sec)

mysql> describe food;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| ftype | varchar(30) | YES  |     | NULL    |       |
| fdesc | varchar(30) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> insert into food(ftype,fdesc)values
    -> ('chinese','asian food'),
    -> ('punjabi','north indian'),
    -> ('thai','asian'),
    -> ('continental','european'),
    ->  ('italian','Itlly');
Query OK, 5 rows affected (0.00 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> describe grocery;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| gtype | varchar(30) | YES  |     | NULL    |       |
| gdesc | varchar(30) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> insert into grocery(gtype,gdesc)values
    ->  ('rashan','dry products'),
    ->  ('veggies','vegetables'),
    -> ^C
mysql> insert into grocery(gtype,gdesc)values
    ->  ('rashan','dry products'),
    ->  ('veggies','vegetables'),
    ->  ('Fruits','fresh');
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> describe medicines;;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| mtype | varchar(30) | YES  |     | NULL    |       |
| mdesc | varchar(30) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.00 sec)

ERROR:
No query specified

mysql> insert into medicines(mtype,mdesc)values
    ->  ('Allopathy','strong dosage'),
    ->  ('homeopathy','mild dosage'),
    ->  ('Ayurvedic','light dosage');
Query OK, 3 rows affected (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> describe payment;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| payid | int(11)     | NO   | PRI | NULL    |       |
| pmode | varchar(30) | YES  |     | NULL    |       |
| oid   | int(11)     | YES  | MUL | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)

mysql> decsribe stores;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'decsribe stores' at line 1
mysql> decsribe store;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'decsribe store' at line 1
mysql> describe store;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| stid  | int(11)     | NO   | PRI | NULL    |       |
| sname | varchar(30) | YES  |     | NULL    |       |
| stloc | varchar(30) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> insert into store(stid,sanme,stloc)values
    -> (,'',''),^C
mysql> insert into store(stid,sanme,stloc)values
    -> (301,'SP1','pune'),
    -> (302,'SP2','pune'),
    -> (303,'SM1','mumbai'),
    -> (304,'SM2','mumbai'),
    -> (305,'SD1','delhi'),
    -> (306,'S21','delhi'),
    -> (307,'SD2','delhi');
ERROR 1054 (42S22): Unknown column 'sanme' in 'field list'
mysql> insert into store(stid,sname,stloc)values
    -> (301,'SP1','pune'),
    -> (302,'SP2','pune'),
    -> (303,'SM1','mumbai'),
    -> (304,'SM2','mumbai'),
    -> (305,'SD1','delhi'),
    -> (306,'SD2','delhi'),
    -> (307,'SD3','delhi');
Query OK, 7 rows affected (0.00 sec)
Records: 7  Duplicates: 0  Warnings: 0

mysql> describe menu;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| mid    | int(11)     | NO   | PRI | NULL    |       |
| metype | varchar(30) | YES  |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> insert into menu(mid,metype)values
    -> (401,'food'),
    -> (402,'meds'),
    -> (403,'groceries');
Query OK, 3 rows affected (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> describe payment;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| payid | int(11)     | NO   | PRI | NULL    |       |
| pmode | varchar(30) | YES  |     | NULL    |       |
| oid   | int(11)     | YES  | MUL | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> describe orders;
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| oid         | int(11)     | NO   | PRI | NULL    |       |
| type        | varchar(30) | YES  |     | NULL    |       |
| description | varchar(20) | YES  |     | NULL    |       |
| quantity    | int(20)     | YES  |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> select *from orders;
+-----+-------+-------------------+----------+
| oid | type  | description       | quantity |
+-----+-------+-------------------+----------+
| 201 | food  | none              |        2 |
| 202 | meds  | none              |        3 |
| 203 | meds  | bring change      |        3 |
| 204 | food  | it should be hot! |        1 |
| 205 | grocs | should be fresh   |        7 |
+-----+-------+-------------------+----------+
5 rows in set (0.00 sec)

mysql> describe payment;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| payid | int(11)     | NO   | PRI | NULL    |       |
| pmode | varchar(30) | YES  |     | NULL    |       |
| oid   | int(11)     | YES  | MUL | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> insert into payment(payid,pmode,oid)values
    -> (501,'cod',201),
    -> (502,'cod',202),
    -> (503,'card',203),
    -> (504,'card',204),
    -> (505,'ebanking',205);
Query OK, 5 rows affected (0.00 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> decsribe cod;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'decsribe cod' at line 1
mysql> describe cod;
+-------+---------+------+-----+---------+-------+
| Field | Type    | Null | Key | Default | Extra |
+-------+---------+------+-----+---------+-------+
| codid | int(11) | NO   | PRI | NULL    |       |
| amt   | float   | YES  |     | NULL    |       |
+-------+---------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> insert into payment(codid,amt)values
    -> (601,535),
    -> (602,1535.98),
    -> (603,155.44),
    -> (604,200);
ERROR 1054 (42S22): Unknown column 'codid' in 'field list'
mysql> insert into cod(codid,amt)values
    -> (601,535),
    -> (602,1535.98),
    -> (603,155.44),
    -> (604,200);
Query OK, 4 rows affected (0.01 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select *from payment;
+-------+----------+------+
| payid | pmode    | oid  |
+-------+----------+------+
|   501 | cod      |  201 |
|   502 | cod      |  202 |
|   503 | card     |  203 |
|   504 | card     |  204 |
|   505 | ebanking |  205 |
+-------+----------+------+
5 rows in set (0.00 sec)

mysql> select *from cod;
+-------+---------+
| codid | amt     |
+-------+---------+
|   601 |     535 |
|   602 | 1535.98 |
|   603 |  155.44 |
|   604 |     200 |
+-------+---------+
4 rows in set (0.00 sec)

mysql> describe card;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| cardno   | bigint(20)  | NO   | PRI | NULL    |       |
| cardtype | varchar(30) | YES  |     | NULL    |       |
| expdate  | date        | YES  |     | NULL    |       |
| cvv      | int(11)     | NO   |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> insert into card(cardno,cardtype,expdate,cvv)values
    -> (701,'debit','2022-06-12',898),
    -> (702,'debit','2022-05-15',896),
    -> (703,'credit','2042-06-06',777);
Query OK, 3 rows affected (0.01 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> describe ebanking;
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| userbankid | bigint(20)  | NO   | PRI | NULL    |       |
| bname      | varchar(30) | YES  |     | NULL    |       |
| buname     | varchar(30) | YES  |     | NULL    |       |
| bpass      | int(11)     | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> insert into ebanking(userbankid,bname,buname,bpass)values
    -> (801,'SBI','ameya',qwerty),
    -> (802,'SBI','kriti',qwerty1),
    -> (803,'BOB','sarita',qwerty11),
    -> (804,'BOB','tushali',qwerty112),
    -> (805,'ICICI','zeel',qwerty1122);
ERROR 1054 (42S22): Unknown column 'qwerty' in 'field list'
mysql> insert into ebanking(userbankid,bname,buname,bpass)values
    -> (801,'SBI','ameya',1111),
    -> (802,'SBI','kriti',2222),
    -> (803,'BOB','sarita',1122),
    -> (804,'BOB','tushali',1212),
    -> (805,'ICICI','zeel',1221);
Query OK, 5 rows affected (0.01 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> describe partner;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| pname    | varchar(30) | YES  |     | NULL    |       |
| pcontact | bigint(20)  | YES  |     | NULL    |       |
| pid      | int(11)     | NO   | PRI | NULL    |       |
+----------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)

mysql> insert into partner(pname,pcontact,pid)values
    -> (vinod,'9769399999',901),
    -> (Bipin,'9769355999',902),
    -> (vipul,'9769356599',903),
    -> (jayesh,'9769836759',904),
    -> (bhupesh,'8769836759',905);
ERROR 1054 (42S22): Unknown column 'vinod' in 'field list'
mysql> insert into partner(pname,pcontact,pid)values
    -> ('vinod',9769399999,901),
    -> ('Bipin',9769355999,902),
    -> ('vipul',9769356599,903),
    -> ('jayesh',9769836759,904),
    -> ('bhupesh',8769836759,905);
Query OK, 5 rows affected (0.00 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> describe vehical;
ERROR 1146 (42S02): Table 'happyfeet.vehical' doesn't exist
mysql> describe vehicals;
ERROR 1146 (42S02): Table 'happyfeet.vehicals' doesn't exist
mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| areas               |
| card                |
| cart                |
| cod                 |
| confirmation        |
| contact             |
| customers           |
| ebanking            |
| food                |
| grocery             |
| location            |
| medicines           |
| menu                |
| orders              |
| partner             |
| payment             |
| store               |
| support             |
| tracks              |
| vehicles            |
+---------------------+
20 rows in set (0.00 sec)

mysql> describe vehicles;
+---------------+-------------+------+-----+---------+----------------+
| Field         | Type        | Null | Key | Default | Extra          |
+---------------+-------------+------+-----+---------+----------------+
| vid           | int(11)     | NO   | PRI | NULL    | auto_increment |
| vehiclenumber | varchar(30) | YES  |     | NULL    |                |
| vname         | varchar(30) | YES  |     | NULL    |                |
+---------------+-------------+------+-----+---------+----------------+
3 rows in set (0.00 sec)

mysql> insert into vehicles(vid,vehiclenumber,vname)values
    -> (1001,'MH12b11','Activa'),
    -> (1002,'MH12b331','Activa 5g'),
    -> (1003,'MH14b3431','pulser'),
    -> (1004,'MH47b1342','R15');
Query OK, 4 rows affected (0.00 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> describe support;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| sid   | int(11)     | NO   | PRI | NULL    |       |
| stype | varchar(30) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> insert into support(vid,vehiclenumber,vname)values
    -> (1101,'customer care'),
    -> (1102,'complaint registration'),
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 3
mysql> insert into support(vid,vehiclenumber,vname)values
    -> (1101,'customer care'),
    -> (1102,'complaint registration');
ERROR 1136 (21S01): Column count doesn't match value count at row 1
mysql> insert into support(vid,vehiclenumber,vname)values
    -> (1101,'customer care'),
    -> (1102,'complaint');
ERROR 1136 (21S01): Column count doesn't match value count at row 1
mysql> insert into support(sid,stype)values
    -> (1101,'customer care'),
    -> (1102,'complaint registration');
Query OK, 2 rows affected (0.01 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> describe contact;
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| contactno  | bigint(20)  | YES  |     | NULL    |       |
| assistname | varchar(30) | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> insert into support(contactno,assistname)values
    -> (28454455,'ramesh'),
    -> (28754455,'brhamesh'),
    -> (28458855,'Sourav');
ERROR 1054 (42S22): Unknown column 'contactno' in 'field list'
mysql> insert into contact(contactno,assistname)values
    -> (28754455,'brhamesh'),
    -> (28458855,'Sourav');
Query OK, 2 rows affected (0.00 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> describ tracks;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'describ tracks' at line 1
mysql> describe tracks;
+---------+---------+------+-----+---------+-------+
| Field   | Type    | Null | Key | Default | Extra |
+---------+---------+------+-----+---------+-------+
| cid     | int(11) | YES  | MUL | NULL    |       |
| trackid | int(11) | NO   | PRI | NULL    |       |
| pid     | int(11) | YES  | MUL | NULL    |       |
+---------+---------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> select *from cart;
+-----+----------+
| cid | quantity |
+-----+----------+
|   1 |        5 |
|   2 |        5 |
|   3 |        3 |
|   4 |        3 |
|   5 |        1 |
+-----+----------+
5 rows in set (0.00 sec)

mysql> select *from customer;
ERROR 1146 (42S02): Table 'happyfeet.customer' doesn't exist
mysql> select *from customers;
+-----+---------+-------------------+------+------------+----------------------------------------+
| cid | name    | email             | pwd  | phno       | address                                |
+-----+---------+-------------------+------+------------+----------------------------------------+
|   1 | kriti   | kriti@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   2 | sarita  | sarita@gmail.com  | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   3 | ameya   | ameya@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   4 | tushali | tushali@gmail.com | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   5 | zeel    | zeel@gmail.com    | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
+-----+---------+-------------------+------+------------+----------------------------------------+
5 rows in set (0.00 sec)

mysql> select *from partner;
+---------+------------+-----+
| pname   | pcontact   | pid |
+---------+------------+-----+
| vinod   | 9769399999 | 901 |
| Bipin   | 9769355999 | 902 |
| vipul   | 9769356599 | 903 |
| jayesh  | 9769836759 | 904 |
| bhupesh | 8769836759 | 905 |
+---------+------------+-----+
5 rows in set (0.00 sec)

mysql> insert into tracks(cid,trackid,pid)values
    -> (1,1201,901),
    -> (2,1202,902),
    -> (3,1203,903),
    -> (4,1204,904),
    -> (5,1205,905);
Query OK, 5 rows affected (0.00 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> describe conformationl
    -> ;
ERROR 1146 (42S02): Table 'happyfeet.conformationl' doesn't exist
mysql> describe conformation;
ERROR 1146 (42S02): Table 'happyfeet.conformation' doesn't exist
mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| areas               |
| card                |
| cart                |
| cod                 |
| confirmation        |
| contact             |
| customers           |
| ebanking            |
| food                |
| grocery             |
| location            |
| medicines           |
| menu                |
| orders              |
| partner             |
| payment             |
| store               |
| support             |
| tracks              |
| vehicles            |
+---------------------+
20 rows in set (0.00 sec)

mysql> describe  confirmation;
+-------+---------+------+-----+---------+-------+
| Field | Type    | Null | Key | Default | Extra |
+-------+---------+------+-----+---------+-------+
| cid   | int(11) | YES  | MUL | NULL    |       |
| pid   | int(11) | YES  | MUL | NULL    |       |
+-------+---------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> insert into  confirmation(cid,pid)values
    -> (1,901),
    -> (2,902),
    -> (3,903),
    -> (4,904),
    -> (5,905);
Query OK, 5 rows affected (0.01 sec)
Records: 5  Duplicates: 0  Warnings: 0






	



mysql> show tables;
+---------------------+
| Tables_in_happyfeet |
+---------------------+
| areas               |
| card                |
| cart                |
| cod                 |
| confirmation        |
| contact             |
| customers           |
| ebanking            |
| food                |
| grocery             |
| location            |
| medicines           |
| menu                |
| orders              |
| partner             |
| payment             |
| store               |
| support             |
| tracks              |
| vehicles            |
+---------------------+
20 rows in set (0.01 sec)

mysql> select * from customers;
+-----+---------+-------------------+------+------------+----------------------------------------+
| cid | name    | email             | pwd  | phno       | address                                |
+-----+---------+-------------------+------+------------+----------------------------------------+
|   1 | kriti   | kriti@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   2 | sarita  | sarita@gmail.com  | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   3 | ameya   | ameya@gmail.com   | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   4 | tushali | tushali@gmail.com | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
|   5 | zeel    | zeel@gmail.com    | pwd  | 2147483647 | street no 5, house no 81, ocean valley |
+-----+---------+-------------------+------+------------+----------------------------------------+
5 rows in set (0.00 sec)

mysql> select * from location;
+-----+---------+--------+
| lid | street  | city   |
+-----+---------+--------+
|   1 | sus     | pune   |
|   2 | sb road | pune   |
|   3 | thakur  | mumbai |
|   4 | dataa   | mumbai |
|   5 | dwarka  | delhi  |
+-----+---------+--------+
5 rows in set (0.00 sec)

mysql> select * from areas;
+-----+--------+------+
| aid | aname  | size |
+-----+--------+------+
| 101 | pune   | 300  |
| 102 | mumbai | 600  |
| 103 | delhi  | 1200 |
+-----+--------+------+
3 rows in set (0.00 sec)

mysql> select * from cart;
+-----+----------+
| cid | quantity |
+-----+----------+
|   1 |        5 |
|   2 |        5 |
|   3 |        3 |
|   4 |        3 |
|   5 |        1 |
+-----+----------+
5 rows in set (0.00 sec)

mysql> select * from orders;
+-----+-------+-------------------+----------+
| oid | type  | description       | quantity |
+-----+-------+-------------------+----------+
| 201 | food  | none              |        2 |
| 202 | meds  | none              |        3 |
| 203 | meds  | bring change      |        3 |
| 204 | food  | it should be hot! |        1 |
| 205 | grocs | should be fresh   |        7 |
+-----+-------+-------------------+----------+
5 rows in set (0.00 sec)

mysql> select * from tracks;
+------+---------+------+
| cid  | trackid | pid  |
+------+---------+------+
|    1 |    1201 |  901 |
|    2 |    1202 |  902 |
|    3 |    1203 |  903 |
|    4 |    1204 |  904 |
|    5 |    1205 |  905 |
+------+---------+------+
5 rows in set (0.00 sec)

mysql> select * from food;
+-------------+--------------+
| ftype       | fdesc        |
+-------------+--------------+
| chinese     | asian food   |
| punjabi     | north indian |
| thai        | asian        |
| continental | european     |
| italian     | Itlly        |
+-------------+--------------+
5 rows in set (0.00 sec)

mysql> select * from grocery;
+---------+--------------+
| gtype   | gdesc        |
+---------+--------------+
| rashan  | dry products |
| veggies | vegetables   |
| Fruits  | fresh        |
+---------+--------------+
3 rows in set (0.00 sec)

mysql> select * from medicines;
+------------+---------------+
| mtype      | mdesc         |
+------------+---------------+
| Allopathy  | strong dosage |
| homeopathy | mild dosage   |
| Ayurvedic  | light dosage  |
+------------+---------------+
3 rows in set (0.00 sec)

mysql> select * from stores;
ERROR 1146 (42S02): Table 'happyfeet.stores' doesn't exist
mysql> select * from store;
+------+-------+--------+
| stid | sname | stloc  |
+------+-------+--------+
|  301 | SP1   | pune   |
|  302 | SP2   | pune   |
|  303 | SM1   | mumbai |
|  304 | SM2   | mumbai |
|  305 | SD1   | delhi  |
|  306 | SD2   | delhi  |
|  307 | SD3   | delhi  |
+------+-------+--------+
7 rows in set (0.00 sec)

mysql> select * from menu;
+-----+-----------+
| mid | metype    |
+-----+-----------+
| 401 | food      |
| 402 | meds      |
| 403 | groceries |
+-----+-----------+
3 rows in set (0.01 sec)

mysql> select * from payment;
+-------+----------+------+
| payid | pmode    | oid  |
+-------+----------+------+
|   501 | cod      |  201 |
|   502 | cod      |  202 |
|   503 | card     |  203 |
|   504 | card     |  204 |
|   505 | ebanking |  205 |
+-------+----------+------+
5 rows in set (0.00 sec)

mysql> select * from cod;
+-------+---------+
| codid | amt     |
+-------+---------+
|   601 |     535 |
|   602 | 1535.98 |
|   603 |  155.44 |
|   604 |     200 |
+-------+---------+
4 rows in set (0.00 sec)

mysql> select * from card;
+--------+----------+------------+-----+
| cardno | cardtype | expdate    | cvv |
+--------+----------+------------+-----+
|    701 | debit    | 2022-06-12 | 898 |
|    702 | debit    | 2022-05-15 | 896 |
|    703 | credit   | 2042-06-06 | 777 |
+--------+----------+------------+-----+
3 rows in set (0.00 sec)

mysql> select * from e-banking;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '-banking' at line 1
mysql> select * from ebanking;
+------------+-------+---------+-------+
| userbankid | bname | buname  | bpass |
+------------+-------+---------+-------+
|        801 | SBI   | ameya   |  1111 |
|        802 | SBI   | kriti   |  2222 |
|        803 | BOB   | sarita  |  1122 |
|        804 | BOB   | tushali |  1212 |
|        805 | ICICI | zeel    |  1221 |
+------------+-------+---------+-------+
5 rows in set (0.01 sec)

mysql> select * from partner;
+---------+------------+-----+
| pname   | pcontact   | pid |
+---------+------------+-----+
| vinod   | 9769399999 | 901 |
| Bipin   | 9769355999 | 902 |
| vipul   | 9769356599 | 903 |
| jayesh  | 9769836759 | 904 |
| bhupesh | 8769836759 | 905 |
+---------+------------+-----+
5 rows in set (0.00 sec)

mysql> select * from vehicle;
ERROR 1146 (42S02): Table 'happyfeet.vehicle' doesn't exist
mysql> select * from vehicles;
+------+---------------+-----------+
| vid  | vehiclenumber | vname     |
+------+---------------+-----------+
| 1001 | MH12b11       | Activa    |
| 1002 | MH12b331      | Activa 5g |
| 1003 | MH14b3431     | pulser    |
| 1004 | MH47b1342     | R15       |
+------+---------------+-----------+
4 rows in set (0.00 sec)

mysql> select * from confirmation;
+------+------+
| cid  | pid  |
+------+------+
|    1 |  901 |
|    2 |  902 |
|    3 |  903 |
|    4 |  904 |
|    5 |  905 |
+------+------+
5 rows in set (0.01 sec)

mysql> select * from support;
+------+------------------------+
| sid  | stype                  |
+------+------------------------+
| 1101 | customer care          |
| 1102 | complaint registration |
+------+------------------------+
2 rows in set (0.01 sec)

mysql> select * from contact;
+-----------+------------+
| contactno | assistname |
+-----------+------------+
|  28754455 | brhamesh   |
|  28458855 | Sourav     |
+-----------+------------+
2 rows in set (0.00 sec)

