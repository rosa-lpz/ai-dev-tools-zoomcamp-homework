# Frontend

Implemente the frontend using react+vite with javascript for a coding tests plataform

Frontend:

* User authentication
* Dashboard
  * candidate dashboard
* Coding enviroment
  * Code editor (e.g., Monaco Editor or Ace Editor) to write code in multiple languages.
  * Auto-save functionality (e.g., save code every 30 seconds).
  * Output display panel for runtime results or errors.
  * Timer to track the candidate’s time while solving problems.
  * Optional features: Syntax highlighting, error highlighting, input/output formatting.

Create templates for backend (django)

* "users" model

* "codetests" models

  * test
  * testcase

  



###  **User Authentication & Authorization**

- **Frontend (React)**:
  - Sign Up/Sign In page with secure authentication (OAuth, JWT, etc.).
  - User roles (e.g., Admin, Interviewer, Candidate).
  - Password reset functionality.
- **Backend (Django)**:
  - JWT-based authentication or OAuth2 for secure login.
  - Role-based access control (e.g., admin, interviewer, candidate).
  - Token expiry and refresh token management.



### Dashboard (for Candidates and Interviewers)

- **Frontend (React)**:
  - **Candidate Dashboard**: View current tests, progress, and past results.
  - **Interviewer Dashboard**: Access active interviews, assign tests, and review submissions.
  - **Admin Dashboard**: Manage users, tests, and view overall system statistics (e.g., number of candidates, test completion rates).
- **Backend (Django)**:
  - Manage test assignments for interviewers and candidates.
  - Store and retrieve user data such as past test results, time limits, and scores.
  - Logging and statistics of test usage.

### **Coding Environment (Live Coding Interface)**

- **Frontend (React)**:
  - Code editor (e.g., Monaco Editor or Ace Editor) to write code in multiple languages.
  - Auto-save functionality (e.g., save code every 30 seconds).
  - Output display panel for runtime results or errors.
  - Timer to track the candidate’s time while solving problems.
  - Optional features: Syntax highlighting, error highlighting, input/output formatting.
- **Backend (Django)**:
  - Securely run code in isolated environments (using Docker or cloud-based services like AWS Lambda, Google Cloud Functions).
  - Execute submitted code in the selected language and provide results back to the candidate.
  - Manage code execution timeouts and resource limits (CPU, memory).
  - Handle multiple languages and versioning (Python 3, Node.js, Java, etc.).

### **Test Execution & Evaluation**

- **Frontend (React)**:
  - Display results in real-time (e.g., success, errors, and runtime output).
  - Provide an option for candidates to submit code once they’re done.
- **Backend (Django)**:
  - **Test Runner**: Use a sandboxed environment (e.g., Docker) to run the candidate's code with the given input.
  - Evaluation based on **expected output**. Compare the candidate’s code output with the predefined expected results.
  - Handle timeouts and infinite loops (kill processes after a predefined time or resource usage limit).
  - Save the execution logs for debugging and scoring.

------

### **Result Calculation and Feedback**

- **Frontend (React)**:
  - Show a summary of results once the test is submitted (pass/fail, points scored, and time taken).
  - Provide detailed feedback on performance, such as which test cases passed, failed, and how the code could be optimized.
- **Backend (Django)**:
  - Calculate and store results: Track whether the candidate’s solution passed all test cases and assign a score.
  - Generate a report for the interviewer: Display test case results, code performance metrics (time complexity, space complexity), and areas for improvement.
  - Support partial scoring in case some test cases pass.

------

### 