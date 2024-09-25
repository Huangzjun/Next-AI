# Next-AI : Web Based Q&A AI Agent for PDF Document Queries

## Project Introduction

**Next-AI** is a full-stack web application that allows users to upload PDF documents and ask questions about their content, receiving intelligent answers in real-time. The system supports both text-based and voice-based queries, offering spoken responses as well. Built with **React** on the frontend and **Node.js with Express** on the backend, it integrates **OpenAI API** for advanced natural language processing. The application delivers an interactive, speech-enabled experience for seamless document querying.

![image-20240915081222373](https://github.com/Huangzjun/Next-AI/blob/main/img/image-20240915081222373.png)

Demo Video： https://youtu.be/9QPuPGjVPD0

## features

* users can upload a PDF

* users can ask questions in the PDF

* users will receive answers on questions asked

* users can ask questions about the PDF using speech

* users can hear the answers in speech

## Build Instructions

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