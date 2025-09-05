### Lab CRUD API


### PROJECT OVERVIEW
The API provides:
- Manage 'students' (post, view/get, update, delete)
- Manage 'courses' (post, view/get, update, delete)
- MySQL database integration
- Built with Node.js, Express, and MySQL
- Can be tested using Postman for sending requests and viewing responses


### Setup Steps

1. Clone the repository
   ```bash
   git clone https://github.com/riyoki/lab-crud-api.git
   cd lab-crud-api
   
2. Install dependencies
   ```bash
   npm install
   
3. Configure environment variables
   Copy .env.example to .env
   
   Fill in your MySQL details:
   PORT=yourport
   DB_HOST=yourhost
   DB_USER=yourusername
   DB_PASSWORD=yourpassword
   DB_NAME=yourdbname

4. Setup Database
   - Open phpMyAdmin
     Usually at http://localhost/phpmyadmin (if you’re using XAMPP).
  - Create a new database
    - On the left sidebar, click New.
    - Enter your database name.
    - Choose utf8mb4_general_ci as collation.
    - Click Create.

 - Create the students table
    - Select the database you just created.
    - Click Create table and name it as students.
    - Define the columns:
      - id (INT, AUTO_INCREMENT, PRIMARY KEY)
      - name (VARCHAR(50))
      - email (VARCHAR(100), UNIQUE)
      - course (VARCHAR(100))
      - year_level (INT)
     
   - Create the courses table
    - Inside the same database, click Create table and name it as courses.
    - Click Create table and name it students.
    - Define the columns:
      - id (INT, AUTO_INCREMENT, PRIMARY KEY)
      - code (VARCHAR(50), UNIQUE)
      - title (VARCHAR(50))
      - units (INT)
      - created_at (TIMESTAMP, default CURRENT_TIMESTAMP)
     
   - Verify Tables
      - On the left sidebar, you should now see both students and courses tables inside your database.
      - You can click each table and then click Structure to confirm the fields.
    
### How to Run

  1. Run the server.js through VSCode
  2. Check if it’s working:
     - GET http://localhost:3000/api/health (Run through postman/browser)
     - You should get a JSON response similar to:
       {
         "status": "ok",
         "db": "connected",
         "time": "2025-09-04T07:59:08.035Z"
       }

### List of Endpoints

Example Base URL: http://localhost:3000 

                Students
| Method |      Endpoint       |     Description      |
| ------ | ------------------- | -------------------- |
| POST   |   `/api/students`   | Create a new student | 
| GET    |   `/api/students`   c|   Get all students   |
| GET    | `/api/students/:id  |   Get student by ID  | 
| PUT    | `/api/students/:id` | Update student by ID |
| DELETE | `/api/students/:id` | Remove student by ID |


                 Courses
| Method |      Endpoint       |     Description      |
| ------ | ------------------- | -------------------- |
| POST   |   `/api/courses`    | Create a new course  | 
| GET    |   `/api/courses`    |   Get all courses    |
| GET    | `/api/courses/:id   |   Get course by ID   | 
| PUT    | `/api/courses/:id`  | Update course by ID  |
| DELETE | `/api/courses/:id`  | Remove course by ID  |




