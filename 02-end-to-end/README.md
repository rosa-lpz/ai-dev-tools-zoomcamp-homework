# End-to-End Application Development

In this homework, we'll build an end-to-end application with AI.

You can use any tool you want: ChatGPT, Claude, GitHub Copilot, Codex, Cursor, Antigravity, etc.

With chat-based applications you will need to copy code back-and-forth, so we recommend that you use an AI assistant in your IDE with agent mode.

We will implement a platform for online coding interviews.

The app should be able to do the following:

- Create a link and share it with candidates
- Allow everyone who connects to edit code in the code panel
- Show real-time updates to all connected users
- Support syntax highlighting for multiple languages
- Execute code safely in the browser

You can choose any technologies you want. For example:

- Frontend: React + Vite
- Backend: Express.js

We recommend using JavaScript for frontend, because with other technologies, some of the homework requirements may be difficult to implement.

But you can experiment with alternatives, such as Streamlit.

You don't need to know these technologies for doing this homework.

# Application repository

* https://github.com/rosa-lpz/django-react-coding-tests-platform


## Question 1: Initial Implementation

Ask AI to implement both frontend and backend - in one prompt.

Note: you can also follow the same path as in the videos and make it in 3 steps:

1. Frontend
2. OpenAPI specs
3. Backend

What's the initial prompt you gave to AI to start the implementation?

Copy and paste it in the homework form.

```
Crate the frontend code using react+vite with javascript for a coding tests plataform

Frontend:

User authentication
Dashboard
- candidate dashboard
- Coding enviroment
- Code editor (e.g., Monaco Editor or Ace Editor) to write code in multiple languages.
- Auto-save functionality (e.g., save code every 30 seconds).
- Output display panel for runtime results or errors.
- Timer to track the candidate’s time while solving problems.
- Optional features: Syntax highlighting, error highlighting, input/output formatting.

For the backend create templates django

Backend:

- "users" model
- "codetests" models
	- test
	- testcase
```



## Question 2: Integration Tests

Maybe at this point your application will already function. Maybe not. But it's always a good idea to cover it with tests.

We usually do it even before trying to run the application because it helps to resurface all the problems with implementation.

Ask AI to write integration tests that check that the interaction between client and server works.

Also it's a good idea to ask it to start creating a `README.md` file with all the commands for running and testing your application.

What's the terminal command you use for executing tests?

```
 python manage.py test
```



## Question 3: Running Both Client and Server

Now let's make it possible to run both client and server at the same time. Use `concurrently` for that.

What's the command you have in `package.json` for `npm dev` for running both?



### **Method 1: One-Command Startup (Easiest)** ⭐

```bash
./start-servers.sh
```

**Features:**

- ✅ Starts both Django and React servers automatically
- ✅ Colored output showing which server each log comes from
- ✅ Nice formatted display with URLs and credentials
- ✅ Single `Ctrl+C` stops both servers gracefully
- ✅ Auto-creates logs directory

### **Method 2: Using Makefile**

```bash
make dev          # Start both servers
make run-backend  # Backend only
make run-frontend # Frontend only
make help         # See all commands
```

### **Method 3: Separate Terminals**

**Terminal 1 (Backend):**

```bash
cd backend
../codingtestsvenv/bin/python manage.py runserver
```

**Terminal 2 (Frontend):**

```bash
cd frontend
npm run dev
```

### **Scripts Created:**

1. **[start-servers.sh](vscode-file://vscode-app/usr/share/code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)** - Beautiful startup script with formatted output
2. **[start-dev.sh](vscode-file://vscode-app/usr/share/code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)** - Simpler version that logs to files
3. **[stop-servers.sh](vscode-file://vscode-app/usr/share/code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)** - Stops both servers by killing processes on ports 8000 and 5173
4. **[Makefile](vscode-file://vscode-app/usr/share/code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)** - Convenient make commands for all operations
5. **[RUNNING.md](vscode-file://vscode-app/usr/share/code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)** - Complete guide with all methods including tmux and screen



## Question 4: Syntax Highlighting

Let's now add support for syntax highlighting for JavaScript and Python.

Which library did AI use for it?

```javascript
import Editor from '@monaco-editor/react';
```



```javascript

<Editor
  height="calc(100% - 200px)"
  language={language}  // ← This prop tells Monaco which syntax to highlight
  value={code}
  onChange={(value) => setCode(value || '')}
  theme="vs-dark"      // ← Dark theme with syntax colors
  options={{
    minimap: { enabled: false },
    fontSize: 14,
    lineNumbers: 'on',
    scrollBeyondLastLine: false,
    automaticLayout: true,
    tabSize: 4,
    readOnly: !isTestActive,
  }}
/>
```

**Key Features Provided by Monaco:**

- ✅ Syntax highlighting (colors for keywords, strings, comments, etc.)
- ✅ Auto-completion (IntelliSense)
- ✅ Error detection
- ✅ Bracket matching
- ✅ Code folding
- ✅ Multiple themes (vs-dark, vs-light, hc-black)
- ✅ Multi-cursor editing
- ✅ Find and replace



## Question 5: Code Execution

Now let's add code execution.

For security reasons, we don't want to execute code directly on the server. Instead, let's use WASM to execute the code only in the browser.

Which library did AI use for compiling Python to WASM?



## Question 6: Containerization

Now let's containerize our application. Ask AI to help you create a Dockerfile for the application. Put both backend and frontend in one container.

What's the base image you used for your Dockerfile?



## Question 7: Deployment

Now let's deploy it. Choose a service to deploy your application.

Which service did you use for deployment?



## Homework URL

Commit your code to GitHub. You can create a repository for this course. Within the repository, create a folder, e.g. "02-coding-interview", where you put the code.

Use the link to this folder in the homework submission form.

Don't forget to commit your code at every step. You can create an `AGENTS.md` file with the instructions for AI to help you with git commands.



## Tip

You can copy-paste the homework description into the AI system of your choice. But make sure you understand (and follow) all the steps in the response.


## Submission

Submit your homework here: https://courses.datatalks.club/ai-dev-tools-2025/homework/hw2


## Learning in Public

We encourage everyone to share what they learned. 

Don't worry about being perfect. Everyone starts somewhere, and people love following genuine learning journeys!

### Recording a Demo Video

Consider recording a short demo video of your application in action! This makes your post much more engaging and helps others see what you've built.

You can use:
- Screen recording tools like OBS Studio, QuickTime, or Windows Game Bar
- Loom for quick and shareable recording
- Snapping Tool on Windowns
  

Keep it short (30-90 seconds) and show:
- Creating a coding session link
- Multiple users editing code simultaneously
- Real-time updates across browsers
- Code execution in action

Upload your video to LinkedIn, Twitter/X, or YouTube and share the link!

### Example post for LinkedIn:

```
🚀 Week 2 of AI Dev Tools Zoomcamp by @DataTalksClub complete!

Just built a real-time collaborative coding interview platform using AI assistants!

Today I learned how to:

- ✅ Build full-stack applications with AI (frontend + backend)
- ✅ Implement real-time collaboration with WebSockets
- ✅ Add syntax highlighting for multiple languages
- ✅ Execute code safely in the browser with WASM
- ✅ Containerize and deploy the application

Here's my repo: <LINK>
Demo video: <VIDEO_LINK>

Following along with this amazing course - who else is building with AI?

You can sign up here: https://github.com/DataTalksClub/ai-dev-tools-zoomcamp/
```

### Example post for Twitter/X:


```
🤖 Built a collaborative coding platform with AI!

🔗 Shareable links
⚡ Real-time collaboration
🎨 Syntax highlighting
🚀 Browser code execution

My repo: <LINK>
Demo: <VIDEO_LINK>

Join me: https://github.com/DataTalksClub/ai-dev-tools-zoomcamp/
```