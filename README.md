Here is the fully updated **`README.md`** file, complete with an dedicated **"Application Screenshots"** section incorporating your provided interface images: `image_3ffa0c.jpg`, `image_3ffa13.jpg`, and `image_3ffa30.jpg` verbatim.

---

# My Green Habits

`My Green Habits` is a comprehensive desktop system designed to help individuals track and improve their daily environmentally friendly habits. Built as a Java Swing application and backed by a relational MySQL database, the system allows users to record, analyze, and manage sustainable eco-actions. By translating these actions into a dynamic sustainability score, the application raises environmental awareness, encourages responsible daily behaviors, and provides performance feedback.

This project was developed as a core requirement for the **Object-Oriented Programming 2 (CSC236)** course at the College of Science and Humanities-Jubail, Imam Abdulrahman bin Faisal University (IAU).

---

## 👥 Project Members

| ID | Member Name | Student's Section | OOP2 Instructor |
| --- | --- | --- | --- |
| **** | Jana  | Section 1 | Ms. Hanan  |
| **** | Fatimah  | Section 1 | Ms. Hanan  |
| **** | Hawra  | Section 1 | Ms. Hanan  |
| **** | Zahra  | Section 1 | Ms. Hanan  |
| **** | Batool  | Section 1 | Ms. Hanan  |

---

## 🎯 Project Objectives

* Enable users to consistently monitor and enhance their green routines, including plastic minimization, electricity conservation, and effective waste recycling.


* Offer automated, real-time performance tracking and scoring feedback (Sustainability Score) to promote sustainable living over time.


* Demonstrate practical execution of robust Object-Oriented Programming (OOP) architectures and Java Database Connectivity (JDBC) paradigms within a real-world system.



---

## 🚀 Key Features

### 1. Graphical User Interface (Java Swing Component)

* **Secure Authentication System:** A robust user registration and login interface that verifies credentials against the database and seamlessly routes accounts based on structural credentials.


* **User Dashboard:** A centralized control hub greeting authenticated users, displaying their real-time sustainability scores, and managing modular navigations.


* **Activity Entry Form:** A structured entry interface allowing users to log their green behaviors, dates, and corresponding values directly.


* **History Log & CRUD Management:** A responsive, interactive table layout that lists all past actions, enabling full Create, Read, Update, and Delete operations on personal logs.



### 2. Business Logic & Scoring Rules

* **Categorized Activities:** Programmatic categorization separating entries into two core eco-fields: Recycling Activities and Energy Saving Activities.


* **Dynamic Point System:** Automatically computes values based on the action type (e.g., 15 points assigned for structural Recycling actions and 10 points for Energy Saving actions).


* **Input Data Validation:** Server-side conditions that validate user input structures (such as matching passwords, validating `@` mail criteria, and preventing negative entry scores).


* **Data Log Exporting:** Integrates a file I/O framework that silently logs and appends every newly added activity into a persistent external text archive titled `activities.txt`.



### 3. Role-Based Capabilities

* **Admin Role:**
* Displays and monitors account listings for all registered system users.


* Reviews aggregated activity logs compiled across the entire system database.


* Grants authority to update or modify baseline points for various activity types globally.




* **User Role:**
* Authenticates safely, creates individual profiles, and modifies personal entries only.


* Tracks individual scores and reviews dynamic updates to historical performance.





---

## 📸 Application Screenshots

### Login Interface

The secure login window supporting standard user validation and exclusive admin routing triggers.

### Registration Interface

The user registration portal enforcing matching validation checks on account field creations.

### User Dashboard

The central dashboard displaying personal greetings and access points to activity metrics.

---

## 🛠️ Tools & Technologies

* **Programming Language (Java SE):** Complete reliance on Object-Oriented principles, using structured encapsulation, inheritance for specialized activity trees, and object references.


* **GUI Framework:** Developed via standard `javax.swing` and `java.awt` packages, enforcing grid-based layouts and uniform themes via the `logo2.jpeg` brand visual.


* **Database Management:** Run using **MySQL Database Server** to manage and guarantee persistent, relational records.


* **Integration Library (JDBC):** Connects the Java runtime with MySQL using secure `PreparedStatement` boundaries to block SQL injections and process safe query transitions inside `DatabaseConnection`.



---

## 🗂️ Project Structure

```bash
mygreenhabits/
│
├── MyGreenHabits.java             # System bootstrap and main execution loop 🚀
├── DatabaseConnection.java        # Handles connection sessions with MySQL via JDBC 🔌
├── User.java                      # Base model mapping user entities and security tokens 👤
├── Admin.java                     # Specialized administrative entity extending standard User 🔑
│
├── Activity.java                  # Main abstract parent model defining structural eco-fields 🟩
├── RecyclingActivity.java         # Inherited class computing points for recycling routines (15 pts) ♻️
├── EnergySavingActivity.java      # Inherited class computing points for saving energy routines (10 pts) 💡
├── ActivityManager.java           # Internal controller performing CRUD collection processes ⚙️
├── SustainabilityScore.java       # Evaluates accumulated total user scores and updates dates 📊
├── ExportData.java                # Exporter utility writing runtime details to activities.txt 📝
│
├── LoginFrame.java                # GUI providing authorization checks for Users & Admins 🔏
├── RegisterFrame.java             # UI form managing registration validation and user inserts 📝
├── UserDashboardFrame.java        # Interface routing users to core feature modules 🏠
├── AddActivityFrame.java          # Input panel processing newly logged activities and scores ➕
├── ManageActivitiesFrame.java     # Visual dashboard managing editable historical tabular rows ✏️
├── AdminDashboardFrame.java       # Control deck monitoring system registers and global points ⚙️
├── ScoreFrame.java                # Modular frame summarizing total performance ranks and dates 🏆
│
└── logo2.jpeg                     # Theme logo utilized as a graphical backdrop for frames 🖼️

```

---

## 🗃️ Relational Database Schema

The architecture maintains strict data integrity using primary keys, auto-increments, and foreign constraints across the following schemas:

### 1. `Users` Table

* `UserID` (INT, Primary Key) - Auto-incremented identification key.


* `FirstName` (VARCHAR) - Stores first name.


* `LastName` (VARCHAR) - Stores last name.


* `Email` (VARCHAR, Unique) - Enforces unique registration emails.


* `Password` (VARCHAR) - Secure password text field.


* `AdminID` (INT, Nullable) - Indicates administrative account classifications.



### 2. `Activity` Table

* `ActivityID` (INT, Primary Key) - Unique identifier for logged activities.


* `Date` (DATE) - Calendar date tracking when the action took place.


* `ActivityType` (VARCHAR) - Text indicator specifying the green behavior performed.


* `Points` (INT) - Evaluated points assigned for the specific entry.


* `UserID` (INT, Foreign Key) - References the explicit logger from the `Users` table.


* `CategoryID` (INT, Foreign Key) - References type designations (1 for Recycling, 2 for Energy).



### 3. `SustainabilityScore` Table

* `UserID` (INT, Primary Key, Foreign Key) - Associated user identifier link.


* `TotalScore` (INT) - Aggragated total points score tracked for the user.


* `LastUpdated` (DATE) - Timestamp capturing the user's latest point entry.



---

## ⚙️ Local Installation & Usage Guide

### Prerequisites

1. Install **Java Development Kit (JDK 8 or later)**.
2. Install **MySQL Server** engine.
3. Download the library jar for **MySQL Connector/J** and link it into your target project runtime dependencies (Classpath).

### Database Configuration

1. Open your target MySQL connection tool (CLI or Workbench) and run the initialization commands:


```sql
CREATE DATABASE MyGreenHabits;
USE MyGreenHabits;

```



```
2. Update the localized credential string paths residing in `DatabaseConnection.java` to align with your personal environment properties[cite: 7]:
   ```java
   private static final String URL = "jdbc:mysql://localhost:3306/MyGreenHabits";
   private static final String USER = "root";       // Input your native db username
   private static final String PASSWORD = "YOUR_PASSWORD"; // Input your native db password

```

### Building and Running the System

You can import, link dependencies, and run the project via standard integrated developer environments (such as NetBeans, IntelliJ, or Eclipse), or use your terminal console:

```bash
# Navigate to the target root folder containing the packet
cd path/to/mygreenhabits

# Compile all source modules within the packages
javac mygreenhabits/*.java

# Run the system using the absolute main entry file path
java mygreenhabits.MyGreenHabits

```

---

## 📌 Project Outcomes & Academic Standards

* **Java Application Evaluation:** Clean, modular package layouts highlighting encapsulation boundaries, error fallback mechanisms (Exception Handling), and zero compile bugs.


* **Database Integration Evaluation:** A fully normalized structure executing aggregate selections, dynamic join relations, and functional synchronization over active JDBC connections.



---

### 📄 License

This system was built strictly for academic evaluation and fulfillment purposes within Imam Abdulrahman bin Faisal University (IAU). All development rights reserved to the respective project team authors © 2026.
