# Spotify Microservices Project

A Spotify-like music app built with a microservices architecture (React frontend + 3 Node.js backend services).

## 🧭 Project Structure

- `frontend/` – React + TypeScript + Vite client
- `user service/` – Express + TypeScript + MongoDB auth service
- `song service/` – Express + TypeScript + PostgreSQL + Redis read service
- `admin service/` – Express + TypeScript + PostgreSQL + Cloudinary + Redis admin service

## 👤 Author

**Dhruv Chouksey**

## 🚀 Features

- User registration/login with JWT
- Role-based admin protected routes
- Add/delete albums and songs
- Cloudinary image upload for album thumbnails
- Redis caching for songs/albums
- Separate user, song, and admin microservices
- React client with routing and protected pages

## 🔧 Setup

1. Clone repo:
   ```bash
   git clone <repo-url>
   cd "Microservices-project"
   ```

2. Install dependencies in each folder:
   ```bash
   cd user service && npm install
   cd ../song service && npm install
   cd ../admin service && npm install
   cd ../frontend && npm install
   ```

3. Add `.env` files:

### `user service/.env`
```env
MONGO_URI=your_mongo_connection_string
JWT_SEC=your_jwt_secret
PORT=5000
```

### `song service/.env`
```env
DB_URL=postgresql://...
Redis_Password=your_redis_password
PORT=5001
```

### `admin service/.env`
```env
DB_URL=postgresql://...
Redis_Password=your_redis_password
Cloud_Name=your_cloud_name
Cloud_Api_Key=your_cloud_api_key
Cloud_Api_Secret=your_cloud_api_secret
User_URL=http://localhost:5000
PORT=3000
```

4. Start services in separate terminals:

```bash
cd user service && npm run dev
cd song service && npm run dev
cd admin service && npm run dev
cd frontend && npm run dev
```

5. Open frontend: `http://localhost:5173` (or Vite printed URL).

## 📁 API Endpoints

### User service
- `POST /api/v1/user/register`
- `POST /api/v1/user/login`
- `GET /api/v1/user/me`

### Song service
- `GET /api/v1/song/all`
- `GET /api/v1/album/all`

### Admin service
- `POST /api/v1/album/new` (admin only)
- `POST /api/v1/song/new` (admin only)
- `DELETE /api/v1/album/:id` (admin only)
- `DELETE /api/v1/song/:id` (admin only)


