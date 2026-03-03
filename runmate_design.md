# RunMate – App Concept

## 1. App Overview

### 1.1 One-Sentence Pitch
RunMate is a simple fitness app that helps beginners track their running distance, time, and calories without overwhelming features.

---

## 2. Core Screens

1. Login / Sign Up Screen  
2. Home Dashboard Screen  
3. Start Run Screen  
4. Run Summary Screen  
5. Profile / Settings Screen  

---

## 3. Screen Flow

### Root Screen:
Login / Sign Up Screen  

### Navigation Type:
Bottom Tab Bar  

### Main Flow:
Login → Home Dashboard  

### Running Flow:
Home Dashboard → Start Run → Run Summary → Home Dashboard  

### Account Flow:
Home Dashboard → Profile / Settings → Home Dashboard  

---

## 4. Basic Data Model

### User:
- user_id
- name
- email
- password
- total_distance_km
- total_calories

### Run Record:
- run_id
- user_id
- distance_km
- duration_minutes
- calories_burned
- date
- average_pace

---

## 5. API Design

### Authentication

1. POST /login  
   - Description: User login with email and password  
   - Request Body: { email, password }  
   - Response: { user_id, token }

---

### Run Management

2. GET /runs  
   - Description: Get all run records for the logged-in user  

3. POST /runs  
   - Description: Save a new run record  
   - Request Body: { distance_km, duration_minutes, calories_burned, date }

---

### Profile

4. GET /profile  
   - Description: Get user profile information  

5. PUT /profile  
   - Description: Update user profile information  

---

## 6. JSON Data Model

### 6.1 Core Entity: Run

```json
{
  "run_id": "run_001",
  "user_id": "user_123",
  "distance_km": 3.5,
  "duration_minutes": 28,
  "calories_burned": 240,
  "date": "2026-02-01",
  "average_pace": "8:00 min/km"
}
```

### 6.2 User Data

```json
{
  "user_id": "user_123",
  "name": "Kaung Khant Soe Moe",
  "email": "kaung@example.com",
  "avatar_url": "https://example.com/avatar.png",
  "total_distance_km": 42.5,
  "total_runs": 15,
  "goal_km_per_week": 10
}
```
---

## 7. API Bridge (Connecting Client & Server)

### 7.1 How Does the App Talk to the Backend?

The mobile app communicates with the backend server using RESTful API endpoints over HTTP.  
The client sends requests (GET, POST, PUT) and receives JSON responses.

---

### 7.2 Three Most Important API Actions

| Action Name | HTTP Method | Endpoint URL | Data Sent | Data Returned |
|------------|------------|--------------|-----------|--------------|
| Login | POST | /api/v1/auth/login | { email, password } | { token, user_id } |
| Create Run | POST | /api/v1/runs | { distance_km, duration_minutes, calories_burned, date } | { run_id, message } |
| Get Runs | GET | /api/v1/runs | token (in header) | List of run records |
