# Typing Test Application

## Overview

This is a **Typing Test** project developed using Angular for the frontend, ASP.NET Core Web API for the backend, and SQL Server for the database. The application allows users to test their typing speed and accuracy, track their progress, and manage test data effectively.

---

## Features

- **Typing Test Functionality**: Users can practice typing and get real-time feedback on speed (words per minute) and accuracy.
- **User Management**: API handles user data, session history, and typing scores.
- **Score Tracking**: Saves typing test results into a SQL Server database.
- **Modern UI**: Built with Angular to provide an intuitive and responsive user interface.
- **RESTful API**: ASP.NET Core Web API exposes secure endpoints for CRUD operations.
- **Database Storage**: SQL Server for storing typing test scores and user data.

---

## Technology Stack

### Frontend
- **Framework**: Angular (v14+)
- **Tools**: TypeScript, RxJS, Angular CLI
- **UI Components**: HTML, SCSS, Bootstrap (or any other CSS framework)

### Backend
- **Framework**: ASP.NET Core Web API
- **Language**: C#
- **Database**: SQL Server
- **Tools**: Entity Framework Core for data access

### Development Tools
- Visual Studio Code / Visual Studio
- SQL Server Management Studio (SSMS)
- Postman for API testing
- Git for version control

---

## Installation

### 1. **Clone the Repository**
```bash
git clone https://github.com/<YourUsername>/Typing-Test.git
cd Typing-Test
```

### 2. **Setup Backend (ASP.NET Core Web API)**

1. Open the backend project in **Visual Studio**.
2. Update the **`appsettings.json`** file with your SQL Server connection string:
   ```json
   "ConnectionStrings": {
       "DefaultConnection": "Server=YOUR_SERVER_NAME;Database=TypingTestDB;Trusted_Connection=True;"
   }
   ```
3. Run database migrations:
   ```bash
   dotnet ef database update
   ```
4. Start the API server:
   ```bash
   dotnet run
   ```
   The backend will run at `https://localhost:5001` or `http://localhost:5000`.

### 3. **Setup Frontend (Angular Application)**

1. Navigate to the frontend folder:
   ```bash
   cd Frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Update the API URL in the `environment.ts` file:
   ```typescript
   export const environment = {
     production: false,
     apiUrl: 'https://localhost:5001/api' // Adjust to your API URL
   };
   ```
4. Start the Angular development server:
   ```bash
   ng serve
   ```
   The frontend will run at `http://localhost:4200`.

---

## Usage

1. Open the application in your browser at `http://localhost:4200`.
2. Start the typing test by clicking **Start Test**.
3. Type the provided text, and the app will calculate your:
   - Words Per Minute (WPM)
   - Accuracy percentage
4. Results will be saved to the database and can be viewed later.

---

## API Endpoints

### Base URL: `/api/`

| Endpoint               | Method | Description                       |
|------------------------|--------|-----------------------------------|
| `/users`               | GET    | Get all users                    |
| `/users/{id}`          | GET    | Get a specific user              |
| `/scores`              | GET    | Get all typing test scores       |
| `/scores/{id}`         | GET    | Get scores for a specific user   |
| `/scores`              | POST   | Save a new typing test score     |

---

## Database Schema

### **Tables**:
1. **Users**
   - `Id` (PK)
   - `Name`
   - `Email`
2. **Scores**
   - `Id` (PK)
   - `UserId` (FK)
   - `WordsPerMinute`
   - `Accuracy`
   - `CreatedAt`

---

## Screenshots

### Home Page
![Home Page](screenshots/home.png)

### Typing Test Page
![Typing Test Page](screenshots/typing-test.png)

---

## Contribution

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add new feature"
   ```
4. Push to your branch:
   ```bash
   git push origin feature/your-feature
   ```
5. Open a Pull Request.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contact

For any questions or feedback, reach out to:

**Mukesh Kumar Verma**  

---

Let me know if you'd like more enhancements or edits! 🚀
