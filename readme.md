# Watchflix – Movie Review Application 🎬
Aye Khin Khin Hpone(Yolanda Lim)_125970
A Ruby on Rails application for reviewing and discussing movies.  
It is containerized with Docker and deployed on the CSIM server.  
The goal of this lab was to set up a production-ready Rails app with **PostgreSQL and Docker**, deployed on the **CSIM server**.

---
## Application Description

**Watchflix** is a platform where users can review and discuss their favorite movies.  
Users can add a movie, browse movies in the system, and write reviews for them.  
Each movie shows the number of reviews it has received.  

---

## ✅ Features Implemented
- **Authentication**: Only logged-in users can add, edit, or delete movies/reviews.  
- **Movies Index Page**:
  - Displays all movies with title, year, and number of reviews.  
  - Acts as the homepage of the application.  
- **Movie Show Page**:
  - Displays movie details.  
  - Shows all reviews with reviewer’s name.  
  - Allows logged-in users to submit reviews (cannot be empty).  
- **Validations**:
  - Movies require a title and year.  
  - Reviews require non-empty content.
 
---
## 🗂 Basic System Architecture

- **Movie**  
  - id (integer)  
  - title (string)  
  - year (string)  

- **Review**  
  - id (integer)  
  - content (string)  
  - user_id (integer)  
  - movie_id (integer)  

- **User**  
  - id (integer)  
  - first_name (string)  
  - last_name (string)  
  - email (string)  
  - password (string)  

---

### Relationships
- **User → Review**: One user can write many reviews.  
- **Movie → Review**: One movie can have many reviews.  
- **Review → User**: Each review belongs to exactly one user.  
- **Review → Movie**: Each review belongs to exactly one movie.  

---

## ⚙️ Prerequisites
Before running locally, install:
- [Docker](https://docs.docker.com/get-docker/)  
- [Docker Compose](https://docs.docker.com/compose/)  
- Git  

Optional (for local development without Docker):  
- Ruby 3.x  
- Rails 7.x  
- PostgreSQL  

---

## 🚀 Setup & Run Instructions

### 1. Clone the Repository
```bash
git clone <your-gitlab-repo-url>
cd watchflix

## 2. Build Docker Image
docker build -t yourdockerhubusername/watchflix:latest .

3. Run with Docker Compose
docker-compose up

App will be available at: http://localhost:3000 

📄 Submission Details

Name: Aye Khin Khin Hpone (Yolanda Lim)

Student ID: st125970

GitLab Repo URL: https://gitlab.com/ait-fsad-2024/watchflix-st125970

CSIM Deployment URL: http://csim.ait.ac.th:3001

Docker Hub Image URL: https://hub.docker.com/r/yolandalim/watchflix

📝 Notes

Application passes validation rules (no empty movies or reviews).

Deployment tested locally and on CSIM server.

Containerized using Rails + PostgreSQL + Docker Compose.
