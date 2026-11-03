# Learnora — Learning & Course Discovery Platform

Learnora is a responsive course-discovery web application. Visitors can explore a structured course catalogue, search and filter learning options, and create an account to access protected course details and profile features.

## Features

- Email/password registration and login through Better Auth.
- Google sign-in integration (requires Google OAuth credentials).
- Course catalogue with title search, category filters, and difficulty filters.
- Course detail pages protected by authentication.
- User profile view and profile-information updates.
- Home-page sections for popular courses, trending courses, learning tips, and instructors.
- Responsive layouts, loading states, toast feedback, and a not-found page.

## Tech stack

- Next.js App Router and React
- Tailwind CSS and DaisyUI
- Better Auth with its MongoDB adapter
- MongoDB Node.js driver
- React Hook Form, Framer Motion, and icon libraries

## Run locally

**Requirements:** Node.js compatible with the Next.js version in `package.json`, npm, and a MongoDB database.

```bash
npm install
cp .env.example .env.local
# Fill in the values in .env.local before starting the app.
npm run dev
```

Open `http://localhost:3000`.

## Environment variables

Create `.env.local` (never commit this file):

```dotenv
MONGO_URI=mongodb://127.0.0.1:27017/learnora
BETTER_AUTH_SECRET=replace_with_a_long_random_secret
NEXT_PUBLIC_BETTER_AUTH_URL=http://localhost:3000
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
```

Google login will only work after setting valid OAuth credentials and configuring the matching redirect URI in Google Cloud. Set `NEXT_PUBLIC_BETTER_AUTH_URL` to the deployed app URL in production.

## Useful scripts

```bash
npm run dev      # development server
npm run build    # production build
npm start        # start production server after build
npm run lint     # ESLint
```

## Data and deployment notes

Course catalogue content is stored in `src/data/courses.json`. Authentication data is stored through the configured MongoDB adapter. No production database or OAuth credentials are included in this repository.

## Source attribution note

The supplied source archive included an earlier README linking to `github.com/mdalaminmiah/b13-a8-skillsphere-app`. Confirm your right to publish this code and retain any required notices before making this repository public. The supplied archive did not include a `LICENSE` file.
