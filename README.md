# ShopStream

ShopStream is a full-stack e-commerce showcase where shoppers browse products, manage a cart, and admins curate the product catalog.

## Stack

- React + Vite frontend
- Node.js + Express backend
- MongoDB + Mongoose
- JWT authentication
- Cloudinary image uploads
- Netlify-ready frontend and Render-ready backend

## Quick Start

```bash
npm run install:all
cp server/.env.example server/.env
cp client/.env.example client/.env
npm run seed
npm run dev
```

Frontend: http://localhost:5173  
Backend: http://localhost:5000

## Demo Accounts

The seed script creates:

- Admin: `admin@shopstream.dev` / `Admin123!`
- Customer: `customer@shopstream.dev` / `Customer123!`

## Environment

Backend values live in `server/.env`.

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/shopstream
JWT_SECRET=replace-with-a-long-random-secret
CLIENT_ORIGIN=http://localhost:5173
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
```

Frontend values live in `client/.env`.

```env
VITE_API_URL=http://localhost:5000/api
```

Cloudinary is optional for local catalog work. If credentials are missing, the API accepts `imageUrl` fields directly.

## API Overview

- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/auth/me`
- `GET /api/products`
- `GET /api/products/:id`
- `POST /api/products` admin only, multipart or JSON
- `PUT /api/products/:id` admin only, multipart or JSON
- `DELETE /api/products/:id` admin only
- `GET /api/cart`
- `POST /api/cart/items`
- `PATCH /api/cart/items/:productId`
- `DELETE /api/cart/items/:productId`
- `DELETE /api/cart`

## Deployment Notes

Render can run the backend from `server` with:

```bash
npm install
npm start
```

Netlify can build the frontend from `client` with:

```bash
npm install
npm run build
```

Set `VITE_API_URL` on Netlify to your Render API URL ending in `/api`.
