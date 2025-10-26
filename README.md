# Task Management Application

A full-stack task management application built with React (Vite), Node.js, Express, and MongoDB. The application is containerized using Docker for easy development and deployment.

## Tech Stack

### Frontend
- React (with Vite)
- TailwindCSS
- Modern JavaScript (ES6+)

### Backend
- Node.js
- Express.js
- MongoDB
- Docker

## Project Structure
```
.
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/    # React components
│   │   ├── services/      # API services
│   │   └── utils/         # Utility functions
│   ├── Dockerfile         # Frontend Docker configuration
│   └── package.json
├── server/                # Backend Node.js application
│   ├── controllers/       # Request handlers
│   ├── models/           # Database models
│   ├── routes/           # API routes
│   ├── Dockerfile        # Backend Docker configuration
│   └── package.json
└── docker-compose.yml     # Docker compose configuration
```

## Prerequisites

Before running this application, make sure you have the following installed:
- [Docker](https://www.docker.com/products/docker-desktop)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/AlexZhu777/devops_project1.git
   cd devops_project1
   ```

2. Create a `.env` file in the server directory:
   ```bash
   cd server
   echo "PORT=5000\nMONGO_URI=mongodb://mongodb:27017/taskdb" > .env
   cd ..
   ```

3. Start the application using Docker Compose:
   ```bash
   docker-compose up --build
   ```

4. Access the application:
   - Frontend: [http://localhost:5173](http://localhost:5173)
   - Backend API: [http://localhost:5000](http://localhost:5000)
   - API Health Check: [http://localhost:5000/health](http://localhost:5000/health)

## Development

### Running Services Individually

#### Frontend (Development Mode)
```bash
cd client
npm install
npm run dev
```

#### Backend (Development Mode)
```bash
cd server
npm install
npm run dev
```

### API Endpoints

- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create a new task
- `DELETE /api/tasks/:id` - Delete a task

## Docker Configuration

The project uses three Docker containers:
1. **Frontend**: React application served through Vite
2. **Backend**: Node.js/Express API
3. **MongoDB**: Database service

Data persistence is handled through Docker volumes for the MongoDB container.

## Troubleshooting

1. **MongoDB Connection Issues**
   - Ensure MongoDB container is running: `docker ps`
   - Check MongoDB logs: `docker-compose logs mongodb`

2. **Frontend Not Loading Tasks**
   - Verify API URL in docker-compose.yml
   - Check browser console for CORS errors
   - Ensure backend service is running

3. **Backend Service Issues**
   - Check server logs: `docker-compose logs backend`
   - Verify MongoDB connection string
   - Ensure all required environment variables are set

## Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/new-feature`
3. Commit your changes: `git commit -am 'Add new feature'`
4. Push to the branch: `git push origin feature/new-feature`
5. Submit a pull request

## License

This project is licensed under the MIT License.