📘 Clinic Appointment & Diagnostics Platform – ER Diagram
📌 Overview

This project presents a scalable ER diagram design for a clinic management system.
It models the complete workflow from patient appointment booking to consultation, diagnostics, reporting, and payments.

The design focuses on real-world usability, normalization, and scalability, making it suitable for modern clinic platforms.

🎯 Objectives

The system is designed to answer:

Who are the doctors and their specialties?
Which patient booked which appointment?
What is the appointment status?
Did the appointment result in a consultation?
What tests were prescribed?
What reports were generated?
Can patients have multiple visits?
How are payments handled?
🔄 System Workflow
Patient → Appointment → Consultation → Tests → Reports → Invoice → Payment
A patient books an appointment with a doctor
Appointment may result in a consultation
During consultation, doctor may prescribe medicines and tests
Tests are processed and reports are generated
Billing is handled via invoices and payments
🧱 Entities Included
👤 Patient Domain
Patients
Patient Addresses
Patient Medical History
👨‍⚕️ Doctor Domain
Doctors
Specialties
Doctor Specialties (M:N)
Doctor Availability
📅 Appointment Domain
Appointments
🩺 Consultation Domain
Consultations
Consultation Medicines
🧪 Diagnostics Domain
Test Types
Labs
Test Orders
Test Order Items
Reports
💳 Billing Domain
Invoices
Payments
🔗 Key Relationships
One patient → many appointments
One appointment → one consultation (optional)
One consultation → many medicines & tests
One test order → multiple test items
One test item → one report
One invoice → multiple payments
Doctors ↔ Specialties (many-to-many)
🧠 Important Design Decisions
1. Appointment vs Consultation
Appointment represents booking
Consultation represents actual visit
Not all appointments lead to consultations
2. Previous Medication Handling
Previous medications are not stored separately
They are derived from:
consultation_medicines
past consultations
Additional support via patient_medical_history
3. Diagnostics Modeling
Tests are structured as:
test_orders → test_order_items → reports
This allows:
Multiple tests per consultation
Scalable lab integration
4. Billing System
Introduced invoice abstraction
Supports:
Partial payments
Multiple payment methods
5. Normalization
Followed 3NF (Third Normal Form)
Avoided redundancy
Used junction tables for M:N relationships
⚙️ Constraints & Data Integrity
Primary Keys (PK) for all entities
Foreign Keys (FK) for relationships
UNIQUE constraints (email, phone, 1:1 mappings)
CHECK constraints for enums (status, gender, etc.)
NOT NULL for critical attributes
Default values for timestamps and flags
🚀 Scalability Features

The system can be extended to support:

Multi-clinic / multi-branch systems
Online consultations (video)
Insurance & claims
E-prescriptions
Lab integrations
Analytics & reporting
🏆 Highlights
Clear separation of business domains
Real-world clinic workflow modeling
Strong relational integrity
Scalable diagnostics and billing system
Clean and readable ER structure
📎 Submission Notes
ER diagram is created using Eraser.io
All entities include:
Attributes
PK/FK
Constraints
Relationships are clearly defined and structured
