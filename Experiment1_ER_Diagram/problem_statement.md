# ER Diagram Workshop – Submission

## 📌 Objective 

To understand and apply **Entity-Relationship (ER) modeling concepts** by creating ER diagrams for real-world applications.

## 🎯 Purpose

This workshop provides hands-on experience in designing ER diagrams that represent:

* Entities
* Attributes
* Primary Keys (PK)
* Foreign Keys (FK)
* Relationships
* Cardinality
* Participation constraints
* Associative entities

---

# 📂 Scenarios Covered

This project contains ER diagrams for the following three real-world applications:

1. **City Fitness Club Management**
2. **City Library Event & Book Lending System**
3. **Restaurant Table Reservation & Ordering**

---

# 🏋️ Scenario A: City Fitness Club Management

### Business Context

FlexiFit Gym wants to manage its members, trainers, fitness programs, personal training sessions, attendance, and payments.

### Main Entities

* **MEMBER**
* **PROGRAM**
* **TRAINER**
* **MEMBER_PROGRAM**
* **PROGRAM_TRAINER**
* **PT_SESSION**
* **PAYMENT**

### Major Relationships

| Relationship                        | Cardinality |
| ----------------------------------- | ----------- |
| Member – Program                    | M:N         |
| Program – Trainer                   | M:N         |
| Member – Personal Training Session  | 1:M         |
| Trainer – Personal Training Session | 1:M         |
| Member – Payment                    | 1:M         |
| Personal Training Session – Payment | 1:0..1      |

### Key Design Decisions

The many-to-many relationships are resolved using associative entities:

* `MEMBER_PROGRAM`
* `PROGRAM_TRAINER`

The `PT_SESSION` entity records the personal training booking and attendance status.

---

# 📚 Scenario B: City Library Event & Book Lending System

### Business Context

The Central Library wants to manage book lending, members, cultural events, speakers, rooms, registrations, and overdue fines.

### Main Entities

* **MEMBER**
* **BOOK**
* **LOAN**
* **FINE**
* **EVENT**
* **EVENT_REGISTRATION**
* **SPEAKER**
* **EVENT_SPEAKER**
* **ROOM**

### Major Relationships

| Relationship    | Cardinality |
| --------------- | ----------- |
| Member – Loan   | 1:M         |
| Book – Loan     | 1:M         |
| Loan – Fine     | 1:0..1      |
| Member – Event  | M:N         |
| Event – Speaker | M:N         |
| Room – Event    | 1:M         |

### Key Design Decisions

Many-to-many relationships are resolved using:

* `EVENT_REGISTRATION`
* `EVENT_SPEAKER`

The `FINE` entity stores overdue charges associated with library loans.

---

# 🍽️ Scenario C: Restaurant Table Reservation & Ordering

### Business Context

A restaurant wants to manage customers, table reservations, food orders, dishes, categories, waiters, and billing.

### Main Entities

* **CUSTOMER**
* **TABLE**
* **RESERVATION**
* **WAITER**
* **ORDER**
* **ORDER_ITEM**
* **DISH**
* **CATEGORY**
* **BILL**
* **RESERVATION_WAITER**

### Major Relationships

| Relationship           | Cardinality |
| ---------------------- | ----------- |
| Customer – Reservation | 1:M         |
| Table – Reservation    | 1:M         |
| Reservation – Order    | 1:M         |
| Order – Dish           | M:N         |
| Category – Dish        | 1:M         |
| Reservation – Bill     | 1:1         |
| Reservation – Waiter   | M:N         |

### Key Design Decisions

The many-to-many relationships are resolved using:

* `ORDER_ITEM`
* `RESERVATION_WAITER`

`ORDER_ITEM` stores the quantity and unit price of each dish ordered.

---

# 📁 Project Structure

```text
ER-Diagram-Workshop/
│
├── README.md
│
├── diagrams/
│   ├── er_diagram_fitness.png
│   ├── er_diagram_library.png
│   └── er_diagram_restaurant.png
│
└── ER_Diagram_Workshop_Submission.pdf
```

---

# 🔑 ER Modeling Concepts Used

## Entity

An entity represents a real-world object about which information is stored.

Examples:

```text
MEMBER
TRAINER
BOOK
CUSTOMER
DISH
```

## Attribute

An attribute describes an entity.

Example:

```text
MEMBER
 ├── MemberID
 ├── Name
 ├── MembershipType
 └── StartDate
```

## Primary Key

A primary key uniquely identifies each entity instance.

Example:

```text
MemberID (PK)
```

## Foreign Key

A foreign key establishes a connection between entities.

Example:

```text
Reservation
 ├── ReservationID (PK)
 ├── CustomerID (FK)
 └── TableID (FK)
```

## Cardinality

Cardinality describes how many instances of one entity can be associated with another.

Common types:

* `1:1` — One-to-One
* `1:M` — One-to-Many
* `M:N` — Many-to-Many

---

# 🔗 Many-to-Many Relationships

Many-to-many relationships are converted into associative entities.

### Fitness Example

```text
MEMBER
   │
   │ M:N
   │
MEMBER_PROGRAM
   │
   │ M:N
   │
PROGRAM
```

### Library Example

```text
MEMBER
   │
   │ M:N
   │
EVENT_REGISTRATION
   │
   │ M:N
   │
EVENT
```

### Restaurant Example

```text
ORDER
   │
   │ M:N
   │
ORDER_ITEM
   │
   │ M:N
   │
DISH
```

---

# 🛠️ Tools Used

* **diagrams.net / draw.io** – ER diagram creation
* **Markdown** – Documentation
* **GitHub** – Version control and project submission
* **PDF** – Final workshop submission

---

# 📄 Submission

The completed submission contains:

* ✅ Scenario A – Fitness Club ER Model
* ✅ Scenario B – Library ER Model
* ✅ Scenario C – Restaurant ER Model
* ✅ Entity and attribute tables
* ✅ Relationship and constraint tables
* ✅ Assumptions
* ✅ ER diagrams
* ✅ Combined PDF

---

---

## 📌 Conclusion

This workshop demonstrates how ER modeling can be used to represent the structure of real-world database applications. The three scenarios demonstrate the use of entities, attributes, primary keys, foreign keys, relationships, cardinality, participation constraints, and associative entities in database design.
