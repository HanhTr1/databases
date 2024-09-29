## Week 1:
### Exercise 1
1. 5
2. 5
3. ident
4. varchar
5. iso_country
6. country
7. iso_country
8. varchar
9. 70942
10. iso_country
11. varchar
12. 248
13. goal
14. 0DEG
15. id
16. false
17. game
18. game
19. game
20. game
21. id
22. location
23. goal_reached
24. goal_id and game_id
25. 2
    
## Week 3:
### Exercise 2
select * from goal;
<img width="960" alt="W3_Ex2_Q1Q2" src="https://github.com/user-attachments/assets/789140c4-f467-42cd-8530-54898427660f">

select name from airport where iso_country="FI";
<img width="960" alt="W3_Ex2_Q1Q2" src="https://github.com/user-attachments/assets/7c39ee5c-9afa-4a23-b4b4-dda1b0dd21f6">

select name from airport where iso_country = "FI" order by name asc;
<img width="960" alt="W3_Ex2_Q3" src="https://github.com/user-attachments/assets/ac01b603-efb2-493e-a909-ad32bc02d7ab">

select name, type from airport where iso_country = "FI" order by type asc, name asc;
<img width="960" alt="W3_Ex2_Q4" src="https://github.com/user-attachments/assets/1f7dc594-8441-401e-aa44-ad1e67ff86b8">

select name from country where name like "F%";
<img width="960" alt="W3_Ex2_Q5Q6" src="https://github.com/user-attachments/assets/d703b750-d906-47e6-9552-d61a710e4cad">

select name from country where name like "%F%";
<img width="960" alt="W3_Ex2_Q7" src="https://github.com/user-attachments/assets/365e9cbf-3454-4709-bb84-1c2742858919">

select location from game where screen_name ="Vesa";
<img width="960" alt="W3_Ex2_Q8910" src="https://github.com/user-attachments/assets/49910b83-3f45-4414-8f30-fe4208d3dde1">

select co2_consumed from game where screen_name ="Ilkka";
<img width="960" alt="W3_Ex2_Q8910" src="https://github.com/user-attachments/assets/d8dd6b20-5aa0-48fd-9dfc-15f718d3406d">

select distinct co2_budget from game;
<img width="960" alt="W3_Ex2_Q8910" src="https://github.com/user-attachments/assets/2455f470-69eb-45a7-9079-b28c222ce125">

select screen_name, co2_budget, co2_consumed, (@co2_left := co2_budget - co2_consumed) as co2_left from game where screen_name = "Ilkka";
<img width="960" alt="W3_Ex2_Q8910" src="https://github.com/user-attachments/assets/aab4b216-a3c5-4d3f-a3d7-f30a957e1beb">

### Exercise 3
select country.name as "country name", airport.name as "airport name" from airport, country where airport.iso_country = country.iso_country and country.name = "Iceland";
<img width="960" alt="W3_Ex3_Q1" src="https://github.com/user-attachments/assets/35c5a848-477d-476d-af24-5e0eb661bd4b">

select airport.name as "airport name" from airport where iso_country="FR" and type ="large_airport";
<img width="960" alt="W3_Ex3_Q2Q3" src="https://github.com/user-attachments/assets/62c6caed-11b6-4c32-81e4-0dd6ab59931c">

select country.name as "country_name", airport.name as "airport_name" from country, airport where country.iso_country = airport.iso_country and country.continent ="AN";
<img width="960" alt="W3_Ex3_Q2Q3" src="https://github.com/user-attachments/assets/f324bb4b-1271-49b7-877e-527d6f2d0180">

select elevation_ft from airport, game where location = ident and screen_name = "Heini";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/bf08241d-07fb-4e6d-b791-bcd16d0ef6be">

select elevation_ft * 0.3048 as elevation_m from airport, game where location = ident and screen_name = "Heini";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/f43a2bb4-ddfa-46d3-97e3-6b245fbb19e2">

select name from airport, game where location = ident and screen_name = "Ilkka";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/1fa4e16f-bec4-4680-8978-678ac3b58e93">

select country.name from airport, country, game where location=ident and airport.iso_country=country.iso_country and screen_name="Ilkka";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/f812e5b8-6c7b-4306-8abd-e68e146f8943">

select name from goal, goal_reached, game where game.id = game_id and goal.id = goal_id and screen_name = "Heini";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/dd0e73b7-2c5e-4c94-a707-63d7af9ff930">

select airport.name from airport, game, goal, goal_reached where ident = location and game.id = game_id and goal.id = goal_id  and screen_name = "Ilkka" and goal.name = "CLOUDS";
<img width="960" alt="W3_Ex3_Q9Q10" src="https://github.com/user-attachments/assets/fa282316-3b99-4cc7-95e2-502e05e2267f">

select country.name from country, airport, game, goal, goal_reached where airport.iso_country=country.iso_country and ident=location and game.id=game_id and goal.id=goal_id and screen_name= "Ilkka" and goal.name ="CLOUDS";
<img width="960" alt="W3_Ex3_Q9Q10" src="https://github.com/user-attachments/assets/9d2f5a81-6c71-49bb-8e80-06140d4d5ef0">
## Week 4
### Exercise 4
select country.name as "country name", airport.name as "airport name" from country inner join airport on airport.iso_country = country.iso_country where country.name = "Finland" and scheduled_service = "yes";
<img width="960" alt="W4_Ex4_Q1" src="https://github.com/user-attachments/assets/ff5011e9-501f-4d27-b820-6ea7d7ebd8bd">

select screen_name, airport.name from game inner join airport on location = ident;
<img width="960" alt="W4_Ex4_Q234" src="https://github.com/user-attachments/assets/7249ddcf-5ee3-4ffa-ba32-3bc41c3b66a9">

select screen_name, country.name from game inner join airport on location = ident inner join country on airport.iso_country = country.iso_country;
<img width="960" alt="W4_Ex4_Q234" src="https://github.com/user-attachments/assets/0f4e7802-2cc5-423e-b5fa-ed007b9268af">

select airport.name, screen_name from airport left join game on ident = location where name like "%Hels%";
<img width="960" alt="W4_Ex4_Q234" src="https://github.com/user-attachments/assets/0d1cbf32-f903-499e-bbb6-63f341469134">

select name, screen_name from goal left join goal_reached on goal.id = goal_id  left join game on game.id = game_id;
<img width="960" alt="W4_Ex4_Q5" src="https://github.com/user-attachments/assets/b8d303da-31cd-499a-bda6-2d0152854d3e">

### Exercise 5

select name from country where iso_country in(select iso_country from airport where name like "Satsuma%");
<img width="960" alt="W4_Ex5_Q1234" src="https://github.com/user-attachments/assets/66f656ac-d562-4331-bcdf-34291e7a6aba">

select name from airport where iso_country in(select iso_country from country where country.name = "Monaco");
<img width="960" alt="W4_Ex5_Q1234" src="https://github.com/user-attachments/assets/8e0b2033-9c3f-44a3-a753-11c9d5dfe0fb">

select screen_name from game where game.id in(select game_id from goal_reached where goal_id in (select id from goal where name ="CLOUDS"));
<img width="960" alt="W4_Ex5_Q1234" src="https://github.com/user-attachments/assets/cfa0a0a6-ece4-479e-b208-a9c32ade011d">

select country.name from country where iso_country not in (select airport.iso_country from airport);
<img width="960" alt="W4_Ex5_Q1234" src="https://github.com/user-attachments/assets/b2787ac7-579e-4359-9f65-fbeb0376fc17">

select name from goal where id not in(select goal.id from goal, goal_reached, game where game.id = game_id and goal.id = goal_id and screen_name = "Heini");
<img width="960" alt="W4_Ex5_Q5" src="https://github.com/user-attachments/assets/7324ba76-75bd-4988-a03e-81aa2734538e">

## Week 5
### Exercise 6

select max(elevation_ft) from airport;
<img width="960" alt="W5_Ex6_Q123" src="https://github.com/user-attachments/assets/de8b97b7-80d5-4e97-943c-f56144e30c04">

select continent, count(*) from country group by continent;
<img width="960" alt="W5_Ex6_Q123" src="https://github.com/user-attachments/assets/f96b48c8-39c9-4da7-b619-4bc334a66a07">

select screen_name, count(*) from game, goal_reached where id = game_id group by screen_name;
<img width="960" alt="W5_Ex6_Q123" src="https://github.com/user-attachments/assets/4badb4bb-dd25-4732-8479-99123f453f2b">

select screen_name from game where co2_consumed in(select min(co2_consumed) from game);
<img width="960" alt="W5_Ex6_Q4" src="https://github.com/user-attachments/assets/d58f545d-094d-4610-99c7-a252bdaa6873">

select country.name, count(*) from airport, country where airport.iso_country = country.iso_country group by country.iso_country order by count(*) desc limit 50;
<img width="960" alt="W5_Ex6_Q5" src="https://github.com/user-attachments/assets/54e8ae25-0fd5-4e2c-b919-a28a0576c555">

select country.name from airport, country where airport.iso_country = country.iso_country group by country.iso_country having count(*) > 1000;
<img width="960" alt="W5_Ex6_Q67" src="https://github.com/user-attachments/assets/16bb400b-d93e-4681-8bd0-a036735250b3">

select name from airport where elevation_ft in (select max(elevation_ft) from airport );
<img width="960" alt="W5_Ex6_Q67" src="https://github.com/user-attachments/assets/bdffdaa8-33a7-4b7f-a62f-9f2dff4bb2c3">

select name from country where iso_country in (select iso_country from airport where elevation_ft in(select max(elevation_ft) from airport));
<img width="960" alt="W5_Ex6_Q8910" src="https://github.com/user-attachments/assets/dfb0d75e-db02-4d51-a2da-ea834de40655">

select count(*) from game, goal_reached where id = game_id and screen_name = "Vesa" group by screen_name;
<img width="960" alt="W5_Ex6_Q8910" src="https://github.com/user-attachments/assets/5db633d2-2948-4f3a-a6e6-5bbd96c25a93">

select name from airport where latitude_deg in(select min(latitude_deg) from airport);
<img width="960" alt="W5_Ex6_Q8910" src="https://github.com/user-attachments/assets/f9678e85-42cd-435b-b0eb-2be05d9b9854">

### Exercise 7
update game set  location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500 where screen_name = "Vesa";
select * from game;
<img width="960" alt="W5_Ex7_Q1" src="https://github.com/user-attachments/assets/794a3cc6-51d1-473a-879f-9aa673e970ff">

Question 2: goal_reached

delete from goal_reached;
select * from goal_reached;

<img width="960" alt="W5_Ex7_Q3Q4" src="https://github.com/user-attachments/assets/1e530059-b31d-4b88-b389-ad98852ef7ed">

delete from game;
select * from game;
<img width="960" alt="W5_Ex7_Q3Q4" src="https://github.com/user-attachments/assets/d8b0a889-fa5e-446b-b48c-79d75d6a031c">

## Week 1 software 2
### Exercise 8
1. ident
2. airport
3. Each country can have multiple airports.
4. true
5. false
6. The airport table will have a foreign key that references the country table.
7. The game table will have a foreign key that references the airport table.
8. true
9. The relationship diamond will have its own table.
10. Two foreign keys: One referencing the game table and another referencing the goal table.











