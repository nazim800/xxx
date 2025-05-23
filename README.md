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
## 🗒️ Source Code

```python
import datetime

# ---------------- Member Class ---------------- #
class Member:
    def __init__(self, member_id, name, age, membership_type, goals):
        self.member_id = member_id
        self.name = name
        self.age = age
        self.membership_type = membership_type
        self.goals = goals
        self.booked_classes = []
        self.progress_updates = []

    def change_membership(self, new_type):
        self.membership_type = new_type

    def book_fitness_class(self, fitness_class):
        if fitness_class.add_member(self):
            self.booked_classes.append(fitness_class)
            print(f"{self.name} has booked the {fitness_class.name} class.")
        else:
            print("Booking failed. Class is full.")

    def add_progress(self, update):
        self.progress_updates.append(update)
        print("Progress recorded successfully.")

# ---------------- Trainer Class ---------------- #
class Trainer:
    def __init__(self, trainer_id, name, specialty):
        self.trainer_id = trainer_id
        self.name = name
        self.specialty = specialty
        self.classes_assigned = []

    def assign_class(self, fitness_class):
        self.classes_assigned.append(fitness_class)

    def show_schedule(self):
        print(f"\nSchedule for Trainer {self.name}:")
        for c in self.classes_assigned:
            print(f" - {c.name} on {c.schedule}")

# ---------------- Fitness Class ---------------- #
class FitnessClass:
    def __init__(self, class_id, name, trainer, capacity, schedule):
        self.class_id = class_id
        self.name = name
        self.trainer = trainer
        self.capacity = capacity
        self.schedule = schedule
        self.enrolled_members = []

    def add_member(self, member):
        if len(self.enrolled_members) < self.capacity:
            self.enrolled_members.append(member)
            return True
        return False

    def remove_member(self, member):
        if member in self.enrolled_members:
            self.enrolled_members.remove(member)

# ---------------- Transaction Class ---------------- #
class Transaction:
    def __init__(self, transaction_id, member, amount, service):
        self.transaction_id = transaction_id
        self.member = member
        self.amount = amount
        self.date = datetime.date.today()
        self.service = service

    def show_receipt(self):
        print("\nReceipt")
        print(f"Transaction ID: {self.transaction_id}")
        print(f"Member: {self.member.name}")
        print(f"Membership Type: {self.member.membership_type}")
        print(f"Service: {self.service}")
        print(f"Amount Paid: ${self.amount:.2f}")
        print(f"Date: {self.date}")
        print("----------------------------")
```
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

## 👽 Conclusion

The **Smart Fitness Management System** is a functional, OOP-based Python application that simulates the operations of a digital gym platform. Despite being a solo project, it addresses all core requirements from the case study while maintaining a scalable design for future growth.

This project enhanced skills in:

* Object-Oriented Programming
* System design and class relationships
* Testing and interface usability
* Applying Waterfall methodology from planning to deployment

