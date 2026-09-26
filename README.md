# Hotel Booking Management System

## MySQL Mini Project

### Project Overview

The **Hotel Booking Management System** is a MySQL-based database project developed to manage hotel operations such as hotels, rooms, guests, bookings, and payments.

The system is designed for a hotel chain that operates multiple hotels in different cities. Each hotel contains different types of rooms, including Standard, Deluxe, and Suite rooms. Guests can book rooms for specific dates, and payment details are maintained for each booking.

This project demonstrates the practical use of relational database concepts and SQL queries.

---

## Scenario

A hotel chain owns multiple hotels across different cities. Each hotel has several rooms of different types.

Guests can:

- Book rooms for specific dates
- Check in and check out on selected dates
- Make payments for their bookings
- Have bookings with different statuses such as Booked, Active, Completed, or Cancelled

The system stores all this information in a structured relational database.

---

## Objectives

The main objectives of this project are:

- To manage hotel information.
- To maintain room details and room availability.
- To store guest information.
- To manage room bookings.
- To maintain check-in and check-out dates.
- To manage booking status.
- To record payment details.
- To maintain relationships between different tables.
- To practice SQL queries and database operations.

---

## Technologies Used

- **MySQL**
- **MySQL Workbench**
- **SQL**

---

## Database Structure

The database contains the following five tables:

```text
Hotels
   │
   │ 1 : M
   ↓
Rooms
   │
   │ 1 : M
   ↓
Bookings
   ↑
   │
Guests

Bookings
   │
   │ 1 : 1
   ↓
Payments
```

### Relationships

- One hotel can have many rooms.
- One room can have many booking records.
- One guest can make multiple bookings.
- Each booking belongs to one guest.
- Each booking belongs to one room.
- Each booking has payment information.

---

# Tables

## 1. Hotels

The `Hotels` table stores information about hotels.

| Column | Description |
|---|---|
| hotel_id | Unique ID of the hotel |
| hotel_name | Name of the hotel |
| city | City where the hotel is located |
| star_rating | Star rating of the hotel |

---

## 2. Rooms

The `Rooms` table stores information about rooms available in each hotel.

| Column | Description |
|---|---|
| room_id | Unique ID of the room |
| hotel_id | ID of the hotel |
| room_number | Room number |
| room_type | Type of room |
| price | Price of the room |
| status | Current room status |

Room types include:

- Standard
- Deluxe
- Suite

---

## 3. Guests

The `Guests` table stores information about hotel guests.

| Column | Description |
|---|---|
| guest_id | Unique ID of the guest |
| guest_name | Name of the guest |
| phone | Guest phone number |
| city | Guest city |

---

## 4. Bookings

The `Bookings` table stores information about room reservations.

| Column | Description |
|---|---|
| booking_id | Unique ID of the booking |
| guest_id | ID of the guest |
| room_id | ID of the booked room |
| check_in | Check-in date |
| check_out | Check-out date |
| booking_status | Status of the booking |

Booking statuses include:

- Booked
- Active
- Completed
- Cancelled

---

## 5. Payments

The `Payments` table stores payment information for bookings.

| Column | Description |
|---|---|
| payment_id | Unique ID of the payment |
| booking_id | ID of the booking |
| amount | Payment amount |
| payment_status | Status of the payment |

Payment statuses include:

- Paid
- Pending
- Refunded

---

# SQL Concepts Practiced

This project is created to practice important SQL and database concepts.

### Primary Key

Primary keys uniquely identify each record in a table.

Examples:

```text
hotel_id
room_id
guest_id
booking_id
payment_id
```

### Foreign Key

Foreign keys are used to create relationships between tables.

Examples:

```text
Rooms.hotel_id → Hotels.hotel_id

Bookings.guest_id → Guests.guest_id

Bookings.room_id → Rooms.room_id

Payments.booking_id → Bookings.booking_id
```

### One-to-Many Relationships

Examples:

- One hotel → Many rooms
- One guest → Many bookings
- One room → Many bookings

### INNER JOIN

Used to retrieve matching records from multiple related tables.

### LEFT JOIN

Used to retrieve all records from the left table, including records without matching records in the right table.

### Aggregate Functions

The project can use:

```text
COUNT()
SUM()
AVG()
MIN()
MAX()
```

### GROUP BY

Used to group records based on a particular column.

### HAVING

Used to filter grouped records.

### Date Functions

The `check_in` and `check_out` columns use the `DATE` data type and can be used for date-based calculations and filtering.

### Subqueries

Subqueries can be used to perform queries based on the result of another query.

### Window Functions

Window functions can be used to perform calculations across related rows without combining them into a single grouped row.

---

# Sample Data

The project contains sample data for:

### Hotels

- Grand Palace – Chennai – 5 Star
- Royal Inn – Bangalore – 4 Star
- Blue Moon – Hyderabad – 3 Star

### Guests

- Rahul
- Priya
- Arun
- Sneha
- Karthik

### Room Types

- Standard
- Deluxe
- Suite

### Booking Status

- Completed
- Active
- Booked
- Cancelled

### Payment Status

- Paid
- Pending
- Refunded

---

# Project Structure

```text
Hotel-Booking-Management-System
│
├── README.md
│
└── Database
    └── hotel_booking_management_system.sql
```

---

# How to Run the Project

### Step 1: Download the SQL File

Download:

```text
hotel_booking_management_system.sql
```

from the `Database` folder.

### Step 2: Open MySQL Workbench

Open **MySQL Workbench** and connect to your MySQL server.

### Step 3: Open the SQL File

Open the downloaded `.sql` file in MySQL Workbench.

### Step 4: Execute the SQL Queries

Execute the SQL statements to create the tables and insert the sample data.

### Step 5: View the Tables

Refresh the **Schemas** section.

The following tables should be available:

```text
Hotels
Rooms
Guests
Bookings
Payments
```

### Step 6: View the Data

Use:

```sql
SELECT * FROM Hotels;
SELECT * FROM Rooms;
SELECT * FROM Guests;
SELECT * FROM Bookings;
SELECT * FROM Payments;
```

---

# Example Query

### Display Guest Booking Details

```sql
SELECT 
    g.guest_name,
    b.booking_id,
    b.check_in,
    b.check_out,
    b.booking_status
FROM Guests g
INNER JOIN Bookings b
ON g.guest_id = b.guest_id;
```

This query displays the guest name along with their booking details.

---

# Learning Outcomes

After completing this project, students can understand and practice:

- Relational database design
- Primary Keys
- Foreign Keys
- Table relationships
- Data insertion and retrieval
- INNER JOIN
- LEFT JOIN
- Aggregate Functions
- GROUP BY
- HAVING
- Date Functions
- Subqueries
- Window Functions
- MySQL database management

---

# Conclusion

The **Hotel Booking Management System** is a MySQL mini project that demonstrates how a relational database can be used to manage hotels, rooms, guests, bookings, and payments.

The project provides practical experience in database design and SQL query writing while demonstrating relationships between multiple tables.
