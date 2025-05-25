# hospital-management-system



# Features
Add Patients: Allows adding patient details to the database.
View Patients: Displays a list of all patients stored in the database.
View Doctors: Displays a list of all doctors stored in the database.
Book Appointments: Enables booking an appointment between a patient and a doctor, ensuring the doctor's availability on the specified date.
Exit: Closes the application and database connection safely.




# Database Setup
Create a Database:

CREATE DATABASE hospital;
Use the Database:

USE hospital;
Create Tables:

Patients Table:
CREATE TABLE patients (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    age INT NOT NULL,
    gender VARCHAR(10) NOT NULL
);
Doctors Table:
CREATE TABLE doctors (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    specialty VARCHAR(100) NOT NULL
);
Appointments Table:
CREATE TABLE appointments (
    id INT AUTO_INCREMENT PRIMARY KEY,
    patient_id INT NOT NULL,
    doctor_id INT NOT NULL,
    appointment_date DATE NOT NULL,
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);
How to Run
Clone or Download the Project.
Add MySQL Connector/J:
Place the .jar file in a lib folder in your project directory.
Add the .jar file to the project classpath.
Update Database Credentials:
Modify the following fields in the HospitalManagement class:
private static final String url = "jdbc:mysql://localhost:3306/hospital";
private static final String username = "your_mysql_username";
private static final String password = "your_mysql_password";
Compile and Run:
javac -cp ".;lib/mysql-connector-j-9.1.0.jar" src/*.java
java -cp ".;lib/mysql-connector-j-9.1.0.jar;src" HospitalManagement
