# Netflix Clone

A full-stack Netflix clone built with Next.js 13, featuring a responsive design, user authentication, and a dynamic movie library.

## Key Features

- **Authentication**: Secure login and registration with NextAuth (Google & Github).
- **Responsive UI**: "Billboard" video playback, mobile-friendly navigation, and polished animations.
- **My List**: Add and remove movies from your favorites list.
- **Movie Details**: Interactive info modals with movie descriptions and metadata.
- **Data Strategy**: Optimistic updates and efficient caching using SWR.

## Tech Stack

- **Framework**: Next.js 13 (Pages Router), React 18
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Database**: MongoDB (via Prisma ORM)
- **State Management**: Zustand
- **Auth**: NextAuth.js

## How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/burakyigitaslan/netflix-clone.git
   cd netflix-clone
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure Environment**
   Create a `.env` file in the root directory and add your MongoDB connection string and NextAuth secrets:
   ```env
   DATABASE_URL="mongodb+srv://..."
   NEXTAUTH_SECRET="your-secret"
   ```

4. **Initialize Database**
   ```bash
   npx prisma generate
   ```

5. **Start the app**
   ```bash
   npm run dev
   ```

Open [http://localhost:3000](http://localhost:3000) to view the application.
