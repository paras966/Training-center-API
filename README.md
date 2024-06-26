# Training-center-API

## Setup Instructions (VIDEO)
```
https://drive.google.com/file/d/18QRBNaVBG7FdOZtyEVAPzZ4gqHPtrsja/view?usp=sharing
```
This project is a Spring Boot application that provides APIs for managing training centers and courses offered by them.
`Spring boot, Hibernate(ORM Tool), Mysql, Included Validations`

## Setup Instructions
### Create Database:
- Create a MySQL database named mvp.
- Use the database mvp.
```
create database mvp;
use mvp;
```
### Create Tables:
```
CREATE TABLE training_center (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    centerName VARCHAR(40) NOT NULL,
    centerCode CHAR(12) NOT NULL UNIQUE,
    detailedAddress VARCHAR(255) NOT NULL,
    city VARCHAR(255) NOT NULL,
    state VARCHAR(255) NOT NULL,
    pincode CHAR(6) NOT NULL,
    studentCapacity INT,
    createdOn BIGINT,
    contactEmail VARCHAR(255),
    contactPhone CHAR(10) NOT NULL
);

CREATE TABLE courses_offered (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    trainingCenterId BIGINT NOT NULL,
    courseName VARCHAR(255) NOT NULL,
    FOREIGN KEY (trainingCenterId) REFERENCES training_center(id)
);

```
### Clone Repository:
```
git clone https://github.com/paras966/Backend_Traini8_ParasPatil.git
```
### Edit correct creadentials in ./src/Main/resources/Hibernate.cgf.xml
- Add your URL and username, password for mysql server
### Run the Project:
- Navigate to the project directory.
- Run the project using Maven or your IDE.

### Hit Endpoints:

After running the project, hit the endpoints to interact with the API.First, make a POST request to add data to the tables.Then, use GET requests to retrieve data.
- Sample Body for POST Request
  ```
  http://localhost:8080/api/training-centers
  ```
json
```
{
    "id": 1,
    "centerName": "CodeCrafters Center",
    "centerCode": "CODE00112341",
    "address": {
        "detailedAddress": "789 Elm Street",
        "city": "Chicago",
        "state": "IL",
        "pincode": "600001"
    },
    "studentCapacity": 120,
    "coursesOffered": null,
    "contactEmail": "hello@codecrafters.com",
    "contactPhone": "4561237890"
}
```
`Get API`
```http://localhost:8080/api/training-centers```
Feel free to explore and interact with the API endpoints as per your requirements.
