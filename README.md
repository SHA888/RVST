# 🚀 RVST Template

A lightweight, full-stack template for building web applications with Rust, SQLite, Vue.js, and TypeScript. This template is ideal for small to medium projects, offering a serverless SQLite database and a reactive Vue.js frontend with TypeScript.

## 🛠️ Tech Stack

- **Backend**: Rust (Axum for REST APIs, SQLx for database access)
- **Database**: SQLite (file-based, serverless)
- **Frontend**: Vue.js with TypeScript (Vite for fast builds, Tailwind CSS for styling)
- **Tools**: GitHub Actions for CI/CD, optional Docker support

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Rust**: Stable version (install via [rustup](https://rustup.rs/))
  ```bash
  curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
  ```
- **Node.js**: v20 or higher (install via [nvm](https://github.com/nvm-sh/nvm) or [official installer](https://nodejs.org/))
- **SQLite**: v3.40 or higher (install via package manager, e.g., `brew install sqlite` on macOS)
- **Git**: For version control

## 🚀 Setup

### 1. Clone the Repository

```bash
git clone https://github.com/SHA888/RVST.git
cd RVST
```

### 2. Backend Setup

```bash
# Navigate to backend directory
cd backend

# Copy environment file
cp .env.example .env

# Edit .env with your database configuration
# DATABASE_URL=sqlite://./database/rvst.db

# Install SQLx CLI and run migrations
cargo install sqlx-cli
sqlx migrate run

# Start the backend
cargo run
```

The backend will be available at: http://localhost:3000

### 3. Frontend Setup

```bash
# Navigate to frontend directory
cd frontend

# Copy environment file
cp .env.example .env

# Edit .env with your API URL
# VITE_API_URL=http://localhost:3000

# Install dependencies
npm install

# Start the development server
npm run dev
```

The frontend will be available at: http://localhost:5173

### 4. Database Setup

- SQLite will automatically create `rvst.db` in the `database/` folder during migrations
- No additional database server setup is required

## 🐳 Optional Docker Setup

For containerized development:

1. Ensure Docker and Docker Compose are installed
2. Run the full stack:
   ```bash
   docker-compose -f docker/docker-compose.yml up --build
   ```

Access the services:
- Backend: http://localhost:3000
- Frontend: http://localhost:5173

## 🧪 Testing

### Backend Tests

```bash
cd backend
cargo test
```

### Frontend Tests

```bash
cd frontend
npm test
```

## 🚀 Deployment

- **Backend**: Deploy to [Fly.io](https://fly.io/), [Render](https://render.com/), or AWS ECS
- **Frontend**: Deploy to [Vercel](https://vercel.com/), [Netlify](https://www.netlify.com/), or [Cloudflare Pages](https://pages.cloudflare.com/)
- **Database**: SQLite works for small apps, or replace with managed PostgreSQL on [Supabase](https://supabase.com/), [Neon](https://neon.tech/), or AWS RDS

Remember to update environment variables in `.env` files for production URLs.

## 🤝 Contributing

We welcome contributions! Here's how to get started:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Commit your changes: `git commit -m "Add feature"`
5. Push to the branch: `git push origin feature-name`
6. Open a pull request

Found a bug or have a suggestion? Please [open an issue](https://github.com/SHA888/RVST/issues).

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
