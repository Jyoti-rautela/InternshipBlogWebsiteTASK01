# MERN-Blog – Build Process & Run Steps

## 1. Prerequisites
- Node.js ≥ 18  
- MongoDB running locally (default URI: `mongodb://localhost:27017/mern_blog`)  
- Git (optional)

---

## 2. Project Scaffolding
mkdir mern-blog && cd mern-blog


### 2.1 Backend (Express + Mongoose)
mkdir backend && cd backend
npm init -y
npm i express mongoose cors morgan dotenv
# dev-only
npm i -D nodemon


Add scripts to `backend/package.json`:
```json
"scripts": {
  "dev": "nodemon server.js"
}
```

Create files:
- `backend/server.js` – Express server, Mongo connection  
- `backend/models/Post.js` – Mongoose schema  
- `backend/routes/posts.js` – REST endpoints  
- `backend/.env` – `PORT=5000` & `MONGODB_URI=...`

### 2.2 Frontend (React + Vite)
cd ..

npm create vite@latest frontend -- --template react

cd frontend

npm i

npm i react-router-dom axios bootstrap


Create folders & files:
- `src/pages/` – Home, CreatePost, EditPost, ViewPost  
- `src/components/NavBar.jsx`  
- `src/api.js` – Axios instance pointing to `http://localhost:5000/api`



## 3. Run Locally

### 3.1 Start Backend
cd backend
npm install
npm run dev
# Server listens on http://localhost:5000


### 3.2 Start Frontend
cd frontend
npm install
npm run dev
# Vite dev server on http://localhost:5173


## 4. API Endpoints
| Method | Endpoint         | Purpose         |
|--------|------------------|-----------------|
| GET    | /api/posts       | list posts      |
| GET    | /api/posts/:id   | single post     |
| POST   | /api/posts       | create post     |
| PUT    | /api/posts/:id   | update post     |
| DELETE | /api/posts/:id   | delete post     |

Import `backend/postman_collection.json` into Postman for ready-made requests.



## 5. Tech Stack
- **Database** – MongoDB + Mongoose  
- **Backend** – Node.js, Express, Morgan, CORS  
- **Frontend** – React 18, React-Router, Axios, Bootstrap 5  
- **Tooling** – Vite, Nodemon, dotenv
