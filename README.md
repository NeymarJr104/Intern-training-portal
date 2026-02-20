# Intern Training Portal

A professional frontend training portal built with React, TypeScript, and Vite.

## Features

- **Authentication**: Mock login with localStorage persistence
- **Protected Routes**: Dashboard and course pages require authentication
- **Professional UI**: Clean, minimal light theme design
- **Responsive Layout**: Navbar, sidebar, and main content area
- **Reusable Components**: CourseCard, VideoPlayer, ProgressBar

## Project Structure

```
src/
  layout/
    Layout.tsx      # Main layout wrapper with navbar and sidebar
    Navbar.tsx      # Top navigation bar with logout button
    Sidebar.tsx     # Side navigation with Dashboard and My Courses
  pages/
    Login.tsx       # Authentication page
    Dashboard.tsx   # Home page (protected)
    CourseDetail.tsx # Course detail page (protected)
  components/
    CourseCard.tsx  # Reusable course card component
    VideoPlayer.tsx # Video player component
    ProgressBar.tsx # Progress indicator component
  data/
    mockCourses.ts  # Mock course data
  store/
    authStore.ts    # Zustand auth store
  App.tsx          # Main app with routing
  main.tsx         # React root mount
```

## Authentication Flow

1. User visits `/` and sees Login page
2. Enter credentials: `intern@company.com` / `123456`
3. On successful login:
   - User is stored in Zustand auth store
   - User is persisted to localStorage
   - User is redirected to `/dashboard`
4. Protected routes (`/dashboard`, `/courses`) check auth state
5. If not authenticated, user is redirected to `/`
6. Logout button clears auth and redirects to `/`

## Getting Started

### Install dependencies

```bash
npm install
```

### Start development server

```bash
npm run dev
```

Open http://localhost:5173 in your browser.

## Testing Login

1. Navigate to http://localhost:5173
2. You'll see the Login page
3. Use credentials:
   - Email: `intern@company.com`
   - Password: `123456`
4. Click Login → you'll be redirected to Dashboard
5. Click Logout in the navbar to return to login

## Build for production

```bash
npm run build
```

## Technologies

- **React 18** - UI library
- **TypeScript** - Type safety
- **Vite** - Build tool
- **React Router 6** - Client-side routing
- **Zustand** - State management

## Notes

- No external UI framework used (just styled inline CSS)
- All styling is minimal and professional
- Components are reusable and composable
- Auth state is persisted to localStorage
- Routes are protected based on auth state
