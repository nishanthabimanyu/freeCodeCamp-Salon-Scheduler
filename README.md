# Salon Appointment Scheduler

This project is an interactive command-line application for managing salon appointments, built as part of the freeCodeCamp Relational Database curriculum. It uses **Bash scripting** for the user interface and **PostgreSQL** for database management.

---

## 🚀 Features

* **Service Selection:** Users can view a numbered list of available salon services.
* **Customer Management:**
    * Automatically checks if a customer exists by phone number.
    * Prompts for name if it's a new customer and stores their details.
    * Retrieves existing customer details for returning clients.
* **Appointment Scheduling:** Allows users to book appointments for a selected service at a specified time.
* **Database Integration:** Seamlessly interacts with a PostgreSQL database to store and retrieve customer, service, and appointment data.
* **Robust Input Handling:** Guides users through the booking process, including re-prompting for invalid service selections.

---

## 🛠️ Technologies Used

* **Bash:** For the interactive command-line interface.
* **PostgreSQL:** As the relational database management system.
* **`psql` client:** Used within the Bash script to execute SQL queries.
* **`sed`:** For string manipulation and formatting output.

---

## 📂 Project Structure
