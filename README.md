# **Capstone Project: Car Dealership Management System**

This project is a fully functional web application that allows users to manage car dealerships, review dealers, and handle user authentication. The app integrates a Django-based backend, a React-based frontend, and a MongoDB database accessed via Express APIs.

---

## **Features**
- **Dynamic Pages**: Includes static pages like `About Us` and `Contact Us` and dynamic pages for dealership listings, reviews, and user interactions.
- **User Authentication**: Login, logout, and registration functionalities for users.
- **Admin Access**: Superusers can manage car models, car makes, and dealerships through the Django admin panel.
- **Dealer Reviews**: Users can view and post reviews for dealers.
- **Frontend Integration**: React components for a clean, user-friendly interface.
- **Docker Support**: Containerized services for ease of deployment.
- **Continuous Integration (CI)**: GitHub Actions to automatically lint Python and JavaScript code.

**Note:** The sentiment analysis feature is currently **non-functional** because the microservice provided during the course has been shut down. This may cause "loading reviews" to appear indefinitely.

---

## **Setup Instructions**

Below are the steps to set up and run the application locally:

### **Part 1: Frontend Setup**
1. Navigate to the frontend directory:
   ```bash
   cd /home/project/Car-Dealership-Management-System/server/frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Build the frontend:
   ```bash
   npm run build
   ```

### **Part 2: Database Setup**
1. Navigate to the database directory:
   ```bash
   cd /home/project/Car-Dealership-Management-System/server/database
   ```
2. Build the Docker container for the database:
   ```bash
   docker build . -t nodeapp
   ```
3. Start the database service using Docker Compose:
   ```bash
   docker-compose up
   ```
   > **Note:** Ensure Docker is installed and running.

### **Part 3: Backend Setup**
1. Open a new terminal and navigate to the server directory:
   ```bash
   cd /home/project/Car-Dealership-Management-System/server
   ```
2. Set up a virtual environment:
   ```bash
   pip install virtualenv
   virtualenv djangoenv
   source djangoenv/bin/activate
   ```
3. Install Python dependencies:
   ```bash
   python3 -m pip install -U -r requirements.txt
   ```
4. Apply migrations:
   ```bash
   python3 manage.py makemigrations
   python3 manage.py migrate --run-syncdb
   ```
5. Run the Django development server:
   ```bash
   python3 manage.py runserver
   ```

### **Accessing the Application**
- **Local URL:** [http://localhost:8000](http://localhost:8000)
- **Django Admin Panel:** [http://localhost:8000/admin](http://localhost:8000/admin)

---

## **Creating a Superuser**
To manage database entries directly via the admin panel:

1. Stop the server if it's running.
2. Run:
   ```bash
   python3 manage.py createsuperuser
   ```
3. Follow the prompts to set up username, email, and password.
4. Restart the server:
   ```bash
   python3 manage.py runserver
   ```
5. Navigate to [http://localhost:8000/admin](http://localhost:8000/admin) and log in using your superuser credentials.

---

## **File Structure**

- **Frontend** (`/server/frontend`):
  - React components for the user interface.
- **Backend** (`/server/djangoapp`):
  - Django project for handling business logic and database interactions.
- **Database** (`/server/database`):
  - MongoDB setup and Express APIs.

---

## **Important Notes**

1. **Sentiment Analysis:**  
   The microservice for sentiment analysis is **no longer available**. Reviews may show "loading reviews" indefinitely due to the missing service.

2. **Customization:**  
   Feel free to modify the application, including database entries, frontend UI, and backend logic. The Django admin panel or direct code changes allow you to customize the app as needed.

---

## Acknowledgements

- This application was developed as the final capstone project for the "IBM Full Stack Software Developer Professional Certificate" offered by **Coursera**.
  You can find more details about the certification [here](https://www.coursera.org/professional-certificates/ibm-full-stack-cloud-developer).
- Special thanks to the **IBM Developer Skills Network** for providing the foundational project structure and guidance.
