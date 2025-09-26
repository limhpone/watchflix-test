# Watchflix – Movie Review Application 🎬
Aye Khin Khin Hpone(Yolanda Lim)_125970
A Ruby on Rails application for reviewing and discussing movies.  
This project is part of **FSAD 2024 Midterm Lab Part II** (10% of final grade).  
It is containerized with Docker and deployed on the CSIM server.  

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
 
    ## 🗂 Entity-Relationship (ER) Diagram (Text Format)

User ───────< Review >────── Movie
| |
| has_many | belongs_to
| |
└──────────────> Review <────┘


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

4. Push Image to Docker Hub
docker login
docker push yourdockerhubusername/watchflix:latest

5. Deploy on CSIM Server
ssh student@csim.ait.ac.th
docker pull yourdockerhubusername/watchflix:latest
docker run -d -p <your-port>:3000 --name stXXXXXX_movie_db yourdockerhubusername/watchflix:latest


Example: http://csim.ait.ac.th:3001

## 🗂 System Architecture

Movie: title, year

Review: content, movie_id, user_id

User: first_name, last_name, email, password

(See diagram in assignment sheet)

📄 Submission Details

Name: [Your Name]

Student ID: [Your ID]

GitLab Repo URL: [link here]

CSIM Deployment URL: [http://csim.ait.ac.th
:PORT]

Docker Hub Image URL: [https://hub.docker.com/r/yourdockerhubusername/watchflix
]

## 📝 Notes

Use different ports if teammates are on the same server.

Container names prefixed with Student ID (e.g., st123456_movie_db).

Validations prevent empty movie titles/years and empty reviews.
