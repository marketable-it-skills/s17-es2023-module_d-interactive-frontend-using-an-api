# How to develop and deploy the project?

1. Create a new GitHub repository using the [React or Frontend template](https://github.com/new?template_name=mits-react-v1&template_owner=marketable-it-skills).
2. Place your solution code inside the `/src` folder.
3. Pushing to GitHub triggers GitHub Actions (see `.github/`) to:
   - Build a Docker image
   - Push it to GitHub Container Registry
4. In `docker-compose.yml`, update:
   `image: ghcr.io/<your-github-account>/<your-repo-name>:latest`
5. Run locally:
   ```bash
   docker compose up -d
   ```
6. Visit: [http://localhost](http://localhost)

## Development Setup

### Prerequisites
- Node.js 18+ and npm
- Docker and Docker Compose
- Access to the provided Module C API solution

### Local Development
1. Install dependencies:
   ```bash
   npm install
   ```

2. Start the provided Module C API backend:
   ```bash
   cd assets/swagger
   docker compose up -d
   ```

3. Run the frontend development server:
   ```bash
   npm run dev
   ```

4. The frontend application will be available at `http://localhost:3000`

### Backend API Access
The frontend connects to the Module C API solution provided:
- API base URL: `http://localhost:5555` (when running locally)
- API documentation: Available in `assets/swagger/` folder
- Authentication: Use API tokens as described in the project requirements
- Services: ChatterBlast (chat), DreamWeaver (image generation), MindReader (image recognition)

### Framework Requirements
- Use a modern JavaScript framework (React, Vue, Angular, or similar)
- Implement as Single Page Application (SPA)
- Handle routing within the framework
- Ensure page reloads maintain state (except unsaved inputs)