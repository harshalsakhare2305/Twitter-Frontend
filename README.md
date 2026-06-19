# 🐦 Twitter  — Next.js + GraphQL

A full-featured Twitter/X clone built with **Next.js**, **GraphQL**, and **TailwindCSS**. Supports Google OAuth authentication, tweet creation with image uploads, and a social follow/unfollow system.

---

## ✨ Features

- 🔐 **Google OAuth Authentication** — Sign in with Google using `@react-oauth/google`
- 🐦 **Tweet Feed** — View all tweets with author details and images
- 📝 **Create Tweets** — Post tweets with optional image attachments (via signed S3 URLs)
- 🖼️ **Image Uploads** — Secure pre-signed URL flow for uploading tweet images
- 👤 **User Profiles** — View any user's profile, tweets, followers, and following count
- 🤝 **Follow / Unfollow** — Follow and unfollow other users
- 🔄 **Real-time UI Updates** — Optimistic updates powered by TanStack Query
- 🎨 **Responsive UI** — Dark-themed, Twitter-like layout built with TailwindCSS

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 16 (Pages Router) |
| Language | TypeScript |
| Styling | TailwindCSS v4 |
| API | GraphQL via `graphql-request` |
| GraphQL Client | Apollo Client + TanStack React Query |
| Auth | Google OAuth (`@react-oauth/google`) |
| Code Generation | GraphQL Code Generator |
| Notifications | React Hot Toast |
| Icons | React Icons |

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- Yarn

### Installation

```bash
git clone https://github.com/harshalsakhare2305/Twitter.git
cd Twitter
yarn install
```

### Environment Variables

Create a `.env.local` file in the root:

```env
NEXT_PUBLIC_API_URL=http://localhost:8000/graphql
NEXT_PUBLIC_GOOGLE_CLIENT_ID=your_google_client_id
```

### Run Development Server

```bash
yarn dev
```

This concurrently runs the **GraphQL Code Generator** (watch mode) and the **Next.js dev server**.

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 📁 Project Structure

```
├── src/
│   └── pages/               # Next.js pages (index, [id] user profile)
│       └── components/      # Reusable UI components (FeedCard, TwitterLayout, etc.)
├── graphql/
│   ├── queries/             # GraphQL query definitions (tweets, users)
│   └── mutations/           # GraphQL mutation definitions (tweets, follow/unfollow)
├── graphql-clients/
│   └── api.ts               # GraphQL client setup
├── hooks/
│   ├── tweet.ts             # Tweet-related custom hooks
│   └── user.ts              # User-related custom hooks
├── gql/                     # Auto-generated GraphQL types (via codegen)
└── codegen.ts               # GraphQL Code Generator config
```

---

## 📡 GraphQL Operations

### Queries
- `GetAllTweets` — Fetch the full tweet feed with author info
- `GetCurrentUser` — Get the authenticated user's profile, following, and followers
- `GetUserById` — Fetch a specific user's profile and tweets
- `GetSignedURLForTweet` — Get a pre-signed S3 URL for image upload

### Mutations
- `CreateTweet` — Post a new tweet with optional image
- `FollowUser` — Follow another user
- `UnfollowUser` — Unfollow a user

---

## 🌐 Deployment

Deploy easily on [Vercel](https://vercel.com):

```bash
yarn build
```

Or connect your GitHub repo to Vercel for automatic deployments.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
