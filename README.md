# Next-AI

## 一、Related knowledge

#### 1.1 Prompt Engineering

https://platform.openai.com/docs/guides/prompt-engineering

Prompt engineering is the process of designing and optimizing prompts used in natural language processing (NLP) models, such as ChatGPT, chatbots, or virtual assistants. This involves crafting prompts that are clear, concise, and effective in eliciting the desired response.
(Aka prompt engineering is like making an effective fishing lure — just as a well-designed lure is more likely to catch the fish you want, a well-crafted prompt is more likely to elicit the desired response.)

#### 1.2 Langchain

https://www.langchain.com/

LangChain is a framework for developing applications powered by language models. It enables applications that are:

- **Data-aware**: connect a language model to other sources of data.
- **Agentic**: allow a language model to interact with its environment.

![image-20240915073755347](/Users/zijunhuang/Library/Application Support/typora-user-images/image-20240915073755347.png)

![image-20240915080126800](/Users/zijunhuang/Library/Application Support/typora-user-images/image-20240915080126800.png)

### 1.3 Node.js and Express.js

Node.js - Node.js is an open-source, cross-platform JavaScript runtime environment. 

https://nodejs.org/en

Express.js - web framework for Node.js 

https://expressjs.com/



## 二、Project Introduction

![image-20240915081222373](/Users/zijunhuang/Library/Application Support/typora-user-images/image-20240915081222373.png)

**Demo Video**

youtobe：

### 2.1 features

* users can upload a PDF

* users can ask questions in the PDF

* users will receive answers on questions asked

* users can ask questions about the PDF using speech

* users can hear the answers in speech

### 2.2 Project Architecture

**High level Project Diagram**

![image-20240915082859492](https://github.com/Huangzjun/img/blob/main/image-20240915073755347.png)

This project is a full-stack web application built using the following technologies:

**Frontend:**

- **React**: The user interface is built using React, a popular JavaScript library for building fast and dynamic web applications. It enables a responsive and interactive experience for users.
- **Ant Design (AntD)**: A React-based UI library that provides pre-built components for designing user interfaces with ease and consistency.
- **Axios**: Used to handle HTTP requests between the frontend and the backend, particularly for sending queries and receiving responses.
- **React Speech Recognition & Speak-TTS**: Libraries for handling speech input (speech-to-text) and output (text-to-speech), allowing users to interact with the application via voice commands.

**Backend:**

- **Node.js with Express**: The backend server is built using Express, a lightweight and fast framework for building web applications in Node.js. It handles file uploads and communication with the OpenAI API.
- **Multer**: Middleware used for handling multipart file uploads, specifically for uploading PDFs to the server.
- **OpenAI API**: The backend integrates with OpenAI to process user queries and provide intelligent responses based on the content of the uploaded PDF.

**Architecture:**

- Client-Server Architecture
  - The **frontend** communicates with the **backend** via RESTful API requests.
  - The **backend** handles file uploads (PDFs) and sends queries to OpenAI for processing.
  - The **OpenAI API** generates responses based on the content of the PDF and the user's queries.
- **Concurrent Execution**: Using the `concurrently` package, both the frontend (React) and backend (Express) can be run simultaneously during development.

#### 2.2.1 Project Hierarchy

```shell
.
├── README.md
├── node_modules # Directory containing all installed npm dependencies
├── package-lock.json # Dependency lock file
├── package.json # Project setup and dependencies
├── public # Directory for public assets
├── server # Backend code
└── src # Front-end code
```

##### ➀ backend - server

```shell
.
├── chat.js # PDF processing and OpenAI query handling
├── package-lock.json # Dependency lock file
├── package.json # Project setup and dependencies
├── server.js # Express server for uploads and chat API
└── uploads # Directory for uploaded filess
    ├── hbs-lean-startup.pdf
    └── lab2 reading.pdf
```

##### ➁ frontend - src

```shell
.
├── App.css                 # Styles for the App component
├── App.js                  # Main React component for the app
├── App.test.js             # Test cases for the App component
├── components              # Directory for React components
│   ├── ChatComponent.js    # Component handling chat interactions
│   ├── PdfUploader.js      # Component for uploading PDF files
│   └── RenderQA.js         # Component for displaying questions and answers
├── index.css               # Global styles for the application
├── index.js                # Entry point of the React application
├── logo.svg                # Logo used in the app
├── reportWebVitals.js      # For measuring app performance (optional)
└── setupTests.js           # Setup file for testing with Jest
```

### 2.3 Build Instructions

Follow these steps to set up and run the project:

#### Step 1: Clone the repository from GitHub

Use the following command to clone the project to your local machine:

```shell
git clone https://github.com/your-username/your-repository.git
cd your-repository
```

#### Step 2: Create a `.env` file in the `server` folder

Navigate to the `server` directory and create a `.env` file. Add your OpenAI API keys (which you can obtain from OpenAI's website) to this file:

```shell
cd server
touch .env
```

Add the following lines to your `.env` file:

```shell
REACT_APP_OPENAI_API_KEY=your-openai-api-key
```

Replace `your-openai-api-key` with the actual key you received from OpenAI.

#### Step 3: Install dependencies and run the project

You will need to install the dependencies for both the frontend and the backend. Use the following commands:

1. **Install dependencies for the main project (frontend):**

```shell
npm install
```

2. **Install dependencies for the backend (server):**

```shell
cd server
npm install
```

3. **Run the frontend and backend concurrently:**

In the root directory of your project, run the following command to start both the frontend and backend simultaneously:

```shell
npm run dev
```

This will start both the React frontend and the Express backend. The project should now be running, and you can access the frontend by visiting `http://localhost:3000`.

#### Optional Step: Build for production

To build the project for production, use the following command:

```shell
npm run build
```