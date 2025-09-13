# Project Template

This is a template for project MDX files. Copy this to your GitHub repository under `PersonalArchive/projects/{project-name}/index.mdx`.

## Required Frontmatter Structure

```yaml
---
title: "Your Project Title"
description: "Brief description of your project"
date: "2025-01-10"
category: "Web App" # or Mobile App, Data Science, CLI Tool, etc.
technologies: ["React", "Next.js", "TypeScript", "TailwindCSS"]
githubUrl: "https://github.com/username/repo"
liveUrl: "https://your-project.com" # optional
roles: ["Full Stack Developer", "UI/UX Designer"] # your roles in this project
team: ["John Doe", "Jane Smith"] # optional, people who worked with you
deployment: "Vercel" # optional, where it's deployed
year: 2025
---
```

## Required File Structure

For each project in your GitHub repository, create this structure:
```
PersonalArchive/
└── projects/
    └── your-project-name/
        ├── index.mdx          # Main content file
        ├── Banner.png         # Project banner image (optional)
        └── Icon.png           # Project icon/logo (optional, 64x64px recommended)
```

## Example Project Content

Here's an example of what goes in the MDX file after the frontmatter:

```markdown
---
title: "My Awesome Project"
description: "A comprehensive web application built with modern technologies"
date: "2025-01-10"
category: "Web App"
technologies: ["React", "Next.js", "TypeScript", "TailwindCSS", "Prisma", "PostgreSQL"]
githubUrl: "https://github.com/nfahrisalim/awesome-project"
liveUrl: "https://awesome-project.vercel.app"
roles: ["Full Stack Developer", "UI/UX Designer"]
team: ["Alice Johnson", "Bob Wilson"]
deployment: "Vercel with PostgreSQL on Railway"
year: 2025
---

## Project Overview

This project was built to solve [specific problem]. It features a modern, responsive design with a focus on user experience and performance.

## Key Features

- **Feature 1**: Description of what this feature does
- **Feature 2**: Another important feature
- **Feature 3**: Third key feature

## Technical Implementation

### Frontend
The frontend is built using React and Next.js, providing server-side rendering and optimal performance. The UI is styled with TailwindCSS for rapid development and consistent design.

### Backend
The backend uses Prisma as the ORM with PostgreSQL for data persistence. Authentication is handled through NextAuth.js.

### Architecture
The application follows a clean architecture pattern with separation of concerns:
- API routes for backend logic
- React components for UI
- Custom hooks for state management
- Utility functions for common operations

## Challenges & Solutions

### Challenge 1: Performance Optimization
**Problem**: Initial load times were slow due to large bundle sizes.
**Solution**: Implemented code splitting, lazy loading, and optimized images with Next.js Image component.

### Challenge 2: Database Performance
**Problem**: Complex queries were causing slow response times.
**Solution**: Added database indexes, implemented caching with Redis, and optimized queries.

## Results & Impact

- 🚀 **Performance**: 95+ Lighthouse score across all metrics
- 👥 **Users**: Successfully onboarded 1000+ users in first month
- 📈 **Growth**: 40% increase in user engagement compared to previous solution

## Screenshots

![Main Dashboard](https://via.placeholder.com/800x400)
*Main dashboard showing key metrics and navigation*

![User Profile](https://via.placeholder.com/800x400)
*User profile page with customization options*

## Lessons Learned

1. **Early Testing**: Implementing testing from the start saved significant debugging time
2. **User Feedback**: Regular user feedback sessions led to crucial UX improvements
3. **Performance Monitoring**: Setting up monitoring early helped identify bottlenecks quickly

## Future Enhancements

- [ ] Mobile application using React Native
- [ ] Advanced analytics dashboard
- [ ] AI-powered recommendations
- [ ] Multi-language support

## Tech Stack Deep Dive

### Frontend Technologies
- **React 18**: For building interactive user interfaces
- **Next.js 14**: For SSR, routing, and optimization
- **TypeScript**: For type safety and better developer experience
- **TailwindCSS**: For utility-first styling

### Backend Technologies  
- **Prisma**: For type-safe database operations
- **PostgreSQL**: For reliable data storage
- **NextAuth.js**: For authentication and session management

### DevOps & Deployment
- **Vercel**: For frontend deployment and serverless functions
- **Railway**: For PostgreSQL database hosting
- **GitHub Actions**: For CI/CD pipeline
```

## Important Notes

1. **Banner Image**: Make sure your banner image is named `Banner.png`, `Banner.jpg`, or similar (case-insensitive)
2. **Project Icon**: Add a project icon/logo named `Icon.png`, `Logo.png`, or `favicon.png` (64x64px recommended)
3. **Slug**: The folder name will become the URL slug (e.g., `my-awesome-project` becomes `/projects/my-awesome-project`)
4. **Technologies Array**: List the main technologies used in the project
5. **Roles Array**: List your specific roles in the project
6. **Team Array**: Optional - list team members who worked with you
7. **Deployment**: Optional - describe where/how the project is deployed

## Repository Structure

Your GitHub repository `PersonalArchive` should have this structure:

```text
PersonalArchive/
├── Blog/
│   ├── blog-post-1/
│   │   ├── index.mdx
│   │   └── Banner.png
│   └── blog-post-2/
│       ├── index.mdx  
│       └── Banner.jpg
└── projects/
    ├── project-1/
    │   ├── index.mdx
    │   ├── Banner.png
    │   └── Icon.png
    ├── project-2/
    │   ├── index.mdx
    │   ├── Banner.jpg
    │   └── Logo.png
    └── project-3/
        ├── index.mdx
        ├── Banner.webp
        └── favicon.png
```

The system will automatically:

- Fetch all project folders from the `projects` directory
- Parse the MDX frontmatter for metadata
- Look for banner images and project icons automatically
- Generate project listings and detail pages
- Handle routing and SEO
