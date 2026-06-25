# Course Enrollment System

## 📌 Overview

Course Enrollment System is a console-based **C++** application that simulates an academic course registration process followed in universities. The system manages students, courses, prerequisites, enrollment limits, timetable slot conflicts, and waitlists using **Object-Oriented Programming (OOP)** principles and **Standard Template Library (STL)** containers.

This project was implemented as a robust solution to a problem statement inspired by an Object-Oriented Programming lab assignment at **IIT Madras**.

---

## 🎯 Problem Statement

Design and implement a Course Enrollment Management System that supports:
* **Student Registration:** Onboarding profiles with complete historical records of previously cleared courses.
* **Course Creation:** Defining prerequisites, strict capacity ceilings, and structured weekly timetable slots.
* **Prerequisite Validation:** Ensuring students have completed foundational courses before advanced registration.
* **Conflict Prevention:** Identifying and blocking duplicate enrollments or overlapping timetable slot clashes.
* **Automated Queue Management:** Maintaining a waitlist once a course reaches peak capacity.
* **Dynamic Seat Allocation:** Automatically promoting the next eligible student in line when an active seat is vacated.

---

## 🚀 Features

### 👤 Student Management
* Add new student records dynamically to the system ledger.
* Maintain a persistent, searchable history of completed courses.
* Track actively enrolled course blocks and occupied timetable slots in real time.

### 📚 Course Management
* Add new courses with detailed credit weights to the active academic catalog.
* Establish complex prerequisite dependencies for progressive course progression.
* Assign distinct timetable slots and enforce max seat capacity constraints.
* ### 🛡️ Enrollment & Validation System
* **Prerequisite Checking:** Scans completed student history before authorizing registration.
* **Slot Clash Detection:** Cross-checks new course requests against a student's active schedule matrix.
* **Capacity Tracking:** Routes overflowing sign-ups directly to a FIFO waitlist structure if all other conditions are met.

### 🔄 Course Withdrawal
* Drop currently active courses cleanly.
* Automatically updates the underlying queue to fill empty slots using waitlist polling.

---

## 🛠️ Technologies Used

* **Language:** C++
* **Paradigm:** Object-Oriented Programming (Encapsulation, Friend Classes, Structural Relationships)
* **Library:** Standard Template Library (STL)
* **Architecture:** Rule-Based Validation Matrix & Event Queue Design

---

## 📊 Data Structures

The application utilizes optimized STL containers to map relationships and manage scheduling bounds efficiently:

| Structure | Data Model Mapping | Technical Purpose |
| :--- | :--- | :--- |
| `std::map` | `ID ➔ Object` | Provides fast search, retrieval, and modification matrices for student and course indices. |
| `std::set` | `Course_IDs` / `Slots` | Handles mathematical membership testing for prerequisites, completed records, active courses, and slot conflicts. |
| `std::queue` | `Waiting_Students` | Implements a fair FIFO (First-In, First-Out) pipeline to handle course registration overflows. |
| `std::map<int, string>` | `Order_Index ➔ Student` | Manages stable enrollment ordering and chronological registration queues inside a course. |
---

## 🎮 Supported Operations

The system processes the following space-separated console commands:

* `add_student [id] [name] [year] [completed_count] [course1...]`
* `add_course [code] [name] [credits] [capacity] [slot] [prereq_count] [prereq1...]`
* `enroll [student_id] [course_code]`
* `drop [student_id] [course_code]`
* `print [course_code]`

---

## 📘 Learning Outcomes

This project demonstrates proficiency in:
* **Class Design & Encapsulation:** Isolating domain boundaries and utilizing `friend` relationships cleanly.
* **STL Container Optimization:** Matching container profiles (`set` vs `queue` vs `map`) to exact access complexity demands.
* **Constraint-Based Validation:** Building relational logic checks that model real-world operational rules.
* **System Event Modeling:** Designing self-healing queues to handle background resource allocation tasks.

---

## Note

This implementation is based on a structured lab specification provided by senior students as part of the Object-Oriented Programming laboratory practice at IIT Madras. The codebase represents an independent, optimized implementation of the specified behavioral requirements.

---

## Author

**RISHI GOUTHAM**
*C++ | Systems Programming | Computer Science Student*
Developed as part of OOP practice and coursework preparation.
