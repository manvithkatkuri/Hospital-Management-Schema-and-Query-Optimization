# Hospital Management Schema and Query Optimization

This project demonstrates the design, implementation, and analysis of a relational database schema tailored for managing hospital operations, including patient admissions, appointment scheduling, severity tracking, and doctor assignments. The schema supports complex queries to analyze hospital data efficiently, leveraging indexing and query optimization techniques for enhanced performance.

## Project Overview

### Purpose
The database schema is designed to:
- Manage critical hospital activities such as patient admissions, severity tracking, and doctor assignments.
- Analyze hospital performance through key queries.
- Optimize query execution using indexing and performance analysis.

### Key Components
The schema includes the following tables:
1. **`patient_data`**: Contains patient demographic and medical details, including length of stay (LOS), total charges, and diagnosis codes.
2. **`hospital_info`**: Stores hospital metadata such as division, bed size, and control type.
3. **`hospital_severity`**: Tracks the severity levels of patient conditions linked to hospitals and diagnosis codes.
4. **`doctor_details`**: Manages doctor information, including specialties and contact details.
5. **`appointment_details`**: Records patient appointments with doctors and their purposes.

---

## Queries and Performance Analysis

### Key Queries
1. **Retrieve All Patients with Their Doctors and Severity Levels**
   - Joins multiple tables to display patient, doctor, and severity details.
   - **Performance Optimization**: Hash joins and indexed key columns reduced execution time significantly.

2. **Count the Number of Patients per Severity Level**
   - Aggregates patients by severity levels for hospital-wide analysis.
   - **Performance Optimization**: Indexes on severity and key columns improved grouping efficiency.

3. **Retrieve Patients Admitted to Specific Hospitals**
   - Filters patients based on their hospital assignments.
   - **Performance Optimization**: Indexes on hospital identifiers expedited filtered queries.

4. **Find the Total Number of Appointments for Each Doctor**
   - Aggregates appointment counts grouped by doctor names.
   - **Performance Optimization**: Efficient joins and indexing reduced execution time.

5. **Retrieve All Critical Severity Patients with Specific Doctor Assignments**
   - Filters critical severity cases and links them to doctors.
   - **Performance Optimization**: Indexing severity and doctor-patient relationships enhanced filtering.

---

## Schema Design

### Database Tables
- **Hospital Information**
  ```sql
  CREATE TABLE hospital_info (
      hosp_nis INT PRIMARY KEY,
      hosp_bedsize INT,
      hosp_division VARCHAR(10),
      h_contrl VARCHAR(10),
      total_disc INT
  );
