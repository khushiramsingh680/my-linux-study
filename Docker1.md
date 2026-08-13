## Deployment of Java student App on Docker Container.

- [ ] clone your app code
```sh
git clone https://github.com/khushiramsingh680/studentapp.git
cd studentapp
```
-  [ ] Create a build using maven container. You need to run this wherever you have pom.xml file
```sh
 docker run -it --rm --name my-maven-project -v "$(pwd)":/usr/src/mymaven -w /usr/src/mymaven maven:3.3-jdk-8 mvn clean install
```
- [ ] Install tomcat on container
```sh
docker run -dit  -p 8888:8080 tomcat:9.0
```
-  [ ]  Now copy your war file to tomcat server
```sh
 docker cp studentapp-2.5-SNAPSHOT.war e68e5a1227e8:/usr/local/tomcat/webapps
```
- [ ] Test your war file if this is copied successfully
```sh
 docker exec  e68e5a1227e8  ls /usr/local/tomcat/webapps
```

- [ ] Try mapping the war file
```sh
 docker run -dit  -p 88:8080 -v /root/studentapp/target/studentapp-2.5-SNAPSHOT.war:/usr/local/tomcat/webapps/student.war  tomcat:9.0
```


### Now Integrate your DB with this App

- [ ] Create a db container (Mariadb)
```sh
 docker run -d -e MYSQL_ROOT_PASSWORD=root mysql:5.6

```
-  [ ]  Connect db and create database
```sh
docker exec -it f1b857c33c099 mysql -uroot -p
```
- [ ]  Create db and table
```sh
create database studentapp;
use studentapp;


CREATE TABLE Students(student_id INT NOT NULL AUTO_INCREMENT,
	student_name VARCHAR(100) NOT NULL,
  student_addr VARCHAR(100) NOT NULL,
	student_age VARCHAR(3) NOT NULL,
	student_qual VARCHAR(20) NOT NULL,
	student_percent VARCHAR(10) NOT NULL,
	student_year_passed VARCHAR(10) NOT NULL,
	PRIMARY KEY (student_id)
);


grant all privileges on studentapp.* to 'student'@'%' identified by 'student@1';

```
- [ ] Download db connector in tomcat for connectivity in lib directory of your tomcat server
```sh
docker exec -it c8b89cbc922d sh
 cd lib

apt update
apt install wget
cd lib
wget https://github.com/cit-latex/stack/raw/master/mysql-connector-java-5.1.40.jar
```

- [ ] Change the confif now
```sh
docker exec -it c8b89cbc922d sh
apt install vim
cd conf
vi context.xml
<Resource name="jdbc/TestDB" auth="Container" type="javax.sql.DataSource"
               maxTotal="100" maxIdle="30" maxWaitMillis="10000"
               username="student" password="student@1" driverClassName="com.mysql.jdbc.Driver"
               url="jdbc:mysql://<IP-ADDRESS-OF-DB-SERVER>:3306/studentapp"/>
```

- [ ] Now stop & start tomcat container
```sh
docker stop <container name>
docker start <container name >
```
- [ ] How to check container ip
```sh
docker inspect <container id>
```
