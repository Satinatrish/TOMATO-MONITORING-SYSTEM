create database tomato_db;
use tomato_db;

create table login (
    id INT AUTO_INCREMENT PRIMARY KEY,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    role ENUM('admin', 'manager', 'user') DEFAULT 'user',


    is_verified TINYINT(1) DEFAULT 0,
    verification_token VARCHAR(64),
    email_verification_expires DATETIME NULL,

    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);

create table manager (
    ManagerID int AUTO_INCREMENT PRIMARY KEY, 
    name varchar (255), 
    email varchar (255),
    password varchar(255), 
    role varchar(255)
    );

create table admin (
    AdminID int AUTO_INCREMENT PRIMARY KEY, 
    name varchar (255), 
    email varchar (255),
    password varchar(255), 
    role varchar(255)
    );

create table user(
    userID int AUTO_INCREMENT PRIMARY KEY, 
    name varchar (255), 
    email varchar (255),
    password varchar(255), 
    role varchar(255)
    );

ALTER TABLE manager
ADD CONSTRAINT fk_manager_id 
FOREIGN KEY (fk_manager_id ) REFERENCES user(userID);

ALTER TABLE admin
ADD CONSTRAINT fk_admin_id 
FOREIGN KEY (fk_admin_id ) REFERENCES manager(ManagerID);

create table container(
    containerID int PRIMARY KEY, 
    temperature varchar (255), 
    humidity varchar (255),
    timestamp TIMESTAMP, 
    );



    START TRANSACTION;

INSERT INTO users (username)
   VALUES ('ADMIN')

   INSERT INTO user_activity_logs(action)
      VALUES ('insert_test_data');


COMMIT;
