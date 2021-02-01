# First Start the mysql Docker with the below command:-

docker run --name=mysql5 -e MYSQL_ROOT_PASSWORD=password -d -p 3306:3306 -v /Users/arpan/GitRepo/Spring-boot/spring-boot-mysql-rest-api-tutorial/mysqlSpace_5_6:/var/lib/mysql mysql:5.6 

Here -v /Users/arpan/GitRepo/Spring-boot/spring-boot-mysql-rest-api-tutorial/mysqlSpace_5_6:/var/lib/mysql
will create the mysql space on local disk so we will not loose any mysql table data

#Check mysql instance 
docker exec -it mysql5 mysql -uroot -ppassword  

#create the required database for the application:-
create database notes_app;

==========================================================

**1. Clone the application**

```bash
git clone https://github.com/arpanpics1/mysql-rest-api-with-DockerSQL.git
```

**2. Build and run the app using maven**

```bash
mvn package
java -jar target/easy-notes-1.0.0.jar
```

Alternatively, you can run the app without packaging it using -

```bash
mvn spring-boot:run
```

The app will start running at <http://localhost:8080>.

## Explore Rest APIs

The app defines following CRUD APIs.

    GET /api/notes
    
    POST /api/notes
    
    GET /api/notes/{noteId}
    
    PUT /api/notes/{noteId}
    
    DELETE /api/notes/{noteId}

