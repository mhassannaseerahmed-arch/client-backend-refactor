<h1 align="center">⚙️ Client Management Backend</h1>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,0f172a,50,7c3aed,100,a855f7&height=220&section=header&text=Enterprise%20API&fontSize=60&fontColor=ffffff&fontAlignY=70" width="100%" />
</p>

<p align="center">
  <a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=20&pause=1000&color=a855f7&center=true&vCenter=true&width=600&lines=Scalable+Express+API;TypeScript+Backend;MongoDB+Integration;Enterprise+Ready" alt="Typing SVG" /></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" />
  <img src="https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white" />
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" />
</p>

---

## 🚀 What is Client Management Backend?

**Client Management Backend** is a **robust, production-ready REST API** built with Express, TypeScript, and MongoDB. It powers the Client Management SaaS platform with comprehensive APIs for clients, projects, tasks, and employees.

### Key Features
- 🔐 JWT authentication with refresh tokens
- 🏢 Complete client lifecycle management
- 🏗️ Project tracking with budgets & timelines
- 📋 Task management with assignments
- 👥 Employee directory & role management
- 📊 Analytics & reporting
- 🔄 Full CRUD operations
- 🛡️ Production-grade security

---

## ✨ Core Features

| Feature | Description | Benefit |
| :--- | :--- | :--- |
| 🔐 **Authentication** | JWT + Refresh tokens | Secure, scalable auth |
| 👥 **Client Management** | Full CRUD operations | Manage all client data |
| 🏗️ **Projects** | Budget & timeline tracking | Stay organized |
| 📋 **Tasks** | Assignment & status tracking | Clear ownership |
| 👨‍💼 **Employees** | Team management | HR tracking |
| 📊 **Analytics** | Real-time metrics | Data-driven decisions |
| 🔄 **Relationships** | Complex data linking | Enterprise-grade structure |
| 📧 **Notifications** | Email alerts (ready) | Keep teams informed |

---

## 🏗️ System Architecture

```mermaid
graph TD
    Client((Frontend App))
    Auth[Auth Middleware]
    Routes[API Routes]
    Controllers[Controllers]
    Services[Services]
    Models[Mongoose Models]
    DB[(MongoDB)]
    
    Client -->|HTTP| Auth
    Auth -->|Validated| Routes
    Routes -->|Handler| Controllers
    Controllers -->|Business Logic| Services
    Services -->|Query| Models
    Models -->|Persist| DB
```

---

## 🛠️ Tech Stack

- **Runtime**: Node.js v18+
- **Framework**: Express.js v5
- **Language**: TypeScript
- **Database**: MongoDB + Mongoose
- **Authentication**: JWT (jsonwebtoken)
- **Password**: bcryptjs
- **Validation**: Joi, express-validator
- **Security**: helmet, cors, rate-limit
- **Development**: tsx, nodemon

---

## 📂 Project Structure

```
backend/
├── src/
│   ├── config/
│   │   ├── database.ts       # MongoDB connection
│   │   ├── constants.ts      # App constants
│   │   └── environment.ts    # Env validation
│   │
│   ├── middleware/
│   │   ├── auth.ts           # JWT verification
│   │   ├── errorHandler.ts   # Error handling
│   │   ├── validation.ts     # Request validation
│   │   └── logging.ts        # Request logging
│   │
│   ├── models/
│   │   ├── User.ts           # User schema
│   │   ├── Client.ts         # Client schema
│   │   ├── Project.ts        # Project schema
│   │   ├── Task.ts           # Task schema
│   │   └── Employee.ts       # Employee schema
│   │
│   ├── controllers/
│   │   ├── authController.ts
│   │   ├── clientController.ts
│   │   ├── projectController.ts
│   │   ├── taskController.ts
│   │   └── employeeController.ts
│   │
│   ├── routes/
│   │   ├── auth.ts
│   │   ├── clients.ts
│   │   ├── projects.ts
│   │   ├── tasks.ts
│   │   └── employees.ts
│   │
│   ├── services/
│   │   ├── authService.ts
│   │   ├── clientService.ts
│   │   ├── projectService.ts
│   │   ├── taskService.ts
│   │   └── analyticsService.ts
│   │
│   ├── types/
│   │   ├── index.ts
│   │   ├── auth.ts
│   │   ├── models.ts
│   │   └── request.ts
│   │
│   ├── utils/
│   │   ├── jwt.ts
│   │   ├── validators.ts
│   │   ├── logger.ts
│   │   └── errorHandler.ts
│   │
│   ├── app.ts                # Express app setup
│   └── index.ts              # Server entry point
│
├── .env.example
├── tsconfig.json
├── package.json
└── README.md
```

---

## 🚀 Quick Start

### Prerequisites
- Node.js v18+
- MongoDB (Atlas)
- npm or yarn

### Installation

```bash
git clone https://github.com/mhassannaseerahmed-arch/client-management-saas-backend.git
cd client-management-saas-backend

npm install

cp .env.example .env
```

### Configure Environment

```env
# Server
PORT=4000
NODE_ENV=development

# Database
MONGODB_URI=mongodb+srv://user:password@cluster.mongodb.net/clientmgmt

# JWT
JWT_SECRET=your_super_secret_key_make_it_strong
JWT_EXPIRE=7d
JWT_REFRESH_SECRET=your_refresh_secret_key
JWT_REFRESH_EXPIRE=30d

# Email (optional)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASSWORD=your-app-password

# CORS
CORS_ORIGIN=http://localhost:3000

# Logging
LOG_LEVEL=debug
```

### Run Development Server

```bash
npm run dev
```

Server runs on `http://localhost:4000`

---

## 📡 API Endpoints

### Authentication
```
POST   /auth/register              # Register user
POST   /auth/login                 # Login
POST   /auth/logout                # Logout
POST   /auth/refresh               # Refresh token
GET    /auth/me                    # Get current user
```

### Clients (CRUD)
```
GET    /api/clients                # List all clients
POST   /api/clients                # Create client
GET    /api/clients/:id            # Get client details
PUT    /api/clients/:id            # Update client
DELETE /api/clients/:id            # Delete client
GET    /api/clients/:id/projects   # Get client projects
GET    /api/clients/search?q=term  # Search clients
```

### Projects (CRUD)
```
GET    /api/projects               # List projects
POST   /api/projects               # Create project
GET    /api/projects/:id           # Get project
PUT    /api/projects/:id           # Update project
DELETE /api/projects/:id           # Delete project
GET    /api/projects/:id/tasks     # Get project tasks
GET    /api/projects/:id/budget    # Budget analysis
```

### Tasks (CRUD + Status)
```
GET    /api/tasks                  # List tasks
POST   /api/tasks                  # Create task
GET    /api/tasks/:id              # Get task
PUT    /api/tasks/:id              # Update task
DELETE /api/tasks/:id              # Delete task
PATCH  /api/tasks/:id/status       # Update status
GET    /api/tasks/assigned/me      # My tasks
```

### Employees (CRUD)
```
GET    /api/employees              # List employees
POST   /api/employees              # Add employee
GET    /api/employees/:id          # Get employee
PUT    /api/employees/:id          # Update employee
DELETE /api/employees/:id          # Remove employee
GET    /api/employees/:id/tasks    # Employee tasks
```

### Analytics
```
GET    /api/analytics/dashboard    # Dashboard stats
GET    /api/analytics/clients      # Client metrics
GET    /api/analytics/projects     # Project metrics
GET    /api/analytics/revenue      # Revenue tracking
GET    /api/analytics/employees    # Team metrics
```

### Health
```
GET    /health                     # Health check
GET    /api/health                 # Detailed health
```

---

## 🔐 Authentication Flow

```
1. Register → Password hashed with bcrypt
2. Login → User validated, JWT + Refresh token created
3. Frontend stores tokens (localStorage + httpOnly cookie)
4. Each request → Authorization header includes JWT
5. JWT expires → Use refresh token to get new JWT
6. Refresh expires → User logs out, redirected to login
```

### JWT Structure
```javascript
Access Token: {
  userId: "123",
  email: "user@example.com",
  role: "admin",
  iat: 1234567890,
  exp: 1234654290
}

Refresh Token: {
  userId: "123",
  type: "refresh",
  iat: 1234567890,
  exp: 1245654290
}
```

---

## 📊 Data Models

### User
```javascript
{
  email: String (unique),
  password: String (hashed),
  firstName: String,
  lastName: String,
  role: "admin" | "manager" | "employee",
  department: String,
  phone: String,
  avatar: String,
  isActive: Boolean,
  createdAt: Date,
  updatedAt: Date
}
```

### Client
```javascript
{
  name: String,
  email: String,
  phone: String,
  address: Object,
  industry: String,
  website: String,
  status: "active" | "inactive",
  managedBy: ObjectId (User),
  projects: [ObjectId],
  revenue: Number,
  createdAt: Date
}
```

### Project
```javascript
{
  name: String,
  description: String,
  client: ObjectId,
  manager: ObjectId (User),
  status: "pending" | "active" | "completed",
  budget: Number,
  spent: Number,
  startDate: Date,
  endDate: Date,
  tasks: [ObjectId],
  team: [ObjectId],
  createdAt: Date
}
```

### Task
```javascript
{
  title: String,
  description: String,
  project: ObjectId,
  assignedTo: ObjectId (User),
  status: "todo" | "in-progress" | "done",
  priority: "low" | "medium" | "high",
  dueDate: Date,
  completedAt: Date,
  createdAt: Date
}
```

---

## 🔒 Security Features

- ✅ **JWT Authentication** - Secure token-based auth
- ✅ **Password Hashing** - bcryptjs with salt
- ✅ **Rate Limiting** - Prevent brute force
- ✅ **Input Validation** - Joi + express-validator
- ✅ **CORS Protection** - Configurable origins
- ✅ **Helmet.js** - Security headers
- ✅ **Error Handling** - No sensitive info in responses
- ✅ **Role-Based Access** - RBAC middleware

---

## ⚙️ Middleware Stack

```javascript
// Request Flow
1. CORS Middleware
2. Body Parser
3. Logger Middleware
4. Rate Limiter
5. Routes
6. Auth Middleware
7. Validation Middleware
8. Controller
9. Error Handler
10. Response
```

---

## 🚀 Deployment (Vercel)

```bash
# Deploy
vercel deploy --prod

# Add env vars
vercel env add MONGODB_URI
vercel env add JWT_SECRET
vercel env add JWT_REFRESH_SECRET
vercel env add CORS_ORIGIN
```

---

## 🧪 Testing

```bash
# Run tests
npm test

# Watch mode
npm run test:watch

# Coverage
npm run test:coverage
```

---

## 🐛 Troubleshooting

### MongoDB Connection Error
```bash
# Verify connection string
# Check IP whitelist
# Test credentials
mongodb+srv://user:password@cluster.mongodb.net/dbname
```

### JWT Token Issues
```bash
# Check JWT_SECRET is set
# Verify token format in headers
# Check token expiry
```

### Port Already in Use
```bash
# Kill process
lsof -i :4000
kill -9 <PID>

# Or change PORT in .env
```

---

## 📈 Roadmap

- [ ] WebSocket for real-time updates
- [ ] Advanced filtering & pagination
- [ ] Bulk operations
- [ ] File upload support
- [ ] Email notifications
- [ ] Activity logging
- [ ] Audit trails
- [ ] GraphQL API

---

## 🤝 Contributing

```bash
git checkout -b feature/new-feature
git commit -m "feat: Add new feature"
git push origin feature/new-feature
```

---

## 📄 License

MIT © [Hassan Naseer Ahmed](https://github.com/mhassannaseerahmed-arch)

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=a855f7&height=100&section=footer" width="100%" />
</p>

<p align="center">
  <sub>⚡ Building enterprise-grade APIs with Express and TypeScript</sub>
</p>
