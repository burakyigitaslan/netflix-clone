# Netflix Clone

A full-stack Netflix clone built with Next.js 13, featuring user authentication, a dynamic movie library, and a responsive UI inspired by the original Netflix interface.

## Key Features

- **Authentication** — Email/password registration and login with bcrypt-hashed passwords. OAuth sign-in via Google and GitHub using NextAuth.js with Prisma adapter and JWT sessions.
- **Profile Selection** — Dedicated profile selection screen after login, styled like Netflix's "Who's watching?" page.
- **Billboard** — Randomly featured movie displayed prominently on the homepage with auto-play trailer.
- **Movie Browsing** — Browse all movies in a horizontally scrollable list with thumbnail cards. Hover over a card for an expanded preview with metadata.
- **Movie Details** — Interactive info modal showing movie description, genre, and duration.
- **My List (Favorites)** — Add/remove movies to a personal favorites list with optimistic UI updates.
- **Video Playback** — Full watch page for streaming movie trailers/videos.
- **Responsive Design** — Mobile-friendly navigation with a collapsible mobile menu and adaptive layouts.

## Tech Stack

| Layer | Technology |
|---|---|
| **Framework** | Next.js 13 (Pages Router) |
| **Language** | TypeScript |
| **UI** | React 18, Tailwind CSS, React Icons |
| **Database** | MongoDB (via Prisma ORM) |
| **Auth** | NextAuth.js (Credentials, Google, GitHub) |
| **State** | Zustand (modal state), SWR (data fetching & caching) |
| **HTTP** | Axios |
| **Utilities** | Lodash, bcrypt |

## Project Structure

```
netflix-clone/
├── components/          # Reusable UI components
│   ├── AccountMenu       # User account dropdown
│   ├── Billboard         # Featured hero movie
│   ├── FavoriteButton    # Add/remove from My List
│   ├── InfoModal         # Movie details modal
│   ├── Input             # Styled form input
│   ├── MobileMenu        # Responsive mobile nav
│   ├── MovieCard         # Hoverable movie thumbnail
│   ├── MovieList         # Horizontal movie carousel
│   ├── Navbar            # Top navigation bar
│   ├── NavbarItem        # Individual nav link
│   └── PlayButton        # Play movie CTA
├── hooks/               # Custom React hooks (SWR)
│   ├── useBillboard      # Fetch random billboard movie
│   ├── useCurrentUser     # Fetch authenticated user
│   ├── useFavorites       # Fetch user's favorites list
│   ├── useInfoModal       # Zustand modal state
│   ├── useMovie           # Fetch single movie by ID
│   └── useMovieList       # Fetch all movies
├── lib/                 # Shared utilities
│   ├── fetcher            # Axios GET wrapper for SWR
│   ├── prismadb           # Prisma client singleton
│   └── serverAuth         # Server-side auth helper
├── pages/               # Next.js pages & API routes
│   ├── api/
│   │   ├── auth/[...nextauth]  # NextAuth config
│   │   ├── current             # GET current user
│   │   ├── favorite            # POST toggle favorite
│   │   ├── favorites           # GET user favorites
│   │   ├── movies/             # GET all movies
│   │   ├── movies/[movieId]    # GET movie by ID
│   │   ├── random              # GET random movie
│   │   └── register            # POST register user
│   ├── auth               # Login / Register page
│   ├── profiles            # Profile selection page
│   ├── watch/[movieId]     # Video player page
│   └── index               # Homepage
├── prisma/
│   └── schema.prisma      # Database schema (User, Account, Session, Movie)
└── styles/
    └── globals.css        # Global styles
```

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

3. **Configure environment variables**

   Create a `.env` file in the root directory:
   ```env
   DATABASE_URL="mongodb+srv://..."
   NEXTAUTH_SECRET="your-nextauth-secret"
   NEXTAUTH_JWT_SECRET="your-jwt-secret"

   # OAuth (optional)
   GITHUB_ID="your-github-client-id"
   GITHUB_SECRET="your-github-client-secret"
   GOOGLE_CLIENT_ID="your-google-client-id"
   GOOGLE_CLIENT_SECRET="your-google-client-secret"
   ```

4. **Generate Prisma client**
   ```bash
   npx prisma generate
   ```

5. **Start the development server**
   ```bash
   npm run dev
   ```

Open [http://localhost:3000](http://localhost:3000) to view the application.
