# Court Reservation System

A Django-based project for managing sports court reservations. This repository outlines the initial challenges, the evolution of the solution, and the technical approach used to ensure a smooth and secure booking experience for sports courts.

---

## Overview

The Court Reservation System is designed to provide a robust and reliable solution for users to reserve sports courts. The project incorporates user identity verification (including two-factor authentication via phone or email), strict scheduling validations, and conflict prevention to ensure that each reservation is valid and unique.

---

## Business Rules

The reservation process is governed by the following rules:

- **User Verification:**  
  Users must complete identity verification, including two-factor authentication (2FA), to confirm their telephone or email identity.

- **Valid Reservation Time:**  
  A reservation must occur within the court’s operational hours. Specifically:  
  **open_time** < **reservation_time** < **close_time**

- **Exclusive Time Slot:**  
  Each court can have only one reservation per time slot. If there is an attempt to reserve a slot that is already booked, the reservation will be considered invalid.

- **Dynamic Schedule Display:**  
  The system displays all days of the week in a table format with hourly time slots for each day the court is operational.  
  - The time slots are automatically generated based on the court's opening and closing times.  
  - Each slot clearly shows whether the court is already booked or available.

---

## Model Diagrams

**Old Model Diagram:**  
![image](https://github.com/user-attachments/assets/5225cdbd-4cf4-4eaf-a38c-69ef6d03e323)


**New Model Diagram:**  
![image](https://github.com/user-attachments/assets/77f52c68-492a-4d99-908e-b441118db5a5)


---

## Implementation Process

The project evolved through several stages as I tackled specific challenges and refined the solution:

1. **Identifying Key Business Requirements:**  
   Detailed mapping of the reservation process was performed to ensure that all rules were explicitly implemented.

2. **Model Structure Revision:**  
   Early versions of the model did not fully capture the complexity of the business rules. Through iterative improvements, the database schema was refactored—balancing user experience with data integrity.

3. **Conflict Prevention:**  
   Special care was taken to design a mechanism that prevents overlapping reservations. This is achieved by enforcing unique time slots per court and validating reservations based on the defined operational hours.

4. **User Verification and Security:**  
   Advanced security measures like two-factor authentication (2FA) were integrated, ensuring that only verified users can make reservations.

5. **Dynamic Scheduling Interface:**  
   The interface now visually represents the court availability across the week, generated dynamically from the operational hours settings.

---

## Conclusion

This project is a comprehensive solution for managing sports court reservations with a focus on user security, booking integrity, and system scalability. Your feedback is highly appreciated.

---

*Note:
The source code remains private.
This repository documents the challenges encountered and the solutions implemented during development.
The content will be updated as the project evolves—either through README revisions or new issues.*
