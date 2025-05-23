# 🏋️‍♂️ Smart Fitness Management System (SFMS)

A Python-based console application built with Object-Oriented Programming (OOP) principles to streamline gym and fitness center operations. This system simulates a real-world fitness platform with modules for member management, class booking, trainer scheduling, and payment processing.

---

## 📌 Project Overview

With digital transformation reshaping the fitness industry, the **Smart Fitness Management System (SFMS)** provides a comprehensive solution to manage daily operations at a gym. Built for gym operators, fitness professionals, and administrative staff, SFMS simplifies workflows with a clean, menu-driven interface.

The system supports:

* Member registration and class tracking
* Trainer management and assignment
* Fitness class scheduling
* Payment processing and receipts
* Progress logging and revenue reporting

SFMS was developed using **Python** with **OOP design patterns**, ensuring modularity, reusability, and future extensibility such as GUI support or database integration.

---

## 🏗️ System Architecture

The SFMS consists of five main classes:

### 🔹 1. Member Class

* Stores member ID, name, age, membership type, fitness goals, and progress
* Methods for booking classes, updating memberships, and tracking progress

### 🔹 2. Trainer Class

* Manages trainer profiles, specializations, and assigned classes
* Supports multi-class schedules per trainer

### 🔹 3. FitnessClass

* Represents scheduled fitness sessions (e.g., Yoga, HIIT)
* Tracks assigned trainers, capacity, and enrolled members
* Validates class availability before booking

### 🔹 4. Transaction Class

* Handles membership and service payments
* Generates receipts with transaction details

### 🔹 5. FitnessManagementSystem (Main Controller)

* Manages user interaction, member/trainer registration, bookings, and financial reports
* Console-based, menu-driven system for seamless navigation

---

## 🔧 Software Development Model: Waterfall

The **Waterfall Model** was chosen for its structured and sequential design—ideal for academic and time-bound projects.

### 📋 1. Requirement Analysis

* Detailed specifications provided in a case study, outlining all features and class responsibilities

### 🧠 2. System Design

* Entities were mapped to Python classes with attributes and methods
* Object references modeled relationships like "members book classes" or "trainers manage sessions"

### 💻 3. Implementation

* All classes coded in Python following OOP best practices
* A `main()` function served as a testing interface with a dynamic console menu

### 🧪 4. Testing

* Manual test cases executed for key scenarios, including edge cases like overbooked classes

### 🚀 5. Deployment

* Delivered as a single `.py` script, fully functional through a terminal

### 🔄 6. Maintenance (Future Scope)

* Modular code structure supports enhancements such as authentication, data persistence, and GUI

---

## ✅ Features Implemented

* [x] Member registration and fitness class booking
* [x] Trainer scheduling and class management
* [x] Fitness class capacity enforcement
* [x] Payment and receipt generation
* [x] Progress tracking per member
* [x] Revenue and top class reports
* [x] Interactive menu for navigation and operations

---

## 🧪 Sample Test Cases

| Scenario           | Input                        | Expected Output                            |
| ------------------ | ---------------------------- | ------------------------------------------ |
| Register Member    | M001, Alice, 25, Premium     | "Member registered successfully!"          |
| Book Fitness Class | M001, C001, Trainer: John    | "Class booked successfully!"               |
| Process Payment    | M001, \$50, Service: Premium | Receipt with payment details               |
| Generate Revenue   | N/A                          | Total revenue + top class + active members |
| Track Progress     | M001, "Weight: 70kg"         | "Progress updated."                        |
| View Progress      | M001                         | List of all progress entries for Alice     |

---

## ⚠️ Limitations and Future Improvements

* **No Data Persistence**: Data is lost on exit. Future versions can integrate SQLite, CSV, or JSON storage.
* **Lacks GUI**: Implementing Tkinter or Flask would improve user experience.
* **No Role-based Access**: Admin/Trainer login and permissions should be added.
* **Limited Reporting**: Future analytics may include membership churn or trainer performance trends.

---

## 🧾 Conclusion

The **Smart Fitness Management System** is a functional, OOP-based Python application that simulates the operations of a digital gym platform. Despite being a solo project, it addresses all core requirements from the case study while maintaining a scalable design for future growth.

This project enhanced skills in:

* Object-Oriented Programming
* System design and class relationships
* Testing and interface usability
* Applying Waterfall methodology from planning to deployment

> 🔗 *This project is part of an academic submission for ICT702 and reflects real-world software development principles and practices.*
