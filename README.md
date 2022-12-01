create database test;

use test;

create table log (eater_id int not null, foodmenu_id int not null, id int auto_increment primary key);

insert into log (eater_id, foodmenu_id) values (1, 1), (2, 2), (3, 1), (4, 3), (1, 1), (5, 1), (6, 2), (7, 2), (8, 5), (8, 5), (9, 5), (10, 5), (1, 4);
select foodmenu_id from log group by foodmenu_id order by count(foodmenu_id) desc limit 3;

select 'error' where 2 >= any (select count() from log group by eater_id, foodmenu_id having count() > 1);
