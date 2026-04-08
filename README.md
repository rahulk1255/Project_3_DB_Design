```
📘 Clinic Appointment & Diagnostics Platform – ER Diagram
📌 Overview

This ER diagram represents a clinic management system that handles patients, doctors, appointments, consultations, diagnostic tests, reports, and payments.
The design follows a real-world workflow and is structured to be scalable and normalized.

🔄 Workflow

The system follows this flow:

Patient → Appointment → Consultation → Tests → Reports → Invoice → Payment
A patient books an appointment with a doctor
The appointment may result in a consultation (visit)
During consultation, medicines and diagnostic tests may be prescribed
Tests generate reports
Billing is handled through invoices and payments
🧱 Entities Included
Patients
Patient Addresses
Patient Medical History
Doctors
Specialties
Doctor Specialties
Doctor Availability
Appointments
Consultations
Medicines
Consultation Medicines
Test Types
Labs
Test Orders
Test Order Items
Reports
Invoices
Payments
🔗 Key Relationships
One patient can have many appointments
One appointment can result in one consultation (optional)
One consultation can have multiple medicines and test orders
One test order can contain multiple test items
Each test item generates one report
One invoice can have multiple payments
Doctors can have multiple specialties (many-to-many relationship)
🧠 Important Design Decisions
Appointment and consultation are separate entities to reflect real clinic workflow
Previous medications are derived from past consultation records instead of storing separately
Diagnostic system is divided into test orders and test items for scalability
Billing is handled using invoices to support partial and multiple payments
Patient medical history is stored separately for chronic conditions
⚙️ Constraints & Design Quality
Primary keys (PK) defined for all entities
Foreign keys (FK) used to maintain relationships
Unique constraints on email and phone
Check constraints for status fields and enums
Not null constraints for important attributes
Follows normalization (3NF) to avoid redundancy
```
