use dmkur;
show tables;

# знайти усі машини старше 2000 року
select * from cars where year>2000;

# знайти усі машини до 2000 року
select * from cars where year<2000;

# знайти усі машини 2008, 2009, 2010 років
select * from cars where year in(2008,2009,2010);
# знайти усі машини окрім 2008, 2009, 2010 років
select * from cars where year not in(2008,2009,2010);

# знайти усі машини рік яких співпадає с ціною
select * from cars where price = year;

# знайти усі машини bmw старше 2014 року
select * from cars where year = 2014 and model='bmw';

# найти усі машини audi до 2014 року
select * from cars where model='audi' and year<2014;
# знайти перші 5 машин
select * from cars where model='audi' and year<2014 limit 5;
# знайти останні 5 машин
select * from cars where model='audi' and year<2014 order by id desc limit 5;

# зайти среднее арифметичне цін машин моделі KIA
select avg(price) as avgPrice, model from cars where model='kia';

# знайти среднє арифметичне цін кожної машини
select avg(price) as avgPrice, model from cars group by model;

# підрахувати кількість кожної марки авто
select count(*), model from cars group by model;

# знайти марку машини якої представлено найбільше
select count(*) as count, model from cars group by model order by count desc limit 1;

# знайти всі авто в моделі яких друна і передостання буква "а"
select * from cars where model like '_a%a_';

# знайти усі авто в назві моделі яких більше 8 символів
select * from cars where length(model) > 8;

# ***знайти машини ціна яких більше чем ціни среднього арифметичного усіх машині
select * from cars where price > (select avg(price) from cars);
