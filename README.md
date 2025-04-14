# HealthyMealAI

HealthyMealAI is a web application that allows users to customize recipes found on the internet according to their individual dietary needs using artificial intelligence.

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![MVP Status](https://img.shields.io/badge/Status-In%20Development-yellow)]()

## Table of Contents
- [Project Description](#project-description)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Available Scripts](#available-scripts)
- [Project Scope](#project-scope)
- [Project Status](#project-status)
- [License](#license)

## Project Description

HealthyMealAI solves the problem of manually adapting online recipes to match dietary restrictions, allergies, or food intolerances. Many people struggle with modifying recipes as it requires culinary expertise and nutritional knowledge.

### Key Features

- **Simple OAuth Authentication**: Register and log in via Facebook, Apple, or Microsoft
- **Dietary Preference Management**: Store food intolerances, allergies, and dietary restrictions in your profile
- **Recipe Search**: Find recipes available online through integrated search
- **AI-Powered Recipe Modification**: Automatically adapt recipes to your dietary needs using ChatGPT
- **Recipe Management**: Save, browse, and delete your customized recipes
- **Search Functionality**: Find saved recipes by dish name or ingredients
- **Rating System**: Simple LIKE/DISLIKE mechanism for your recipes

### Target Audience

Anyone who wants to eat healthier, with a special focus on individuals with dietary restrictions, allergies, or food intolerances.

## Tech Stack

The application is built using a modern tech stack:

### Frontend
- **Angular**: JavaScript framework for building the user interface
- **Bootstrap**: CSS framework for responsive design

### Backend
- **.NET 9**: Framework for building the API

### Database
- **PostgreSQL**: Open-source relational database
- **Azure Database for PostgreSQL**: Managed database service in Azure cloud

### AI Integration
- **OpenAI API**: Integration with ChatGPT for recipe modification
- **Azure OpenAI Service** (optional): For better cost control and performance

### DevOps and CI/CD
- **GitHub Actions**: Automation of build and deployment processes
- **Docker**: Application containerization for consistent deployments

### Hosting
- **Azure App Service**: Web application hosting

### Security
- **Azure Key Vault**: Secure storage of API keys and other sensitive data
- **OAuth 2.0**: Authentication standard for login via Facebook, Apple, Microsoft

### Project Management and Monitoring
- **GitHub**: Code repository and version management
- **GitHub Issues**: Task and bug tracking
- **GitHub Project Boards**: Sprint and workflow management
- **Application Insights**: Performance and usage monitoring

## Getting Started

Follow these instructions to set up the project locally.

### Prerequisites

- [Node.js](https://nodejs.org/) (for Angular frontend)
- [.NET 9 SDK](https://dotnet.microsoft.com/download)
- [Docker](https://www.docker.com/products/docker-desktop) (optional, for containerization)
- [PostgreSQL](https://www.postgresql.org/download/) (or use Docker container)
- API keys for OpenAI

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd front-end/HealthyMealAI
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create environment configuration file:
   ```bash
   cp src/environments/environment.example.ts src/environments/environment.ts
   ```

4. Update the environment file with your API endpoints and OAuth configurations

5. Start the development server:
   ```bash
   ng serve
   ```

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd back-end/HealthyMealAI
   ```

2. Restore dependencies:
   ```bash
   dotnet restore
   ```

3. Update connection strings in `appsettings.Development.json`

4. Set up your database:
   ```bash
   dotnet ef database update
   ```

5. Run the API:
   ```bash
   dotnet run
   ```

## Available Scripts

### Frontend

- `ng serve`: Start the development server
- `ng build`: Build the application for production
- `ng test`: Run unit tests
- `ng lint`: Run linting checks

### Backend

- `dotnet run`: Run the application
- `dotnet watch run`: Run with hot reload
- `dotnet test`: Run tests
- `dotnet ef migrations add <name>`: Create a new database migration
- `dotnet ef database update`: Apply migrations to the database

## Project Scope

### MVP Features

- OAuth registration and login (Facebook, Apple, Microsoft)
- User profile with dietary preferences
- Recipe search through Google integration
- AI-based recipe modification
- Recipe management (save, view, delete)
- Recipe search functionality
- Simple rating system (LIKE/DISLIKE)

### Not in Scope for MVP

The following features are planned for future versions:

- Import recipes from URL
- Rich multimedia support (recipe images)
- Recipe sharing between users
- Social features
- Password recovery mechanism
- Recipe categorization and tagging
- Email verification
- OpenAI API request limits per user
- AI fallback mechanism
- Application promotion strategy
- Custom recipe creation
- Original vs. modified recipe comparison
- Recipe modification history

## Project Status

HealthyMealAI is currently in development as an MVP (Minimum Viable Product). The planned development timeline is 6 weeks.

### Success Metrics

- 90% of users have completed dietary preferences in their profile
- 75% of users generate one or more recipes per week

## License

This project is licensed under the MIT License - see the LICENSE file for details.