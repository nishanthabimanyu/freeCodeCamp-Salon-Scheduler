# 💇‍♀️ Salon Appointment Scheduler

This project is an interactive command-line application built with **Bash** and **PostgreSQL** to manage salon appointments. It allows customers to book services, handles new and existing customer data, and schedules appointments efficiently.

Developed as one of the required projects for **freeCodeCamp's Relational Database certification**.

---

## ✨ Features

* **Service Selection:** Displays a numbered list of available salon services.
* **Customer Management:**
    * Checks for existing customers by phone number.
    * Prompts for name and registers new customers if their phone number is not found.
* **Appointment Booking:** Allows customers to select a service and schedule an appointment time.
* **Confirmation:** Provides a clear confirmation message after a successful appointment booking.
* **Robust Input Handling:** Guides users through the process and re-prompts for valid input when necessary (e.g., invalid service selection).

---

## 🛠️ Technologies Used

* **Bash:** For the interactive command-line interface.
* **PostgreSQL:** As the relational database to store salon data (services, customers, appointments).
* **`psql` client:** Used within the Bash script to interact with the PostgreSQL database.
* **`sed`:** For text processing and formatting output.

---

## 🚀 How to Run

To run this project, you'll need **PostgreSQL** installed and a **Bash** environment (like Linux, macOS, or Git Bash on Windows). This project was developed in a Gitpod virtual machine provided by freeCodeCamp.

### 1. Database Setup

First, create the database and tables, and populate the `services` table.

```bash
# 1. Create the 'salon' database
psql --username=freecodecamp --dbname=postgres -c "CREATE DATABASE salon;"

# 2. Connect to the 'salon' database and create tables
psql --username=freecodecamp --dbname=salon <<EOF
CREATE TABLE services (
  service_id SERIAL PRIMARY KEY,
  name VARCHAR(255) NOT NULL
);

CREATE TABLE customers (
  customer_id SERIAL PRIMARY KEY,
  phone VARCHAR(20) UNIQUE NOT NULL,
  name VARCHAR(255) NOT NULL
);

CREATE TABLE appointments (
  appointment_id SERIAL PRIMARY KEY,
  customer_id INT NOT NULL,
  service_id INT NOT NULL,
  time VARCHAR(50) NOT NULL,
  FOREIGN KEY (customer_id) REFERENCES customers(customer_id),
  FOREIGN KEY (service_id) REFERENCES services(service_id)
);

-- Populate initial services
INSERT INTO services (name) VALUES ('cut'), ('color'), ('perm');
EOF
