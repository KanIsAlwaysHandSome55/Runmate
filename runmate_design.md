# RunMate – App Concept

## 1. App Overview

### 1.1 One-Sentence Pitch
RunMate is a simple fitness app that helps users track their running distance, time, and calories in real time.

---

## 2. Core Screens

1. Login / Sign Up Screen
2. Home Dashboard Screen
3. Start Run Screen
4. Run Summary Screen
5. Profile / Settings Screen

---

## 3. Screen Flow

Main Flow:
Login → Home Dashboard

Running Flow:
Home Dashboard → Start Run → Run Summary → Home Dashboard

Account Flow:
Home Dashboard → Profile / Settings → Home Dashboard
## 4. Basic Data Model

User:
- user_id
- name
- email
- password
- total_distance
- total_calories

Run Record:
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
   - Request Body: { distance, duration, calories, date }

---

### Profile
4. GET /profile  
   - Description: Get user profile information  

5. PUT /profile  
   - Description: Update user profile information  
- run_id
- user_id
- distance
- duration
- calories

- date
