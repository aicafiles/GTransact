# GTransact

**GTransact** is a desktop-based GCash transaction management system built using Python's Tkinter library and MySQL. It enables users to record, update, and manage GCash cash-in and cash-out transactions with automatic computation of service charges and date tracking.

---

## Table of Contents 📚
- [GTransact](#gtransact)
  - [Table of Contents 📚](#table-of-contents-)
  - [About 📑](#about-)
  - [Features ✨](#features-)
  - [How to Use 🚀](#how-to-use-)
  - [Technologies Used ⚙️](#technologies-used-️)
  - [Database Setup 🗄️](#database-setup-️)
  - [Notes 📌](#notes-)

---

## About 📑
GTransact is designed to manage **GCash transactions** such as cash-in and cash-out services. It features a simple GUI where users can input transaction details, validate mobile and reference numbers, automatically calculate transaction fees, and view a list of all recorded transactions in a structured table format. It is suitable for small businesses or agents handling GCash services.

---

## Features ✨
* **Record Transaction:** Allows users to insert new transactions into the database.
* **Update Transaction:** Update an existing transaction based on the reference number.
* **Delete Transaction:** Delete a transaction using the reference number.
* **Clear Form:** Clears all form inputs and resets the summary display.
* **Auto Calculation:** Transaction fee is automatically calculated as 1% of the amount entered.
* **Tabular Display:** Displays all recorded transactions in a table format.

---

## How to Use 🚀
1. **Set up the MySQL database**

2. **Install dependencies:**
   ```bash
   pip install mysql-connector-python
   ```
3. **Run the application:**
   ```bash
   python main.py
   ```
4. **Perform Transactions:**
* Choose transaction type (Cash In/Out)
* Fill in the required details for the transaction
* The payment fee will be automatically calculated based on the transaction amount.
* The current date will auto-populate when the date field is focused.
* Use the available buttons to add, update, or delete transaction records.

---

## Technologies Used ⚙️
* **Python 3.x**
* **Tkinter**
* **MySQL**
* **mysql-connector-python**

---

## Database Setup 🗄️
1. **Open MySQL Command Line**
   ```bash
   mysql -u root -p
   ```
2. **Create and Use the Database**
   ```bash
   CREATE DATABASE Gcash;
   USE Gcash;
   ```
3. **Create the TRANSACTIONS Table**
   ```sql
   CREATE TABLE TRANSACTIONS (
      TRANSACTIONSTYPE VARCHAR(45) DEFAULT NULL,
      MOBILENUMBER BIGINT(11) DEFAULT NULL,
      AMOUNT DECIMAL(10, 2) DEFAULT NULL,
      PAYMENTFEE DECIMAL(10, 2) DEFAULT NULL,
      DATE DATE DEFAULT NULL,
      REFERENCENO BIGINT(13) NOT NULL,
      PRIMARY KEY (REFERENCENO)
   );
   ```
---

## Notes 📌
* Make sure MySQL server is running locally.
* Default credentials in code: user=root, password="" (empty). Adjust these as necessary.
* Reference numbers must be unique and exactly 13 digits.
* Mobile numbers must be 11 digits long.