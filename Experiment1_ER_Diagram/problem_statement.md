# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name
Name : K.Mohamed Althaf
Register Number : 212224240089
## Scenario Chosen:
Hospital Database
## ER Diagram:
![6b150c30-2035-4d48-9be9-4d6cd10426ad](https://github.com/user-attachments/assets/d48dfa38-392b-46fd-8f12-6cc6d412c8c0)

## Entities and Attributes:
a) Patients
id (Primary Key)
fullName
dateOfBirth
gender
address
phoneNumber
email
insuranceDetails

b) Doctors
id (Primary Key)
fullName
specialization
phoneNumber
email
workSchedule

c) Appointments
id (Primary Key)
patientId (Foreign Key → Patients.id)
appointmentDateTime
reasonForVisit
additionalNotes
doctorId (Foreign Key → Doctors.id)

d) Medical Records
id (Primary Key)
patientId (Foreign Key → Patients.id)
doctorId (Foreign Key → Doctors.id)
diagnoses
prescribedMedications
treatments
testResults
otherMedicalInfo

e) Departments
id (Primary Key)
departmentName
departmentHead

## Relationships and Constraints:
a) Patients ↔ Appointments
One-to-Many
One patient can have multiple appointments.
Constraint: patientId in appointments must exist in patients.

b) Doctors ↔ Appointments
One-to-Many
One doctor can have multiple appointments.
Constraint: doctorId in appointments must exist in doctors.

c) Patients ↔ Medical Records
One-to-Many
One patient can have multiple medical records.
Constraint: patientId in medical_records must exist in patients.

d) Doctors ↔ Medical Records
One-to-Many
One doctor can be associated with multiple medical records.
Constraint: doctorId in medical_records must exist in doctors.

e) Departments
Currently not directly linked in the ERD, but logically:
A doctor should belong to a department.
Could add: departmentId (FK) in doctors.

## Extension (Prerequisite / Billing):
a) Prerequisite Enhancements
Link Doctors to Departments:
Add departmentId (FK) in doctors referencing departments.id.

User Authentication:
Add users entity to handle login for patients, doctors, and admins.

Room/Bed Management:
New entity: rooms with attributes like roomNumber, bedCount, availability.

b) Billing System
Billing Entity:
id (PK)
patientId (FK)
appointmentId (FK)
amount
paymentDate
paymentMode
billingDetails

Integration:
Link with appointments and/or medical_records to generate charges.

## Design Choices:
The chosen entities in the Hospital Management System—Patients, Doctors, Appointments, Medical Records, and Departments—were selected to represent the core components of hospital operations. Patients and Doctors are fundamental as they are the primary users of the system, while Appointments act as a bridge between them, capturing visit details. Medical Records are essential for maintaining patient history, diagnoses, and treatments, enabling continuity of care. Departments help structure the hospital and organize doctors by specialty. Relationships such as one-to-many between Patients and Appointments or Doctors and Medical Records were designed to reflect real-world scenarios where patients have multiple visits and doctors treat multiple cases. It is assumed that each appointment involves one doctor and one patient, and each medical record corresponds to a specific doctor-patient interaction. While Departments are not directly linked to Doctors in the ERD, such a connection is logically implied for future expansion. Additionally, billing and user authentication are not included but are assumed to be part of an extended version of the system.

## RESULT
The Hospital Management System ERD effectively models key entities and relationships needed for managing patients, doctors, appointments, medical records, and departments. It ensures data integrity, supports scalability, and can be easily extended to include additional features like billing and department-doctor associations.
