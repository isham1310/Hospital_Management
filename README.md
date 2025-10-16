# Hospital_Management

**Overview**  
The Hospital Management System is a simple command-line application designed to manage patients, doctors, and appointments using Java and MySQL. It demonstrates basic CRUD operations, database connectivity, and interaction between Java and MySQL. This project serves as a learning tool for understanding the integration of Java with MySQL.

**Features**  
Add Patients: Allows adding patient details to the database.  
View Patients: Displays a list of all patients stored in the database.  
View Doctors: Displays a list of all doctors stored in the database.  
Book Appointments: Enables booking an appointment between a patient and a doctor, ensuring the doctor's availability on the specified date.  
Exit: Closes the application and database connection safely.  

**Dataset Setup**
```sql
CREATE DATABASE hospital;
```
```sql
USE hospital;
```
```sql
CREATE TABLE patients (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    age INT NOT NULL,
    gender VARCHAR(10) NOT NULL
);
```
```sql
CREATE TABLE doctors (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    specialty VARCHAR(100) NOT NULL
);
```
```sql
CREATE TABLE appointments (
    id INT AUTO_INCREMENT PRIMARY KEY,
    patient_id INT NOT NULL,
    doctor_id INT NOT NULL,
    appointment_date DATE NOT NULL,
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);
```

