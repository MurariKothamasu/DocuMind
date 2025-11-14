# DocuMind 🧠📄

This is the main monorepo for DocuMind, an intelligent document summarizer built with React and Node.js. It contains both the frontend application and the backend API in one repository.


## 📂 Repository Structure

This monorepo is organized with a single root folder containing a global `.gitignore` file, a `backend/` folder for the Node.js API, and a `frontend/` folder for the React client application.

## ✨ Core Features

* **Secure JWT Authentication:** Full signup, login, and logout flow using `httpOnly` cookies.
* **Drag-and-Drop File Upload:** A "human-centric" UI for uploading PDF and image files with visual previews.
* **AI Summarization:** Dynamically generates summaries of different lengths (short, medium, large).
* **Key Point Highlighting:** Extracts and displays key points as animated "tags."
* **Polished UI/UX:** A responsive, animated, and professional interface built with Tailwind CSS and Framer Motion.

## 🛠️ Core Tech Stack

| Area | Technology |
| :--- | :--- |
| **Frontend** | React, Vite, React Router, Tailwind CSS, Framer Motion, Axios |
| **Backend** | Node.js, Express, MongoDB, Mongoose, JWT, bcrypt, Multer |
| **AI** | OpenAI (gpt-4o-mini) |
| **File Parsing** | `pdf-parse`,     `tesseract.js`|

## 🚀 Getting Started (Local Development)

To run this project locally, you will need to run **two** separate processes (one for the backend, one for the frontend).

### Prerequisites

* Node.js (v18 or later)
* `npm`
* MongoDB Atlas account (or local MongoDB instance)
* OpenAI API Key

---

### 1. Backend Setup

First, get the backend server running.

1.  Open a terminal and navigate to the `backend` directory:
    ```bash
    cd backend
    ```
2.  Install all required packages:
    ```bash
    npm install
    ```
3.  Create a `.env` file in the `backend/` directory and add your secret keys:
    ```env
    # Your MongoDB connection string
    MONGO_URI=mongodb+srv://...

    # A long, random string for signing tokens
    JWT_SECRET=YOUR_SUPER_SECRET_KEY

    # Your OpenAI API key
    OPENAI_API_KEY=sk-...

    # The URL of your local frontend
    FRONTEND_URL=http://localhost:5173
    ```
4.  Start the backend server:
    ```bash
    npm run dev
    ```
    Your backend is now running, typically at `http://localhost:3000`.

---

### 2. Frontend Setup

Now, set up the frontend in a **new terminal window**.

1.  Open a **new** terminal and navigate to the `frontend` directory:
    ```bash
    cd frontend
    ```
2.  Install all required packages:
    ```bash
    npm install
    ```
3.  Create a `.env` file in the `frontend/` directory and add the backend URL:
    ```env
    # The URL of your local backend server
    VITE_API_URL=http://localhost:3000
    ```
4.  Start the frontend development server:
    ```bash
    npm run dev
    ```
    Your frontend is now running, typically at `http://localhost:5173`.

You can now open `http://localhost:5173` in your browser to use the full application.

## 📦 Deployment

This monorepo is configured to be deployed as two separate services:

* **Frontend (`frontend/`)**: Deployed on **Vercel**. It is configured with `vercel.json` to handle SPA routing.
* **Backend (`backend/`)**: Deployed on **Render** (or Vercel). It is configured with `vercel.json` to install all necessary system dependencies for `pdf-parse` and `canvas`.
