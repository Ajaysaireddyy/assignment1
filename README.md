# assignment1
q)1
create database online_con;

use online_con;

create table doctor_table(
id int primary key not null,
doctor_name varchar(20) not null,
speciatization varchar(20) not null
);

create table appointments_table(
doctor_name varchar(20) not null,
patient_name varchar(20) not null,
token_num int not null
);

create table patient_table(
p_id int primary key not null,
p_name varchar(20) not null,
bed_num int(10) not null
);

create table reviews_table(
doctor_name varchar(20) not null,
rating int not null
);

q)2
create database q2;

use q2;

create table contact_table(
id int primary key not null,
email varchar(20) not null,
fname varchar(20) not null,
lname varchar(20) not null,
company varchar(20) not null,
active_flag int not null,
opt_out int not null
);

insert into contact_table values(123,"a@a.com","kian","seth","ABC",1,1),(133,"b@a.com","neha","seth","ABC",1,0);
insert into contact_table values(234,"c@c.com","puru","malik","CDF",0,0),(342,"d@d.com","sid","maan","TEG",1,0);

-- select all columns from contact table where active flags is 1 
select * from contact_table where active_flag = 1;

-- deactivate contacts who are opted out
 

-- delete all the contacts who have the company name as ABC
delete from contact_table where company = "ABC";


-- insert a new row 
insert into contact_table values(658,"mili@gmail.com","mili","seth","DGH",1,1);



-- pull out the unique values of the company column
select distinct company from contact_table;



-- update name mili to nili
update contact_table set fname = 'nili' where id = 658;

Q)3
create database q3;
use q3;
create table customer(
customer_id int  not null,
cust_name varchar(20) not null,
city varchar(20) not null,
grade int not null,
salesman_id int not null,
primary key(customer_id),
foreign key(salesman_id) references salesman(salesman_id)
);


insert into customer values(3002,"Nick Rimando","New York",100,5001),(3007,"Brad Davis","New York",200,5001),(3005,"Graham Zusi","california",200,5002),(3008,"Julian Green","London",300,5002),(3004,"Fabian Johnason","Paris",300,5006),(3009,"Geoff Cameron","Berlin",100,5003),(3003,"Jozy Altidor","Moscow",200,5007),(3001,"Brad Guzan","London",0,5005);
select * from customer;
create table salesman(
salesman_id int primary key not null,
sname varchar(20) not null,
city varchar(20) not null,
commission float not null
); 


insert into salesman values(5001,"James Hoog","New York",0.15),(5002,"Nail Knite","Paris",0.13),(5005,"Pit Alex","London",0.11),(5006,"Mc Lyon","Paris",0.14),(5007,"Paul Adam","Rome",0.13),(5003,"Lauson Hen","San Jose",0.12);
drop table customer;
select * from salesman;
drop table salesman;
use q3;
drop database q31;
select cust_name,city,grade,salesman_id from customer where grade < 100;


