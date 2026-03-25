# 3300-landing-page-2

A minimal static HTML landing page project.

## Project Structure

- `index.html` - Main entry point (currently displays "Hello World")
- `.github/workflows/` - Azure Static Web Apps CI/CD configuration (original deployment pipeline)

## Running the App

The app is served as a static site using Python's built-in HTTP server on port 5000.

**Workflow:** "Start application" — runs `python3 -m http.server 5000`

## Deployment

Configured as a static site with `publicDir: "."`.
