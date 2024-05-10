## Deployment steps:
This project is a front-end and back-end separation project. The back-end is completed based on the springboot framework and uses the tomcat server; the front-end is completed based on the vue framework and uses the nginx server. In the project, the folder named "hmdp" is the back-end folder of this project. Please deploy it on the java ide. The folder named "itheima_web_project" is the front-end of the project and requires deployment on the nginx server. I will also use the nginx server. The config file is placed in the project to facilitate you to configure the nginx server. Regarding the database, we use the mysql database. The statements to build the database, database tables, and data records are the "hmdp.sql" files, which can be configured directly. In addition, I also use redis to improve data operation speed. If you need it, you need to download redis.

Questions mentioned in scoring:
1. missing demo: This is my "screenshot and video demo" file, because the video file is too large (more than 25M, so it cannot be uploaded)

2. Regarding my API interface, because there are too many interfaces defined, I will not explain them one by one, but I can talk about the general structure of my project. I designed the overall structure of the project based on the MVC architecture, where config is the springboot startup file I defined, dto is the intermediate class defined for the consistency of data transmission between the front and back ends, entity is the entity class, and util is the tool class. The remaining controller, mapper and service are my mvc.
<img width="195" alt="image" src="https://github.com/BackendHan/530_Final_Project/assets/144406286/164bacaa-5f84-4332-b927-1cba9f9b446e">

3. About unit testing
I placed it under the test file that comes with the springboot project and provides some test methods and preheating methods for the project.
<img width="311" alt="image" src="https://github.com/BackendHan/530_Final_Project/assets/144406286/bcf2f286-dc19-4985-8cb6-eeec104aec6a">


