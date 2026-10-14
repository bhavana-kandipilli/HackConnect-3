# 🚀 HackConnect — AI-Powered Networking Platform

**Connect. Collaborate. Build Something Extraordinary.**

HackConnect is a space-themed networking platform designed to help hackathon participants discover like-minded developers, connect with potential teammates, communicate in real time, and collaborate more effectively. It combines interactive network visualization, attendee discovery, live messaging, location sharing, and gamified networking into one platform.

## ✨ Features

### 🌍 Interactive Networking Dashboard
- Explore a visually engaging, globe-inspired networking interface.
- Discover registered participants through interactive avatar markers.
- View event announcements and attendee activity.

### 🤝 Smart Networking & Connections
- Discover fellow hackathon participants.
- Explore participant profiles, skills, interests, and networking goals.
- Send and manage connection requests.
- Build a network of mutually accepted connections.

### 💬 Real-Time Chat
- Communicate with connected participants.
- Track unread messages.
- Stay updated through real-time messaging and database subscriptions.

### 📍 Location Sharing
- Share campus or event locations with other participants.
- View shared location information to help coordinate in-person meetups.

### 👤 Profile & Onboarding
- Create and customize participant profiles.
- Choose networking goals and showcase skills and interests.
- Personalize avatars for a more engaging experience.

### 🪐 Aura Board — Gamified Networking
- Track networking activity through connection-based streaks.
- Encourage participants to expand their professional network.
- Add a gamified dimension to the hackathon experience.

### 📩 Feedback
- Access the feedback page directly from the participant navigation.
- Redirect participants to a Google Form to collect feedback and suggestions.

### 🛡️ Admin Portal
- Provide a separate administrator login.
- Manage hackathon events and view event-related information.
- Access reporting and event details through dedicated admin pages.

### 🌌 Immersive Space-Themed UI
- Animated starfield and video backgrounds.
- Dark interface with gradient accents.
- Responsive navigation for desktop and mobile devices.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| React | Component-based user interface |
| TypeScript | Type safety and maintainable code |
| Vite | Development server and build tooling |
| Tailwind CSS | Responsive styling and UI design |
| React Router | Client-side navigation and route protection |
| Supabase | Authentication, database, and real-time functionality |
| Zustand | Application state management |
| Motion | Animations and interactive visual effects |
| Lucide React | Icons |
| React Hot Toast | User feedback and notifications |

**Note:** Update this list if any technology is not used in the current version of your project.

## 🏗️ Project Structure

```text
HackConnect/
├── public/
│   └── stars-video.mp4
├── src/
│   ├── app/
│   │   ├── admin/
│   │   │   ├── AdminLoginPage.tsx
│   │   │   ├── AdminDashboard.tsx
│   │   │   ├── AdminEventDetail.tsx
│   │   │   └── AdminReports.tsx
│   │   ├── participant/
│   │   │   ├── AuraBoardPage.tsx
│   │   │   ├── ChatPage.tsx
│   │   │   ├── ConnectionsPage.tsx
│   │   │   ├── DashboardPage.tsx
│   │   │   ├── Feedback.tsx
│   │   │   ├── LocationPage.tsx
│   │   │   ├── MainLayout.tsx
│   │   │   ├── ProfilePage.tsx
│   │   │   └── RequestsPage.tsx
│   │   ├── LandingPage.tsx
│   │   ├── LoginPage.tsx
│   │   └── OnboardingPage.tsx
│   ├── components/
│   │   ├── Globe.tsx
│   │   ├── RevealText.tsx
│   │   ├── StarsBackground.tsx
│   │   └── vid-bg.tsx
│   ├── hooks/
│   │   └── useRealtime.ts
│   ├── lib/
│   │   ├── firebase.ts
│   │   ├── mockDb.ts
│   │   └── supabase.ts
│   ├── stores/
│   │   ├── useAuthStore.ts
│   │   ├── useChatStore.ts
│   │   ├── useEventStore.ts
│   │   └── useNetworkingStore.ts
│   ├── types/
│   │   └── index.ts
│   ├── App.tsx
│   ├── App.css
│   └── index.css
├── supabase/
├── .env.example
├── package.json
└── README.md
```

*The structure above is illustrative. Adjust filenames to match the actual files in your repository.*

## ⚙️ Getting Started

### Prerequisites

Install the following before running the project:

- [Node.js](https://nodejs.org/) — preferably a current LTS version.
- npm — included with Node.js.
- A Supabase account and project.

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/HackConnect.git
cd HackConnect
```

Replace `YOUR_USERNAME` with your GitHub username and `HackConnect` with your actual repository name if different.

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file in the project root and add the required configuration:

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_publishable_or_anon_key
```

If your project uses a separate Node.js authentication server, configure its server-side environment variables separately, including the appropriate Supabase service-role secret where required.

**Security:** Never commit `.env` files, service-role keys, passwords, or other secrets to GitHub. Keep server-side secrets out of frontend code. Add `.env` to `.gitignore` and commit only a sanitized `.env.example`.

### 4. Configure Supabase

1. Create a project in the Supabase dashboard.
2. Copy your project URL and publishable/anon key into `.env`.
3. Configure the authentication provider used by your application.
4. Set up the database tables and Row Level Security (RLS) policies required by your project.
5. Apply any SQL migrations included in the repository.

Required tables and policies depend on your actual implementation. Do not disable RLS globally just to resolve permission errors.

### 5. Start the development server

```bash
npm run dev
```

Open the local URL printed in the terminal, usually:

```text
http://localhost:5173
```

### 6. Build for production

```bash
npm run build
```

To preview the production build locally:

```bash
npm run preview
```

## 🔐 Authentication & Access Control

HackConnect separates participant and administrator experiences.

- Participants sign in and complete onboarding before accessing protected networking features.
- Protected routes restrict access to authenticated users.
- Administrator routes check the application's administrator authorization state.
- Database permissions should be enforced using appropriate Supabase RLS policies and server-side authorization.

**Important:** Hiding an admin page in the frontend is not sufficient security. Administrative operations must also be protected on the server or database.

## 🌐 Deployment

The frontend can be deployed to platforms such as:

- [Vercel](https://vercel.com/)
- [Netlify](https://www.netlify.com/)

Before deploying:

1. Configure environment variables in the hosting platform.
2. Configure SPA routing rewrites so React Router routes work on refresh.
3. Verify Supabase authentication URLs and redirect URLs.
4. Deploy any separate backend server independently.
5. Test login, onboarding, connections, messaging, location sharing, feedback, and admin permissions in the deployed environment.

## 🗺️ Roadmap

Potential future improvements include:

- AI-powered teammate recommendations based on skills and interests.
- Better attendee discovery and filtering.
- Enhanced campus navigation.
- Improved networking analytics and engagement insights.
- Stronger automated testing and accessibility support.
- Additional anti-spam and account security features.

## 🤝 Contributing

Contributions, suggestions, and bug reports are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes with clear messages.
4. Open a pull request describing your changes.

## 📄 License

Choose a license before distributing the project. If you want others to reuse and modify your code, consider adding an appropriate open-source license, such as the MIT License.

---

**Built with 💜 for better hackathon networking.**

*HackConnect — Meet the right people. Build better projects. Turn connections into collaborations.*
