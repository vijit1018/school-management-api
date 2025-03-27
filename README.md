# School Management API

## Overview
This project is a **School Management System API** built using **Node.js**, **Express.js**, and **MySQL**. It provides two main functionalities:
1. **Add a School** – Allows users to add new schools with details such as name, address, latitude, and longitude.
2. **List Schools** – Fetches a sorted list of schools based on proximity to a given user location.

## Features
- **RESTful APIs** with proper validation and error handling.
- **Proximity-based sorting** using the Haversine formula.
- **Cloud-based MySQL database** (PlanetScale) for easy access without local installation.
- **Deployed on Render** for live API access.
- **Postman Collection** for easy API testing.

## Tech Stack
- **Backend:** Node.js, Express.js
- **Database:** MySQL (PlanetScale)
- **Hosting:** Render
- **Testing:** Postman

## API Endpoints
### 1. Add School
- **Endpoint:** `/addSchool`
- **Method:** `POST`
- **Request Body:**
```json
{
  "name": "Greenwood High School",
  "address": "123 Main St, Bangalore",
  "latitude": 12.9716,
  "longitude": 77.5946
}
```
- **Response:**
```json
{
  "message": "School added successfully!",
  "schoolId": 1
}
```

### 2. List Schools (Sorted by Proximity)
- **Endpoint:** `/listSchools`
- **Method:** `GET`
- **Query Parameters:** `latitude`, `longitude`
- **Example Request:** `/listSchools?latitude=12.9716&longitude=77.5946`
- **Response:**
```json
[
  {
    "id": 1,
    "name": "Greenwood High School",
    "address": "123 Main St, Bangalore",
    "latitude": 12.9716,
    "longitude": 77.5946,
    "distance": 1.5
  }
]
```

## Database Schema (MySQL)
```sql
CREATE TABLE schools (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    address VARCHAR(255) NOT NULL,
    latitude FLOAT NOT NULL,
    longitude FLOAT NOT NULL
);
```

## Setup Instructions
### 1. Clone the Repository
```sh
git clone https://github.com/your-repo/school-management.git
cd school-management
```
### 2. Install Dependencies
```sh
npm install
```
### 3. Set Up Environment Variables
Create a `.env` file and add the following details:
```
DB_HOST=your-database-host
DB_USER=your-username
DB_PASSWORD=your-password
DB_NAME=school_management
PORT=3000
```
### 4. Initialize the Database
```sh
node setup.js
```
### 5. Start the Server
```sh
node server.js
```
### 6. Test APIs Using Postman
Import the Postman Collection and test the APIs.

## Deployment
The API is hosted on Render. Use the live endpoint to test the API.

## Postman Collection
- Download the **Postman Collection** from [this link](#) (Replace `#` with your actual link).

## Contributors
- **Your Name** – Developer

## License
This project is licensed under the MIT License.

