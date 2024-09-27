# Week 1 Exercise 1 on Moodle
# Week 2:
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
<img width="960" alt="W3_Ex2_Q7" src="https://github.com/user-attachments/assets/5c5e6d27-3db7-4228-9293-c314a07b8402">

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
<img width="960" alt="W3_Ex3_Q1" src="https://github.com/user-attachments/assets/2d1f608c-c438-460c-8fe6-7406929f382e">

select airport.name as "airport name" from airport where iso_country="FR" and type ="large_airport";
<img width="960" alt="W3_Ex3_Q2Q3" src="https://github.com/user-attachments/assets/d1fc6230-1422-4df1-bd88-7bd8a148ae8d">

select country.name as "country_name", airport.name as "airport_name" from country, airport where country.iso_country = airport.iso_country and country.continent ="AN";
<img width="960" alt="W3_Ex3_Q2Q3" src="https://github.com/user-attachments/assets/65afa06d-9cce-483f-9dfb-96310593bc48">
select elevation_ft from airport, game where location = ident and screen_name = "Heini";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/dad3776c-cf85-46cf-bc6d-19140a4b050b">

select elevation_ft * 0.3048 as elevation_m from airport, game where location = ident and screen_name = "Heini";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/01699dbe-3486-4d1b-8870-810de0ee7030">

select name from airport, game where location = ident and screen_name = "Ilkka";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/cf1507d5-cbb5-4dd6-ae02-245e829c3ff9">

select country.name from airport, country, game where location=ident and airport.iso_country=country.iso_country and screen_name="Ilkka";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/aaf0c7da-8ac4-4276-9306-fb5579d5cdc0">

select name from goal, goal_reached, game where game.id = game_id and goal.id = goal_id and screen_name = "Heini";
<img width="960" alt="W3_Ex3_Q45678" src="https://github.com/user-attachments/assets/16c2f156-edf3-4721-a205-3e64fed10a8c">
select airport.name from airport, game, goal, goal_reached where ident = location and game.id = game_id and goal.id = goal_id  and screen_name = "Ilkka" and goal.name = "CLOUDS";
<img width="960" alt="W3_Ex3_Q9Q10" src="https://github.com/user-attachments/assets/d91f9537-0bfb-4945-8980-eab634cc1247">

select country.name from country, airport, game, goal, goal_reached where airport.iso_country=country.iso_country and ident=location and game.id=game_id and goal.id=goal_id and screen_name= "Ilkka" and goal.name ="CLOUDS";
<img width="960" alt="W3_Ex3_Q9Q10" src="https://github.com/user-attachments/assets/7edbf996-e3af-4416-9d26-13b7575c1723">







