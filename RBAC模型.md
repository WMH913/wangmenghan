  # RBAC模型（Role-Based Access Control：基于角色的访问控制）
  
  RBAC的组成:
  
  在RBAC模型里面，有3个基础组成部分，分别是：**用户、角色和权限**。
  
  RBAC通过定义角色的权限，并对用户授予某个角色从而来控制用户的权限，
  
  实现了用户和权限的逻辑分离（区别于ACL模型）， 极大地方便了权限的管理。
  
  1、**User（用户）**：每个用户都有唯一的UID识别，并被授予不同的角色
  
  2、**Role（角色）**：不同角色具有不同的权限

  3、**Permission（权限）**：访问权限

  4、**用户-角色映射**：用户和角色之间的映射关系

  5、**角色-权限映射**：角色和权限之间的映射
  
  
Welcome to the MySQL monitor.  Commands end with ; or \g.

Your MySQL connection id is 1

Server version: 5.6.26-log MySQL Community Server (GPL)

Copyright (c) 2000, 2015, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its

affiliates. Other names may be trademarks of their respective

owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> create database one;

Query OK, 1 row affected (0.00 sec)

mysql> show databases;

+--------------------+

| Database           |

+--------------------+

| information_schema |

| mydb               |

| mysql              |

| one                |

| performance_schema |

| sakila             |

| test               |

| world              |

+--------------------+

8 rows in set (0.00 sec)

mysql> use one;

Database changed

mysql> create table user(

    -> id int comment 'id';
    
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that

corresponds to your MySQL server version for the right syntax to use near '' at

line 2

mysql> create table user(

    -> id int comment 'id',
    
    -> name varchar(32) comment 'name',
    
    -> status varchar(32) comment 'status'
    
    -> );
    
Query OK, 0 rows affected (0.22 sec)

mysql> insert into user values(1,'Tom','online');

Query OK, 1 row affected (0.05 sec)

mysql> insert into user values(2,'Amy','online');

Query OK, 1 row affected (0.04 sec)

mysql> update user set id=3;

Query OK, 2 rows affected (0.07 sec)

Rows matched: 2  Changed: 2  Warnings: 0

mysql> delete from user where name='Tom';

Query OK, 1 row affected (0.03 sec)

mysql> select*from user;

+------+------+--------+

| id   | name | status |

+------+------+--------+

|    3 | Amy  | online |

+------+------+--------+

1 row in set (0.00 sec)

mysql>
