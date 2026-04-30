# Parking Reservation System: Testing & Coverage Suite

## 📌 Project Overview
This project is a C++ implementation of a **Parking Reservation System** designed to demonstrate rigorous **Software Testing** methodologies. It manages parking slots for various vehicle types (2W, 4W, HV) and features a tiered pricing engine with automatic discounts.

The core of the project is a high-integrity **Test Runner** that executes 30 test cases (White Box and Black Box) and provides a detailed **Code Coverage Report** using manual instrumentation.

## 🚀 Key Features
*   **Entity Management**: Tracks `ParkingSlot` states (Available, Held, Reserved) and generates `Booking` records with unique QR codes.
*   **Fee Computation**: Tiered hourly rates with a 10% discount for long-stay parking (8+ hours).
*   **Transaction Rollback**: Simulates payment gateway failures to ensure that parking slots are released if a transaction fails (ensuring Data Atomicity).
*   **Live Coverage Tracking**: Built-in `CoverageTracker` to measure the effectiveness of the test suite in real-time.

---

## 🧪 Testing Methodologies

### 1. White Box Testing (Structural)
Focuses on the internal logic and control flow of the `reserveSlot()` method.
*   **Statement Coverage**: Ensures every line of the reservation logic is executed at least once.
*   **Branch Coverage**: Ensures all decision paths (Input validation, Slot availability, Payment success/failure) are traversed.
*   **Technique**: Manual instrumentation (marking nodes and edges via a global tracker).

### 2. Black Box Testing (Functional)
Focuses on the system's requirements and user-facing input boundaries.
*   **Equivalence Class Partitioning (ECP)**: Testing valid/invalid input groups (e.g., non-existent zones vs. valid zones).
*   **Boundary Value Analysis (BVA)**: Testing the exact limits of the duration range (0h, 1h, 23h, 24h, 25h).

---

## 📂 File Structure
*   `main.cpp`: Contains entity classes, control logic, test runner, and the coverage tracker.
*   `README.md`: Project documentation and usage guide.

---

## 🛠️ Installation & Usage

### Prerequisites
*   A C++ Compiler (GCC/G++, Clang, or MSVC).
*   Standard: **C++11** or higher.

### Compilation
Use the following command in your terminal:
```bash
g++ -o parking_suite main.cpp