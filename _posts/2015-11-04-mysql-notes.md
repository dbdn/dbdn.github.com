---
layout: post
title: mysql学习笔记
category: [mysql]
tag: [mysql]
date: 2015-11-04
---
---

window刚装完后修改root密码

    C:\Users\dbdn>mysql -uroot
    mysql> set password for 'root'@'localhost' = password('dbdn');


创建用户

    命令:CREATE USER 'username'@'host' IDENTIFIED BY 'password'; 
    create user 'dbdn'@'%' identified by 'dbdn';

给用户授权

    命令:GRANT privileges ON databasename.tablename TO 'username'@'host';
    grant all privileges on one_cms.* to 'dbdn'@'%';

<!-- more -->

创建数据库和用户

    create database one_cms;
    grant all privileges on one_cms.* to dbdn@"%" identified by 'dbdn';

---

有用的sql语句

    -- 统计群组人数分别区间数量
    select
        SUM(CASE
            WHEN (total >= 2 AND total <10)
            THEN 1
            ELSE 0
            END )AS '2-10',
        SUM(CASE
            WHEN (total >= 10 AND total <20)
            THEN 1
            ELSE 0
            END )AS '10-20',
        SUM(CASE
            WHEN (total >= 20 AND total <50)
            THEN 1
            ELSE 0
            END )AS '20-50',
        SUM(CASE
            WHEN (total >= 50 AND total <100)
            THEN 1
            ELSE 0
            END )AS '50-100',
        SUM(CASE
            WHEN (total >= 100)
            THEN 1
            ELSE 0
            END )AS '100-'
    from (
    select 
        group_id id, count(*) total
    from 
        group_user
    
    group by
        group_id)t;

    -- 结果如下
     2-10   10-20   20-50  50-100    100-  
    ------  ------  ------  ------  --------
     1183     153    139      51       41

