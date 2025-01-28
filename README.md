# IgnTattoo - Social Platform for Tattoo Artists & Designers 🎨⚡

**IgnTattoo** is a **mobile social platform** designed exclusively for tattoo artists and tattoo designers. It allows artists to showcase their work, connect with clients, manage appointments, and collaborate on projects. Built with modern technologies like **React Native**, **Expo**, **Express.js**, and **PostgreSQL**, it offers a seamless and professional experience.

---

## ✨ Key Features

- **Artist Portfolio**: High-quality image uploads with specific metadata (style, body placement, ink type).
- **Artist Discovery**: Search by location, style (#Traditional, #Watercolor, #Blackwork), and availability.
- **Social Interaction**: Like, comment, and direct messaging system between users.
- **Appointment Management**: Schedule appointments, reminders, and status tracking.
- **Collaborative Projects**: Spaces for designers and tattoo artists to collaborate on custom projects.
- **Secure Authentication**: JWT with user roles (artist/client).

---

## 🛠 Technologies Used

**Frontend**:

- **React Native (Expo SDK)**: Cross-platform development.
- **NativeWind**: Utility-first styling.
- **Reanimated/GestureHandler**: Smooth animations.
- **Image Picker/Camera**: Image and photo handling.

**Backend**:

- **Node.js + Express**: RESTful API.
- **PostgreSQL**: Relational database.
- **JWT**: Authentication and authorization.

**DevOps**:

- **GitHub Actions**: CI/CD Pipeline.
- **Expo Application Services**: OTA updates.
- **Docker** (optional): Containerization.

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/bealed0n/ign_tattoo.git
cd Capstone
```

### 2. Install Dependencies

#### Backend

1. Navigate to the backend folder:
   ```bash
   cd backend-ign-tattoo-app
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm run dev
   ```

#### Frontend

1. Navigate to the frontend folder:
   ```bash
   cd ../frontend-ign-tattoo-app
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the Expo project:
   ```bash
   npx expo start
   ```

---

## 🗃️ Database Structure (PostgreSQL)

The project uses **PostgreSQL** as its database. Below are the main tables:

### 1. Users (`users`)

| Column      | Type         | Description              |
| ----------- | ------------ | ------------------------ |
| id          | SERIAL       | Unique user identifier   |
| username    | VARCHAR(50)  | Username                 |
| email       | VARCHAR(100) | User email               |
| password    | VARCHAR(255) | Encrypted password       |
| bio         | TEXT         | User description         |
| profile_pic | VARCHAR(255) | Profile picture URL      |
| created_at  | TIMESTAMP    | Account creation date    |
| role        | VARCHAR(50)  | User role (e.g., 'user') |

### 2. Appointments (`appointments`)

| Column              | Type        | Description                            |
| ------------------- | ----------- | -------------------------------------- |
| id                  | SERIAL      | Unique appointment identifier          |
| user_id             | INTEGER     | ID of the user booking the appointment |
| tattoo_artist_id    | INTEGER     | ID of the tattoo artist                |
| date                | DATE        | Appointment date                       |
| time                | TIME        | Appointment time                       |
| description         | TEXT        | Appointment description                |
| status              | VARCHAR(20) | Appointment status (e.g., 'pending')   |
| reference_image_url | TEXT        | Reference image URL                    |

### 3. Designer Projects (`designer_projects`)

| Column       | Type          | Description                           |
| ------------ | ------------- | ------------------------------------- |
| id           | SERIAL        | Unique project identifier             |
| designer_id  | INTEGER       | ID of the designer                    |
| title        | VARCHAR(255)  | Project title                         |
| description  | TEXT          | Project description                   |
| image        | VARCHAR(255)  | Project image URL                     |
| price        | DECIMAL(10,2) | Project price                         |
| created_at   | TIMESTAMP     | Project creation date                 |
| currency     | VARCHAR(10)   | Price currency                        |
| is_available | BOOLEAN       | Indicates if the project is available |

---

## Project Structure

```
Capstone/
│
├── backend-ign-tattoo-app/     # Server code (Express.js)
├── frontend-ign-tattoo-app/    # Client code (React Native)
│
└── README.md                   # Project documentation
```
