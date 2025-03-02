# SzlachetnaPaczka (Charity donation app)

## Project Overview

This project is designed to support the **"Szlachetna Paczka"** charity initiative by managing donations and coordinating aid for families in need. The system enables structured organization of donation processes by involving different user roles: caretakers, donors, and beneficiary families (grouped as help groups).

## Functional Requirements

- **Public Access:** Users can browse the database without an account.  
- **User Roles:**  
  - **Caretaker**  
    - Responsible for managing a **help group**, coordinating collections, and specifying drop-off locations and schedules.  
    - A caretaker may own a car, allowing them to reach remote areas.  
    - Each help group is assigned a single caretaker.  
  - **Help Group**  
    - Represents a family or a group of families in need.  
    - Each group is assigned a **poverty level** (`low`, `mid`, `high`) and a dedicated caretaker.  
  - **Donor**  
    - Can contribute to a **help group** by donating money or delivering selected products to designated collection points.  
- **Needs Management:** Each **help group** can list required **products** along with specified quantities.  
- **Donation Records:** The system tracks **donations**, including financial contributions and physical items.  

## Non-Functional Requirements

- **Performance & Scalability** – Efficient handling of multiple users, optimized PostgreSQL queries.  
- **Security** – Secure authentication, encrypted sensitive data, fraud protection for donations.  
- **Usability** – Intuitive UI, accessible for users with disabilities (WCAG compliance).  
- **Reliability** – Minimal downtime, regular database backups.  
- **Development & Deployment** – Backend: Flask (Python), Frontend: React, Database: PostgreSQL.  
- **Internet Connection** – Required for full functionality.  

## Database Schema

The database consists of the following key entities:  

- **`user_data`** – Stores user credentials, including email, phone number, and password hash.  
- **`caretaker`** – Manages a **help group**, specifies drop-off locations, and coordinates donation schedules.  
- **`help_group`** – Represents families or groups of families in need, classified by a **poverty level**.  
- **`product`** – Defines the types of products that can be donated.  
- **`needs`** – Links products to **help groups**, specifying required quantities.  
- **`donor`** – Tracks donors, their contributions, and accumulated points.  
- **`donations`** – Logs financial and item donations, linking donors to **help groups**.  
- **`person`** – Stores personal details of users, linked to their roles (donor, caretaker, or beneficiary).  

## Data Population

The database was populated using **Mockaroo** to generate sample data. The data insertion process was automated using **Python** with the **psycopg2** library, ensuring efficient data entry into **PostgreSQL**.

## Technology Stack

- **Backend:** Python, Flask  
- **Frontend:** React  
- **Database:** PostgreSQL  

## Entity-Relationship Diagram (ERD)
![ERD](https://github.com/user-attachments/assets/57c8ec7e-f025-4d96-85f3-71e50111b4dd)

## Database diagram
![PostgreSQL_diagram](https://github.com/user-attachments/assets/99c078b2-a333-4a8d-934e-fe466f351b31)

## User Interface Preview

The following screenshots showcase key views of the application:  

- **Welcome Page** – The main landing page of the application.  
- **Fundraising View (Donor Role)** – Allows donors to contribute to selected causes and see their donations.  
- **Fundraising View (Caretaker Role)** – Displays available groups for caretakers; they can take responsibility for groups without an assigned caretaker.  
- **Caretaker Dashboard** – A dedicated section where caretakers track their assigned groups and confirm successful deliveries of needed products.  
- **Account Management** – Screens for user registration and login.  
- **User Profiles** – Views for donor and caretaker profiles, including editable user information.  
- **Error Handling** – Example of an invalid login attempt.  

<img width="1000" alt="Obraz5" src="https://github.com/user-attachments/assets/4a3f9bc1-bceb-4e43-9a02-a3304054dca5" />

<img width="500" alt="Obraz5" src="https://github.com/user-attachments/assets/2b489a1d-0044-409d-96fe-b09a3af068fc" />
<img width="500" alt="Obraz5" src="https://github.com/user-attachments/assets/d97f646f-e969-49e2-aa54-757dd6e059b7" />

<img width="500" alt="Obraz5" src="https://github.com/user-attachments/assets/b5b8faa6-1600-47d8-88ef-bba5f2e87076" />
<img width="500" alt="Obraz6" src="https://github.com/user-attachments/assets/77e10881-da2b-4d47-ab00-faeb25872644" />

<img width="333" alt="Obraz4" src="https://github.com/user-attachments/assets/43cdffed-0361-42e5-b0a2-ad93a5b7fc44" />
<img width="333" alt="Obraz11" src="https://github.com/user-attachments/assets/13e1481f-0b23-4464-9d20-464ba2987fa2" />
<img width="333" alt="Obraz12" src="https://github.com/user-attachments/assets/e91c1d58-3f65-49c6-973c-bb3d26105ee6" />

## Launching backend
    1. sudo service postgresql start
    2. make

## Launching frontend
    1. cd /src/react/
    2. npm install
    3. npm start
