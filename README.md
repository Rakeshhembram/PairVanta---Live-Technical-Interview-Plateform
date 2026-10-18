# PairVanta — Live Technical Interview Platform

PairVanta is a web-based technical interview platform designed to streamline remote hiring through live video interviews, collaborative coding, interview scheduling, and structured candidate evaluation.

The platform combines real-time video communication with an integrated coding workspace, enabling recruiters and candidates to interact during technical interviews.

## Features

- **Live Video Interviews:** Conduct remote interviews with video and audio controls, participant views, and screen-sharing support.
- **Collaborative Interview Workspace:** Access a coding editor alongside the live interview interface.
- **Multi-Language Coding Editor:** Write code in JavaScript, Python, and Java using the Monaco Editor.
- **Coding Problem Library:** Explore programming questions with problem descriptions, examples, constraints, and starter code.
- **Interview Scheduling:** Schedule interviews by selecting candidates, interviewers, dates, and time slots.
- **Authentication and User Roles:** Manage user access with Clerk authentication and candidate/interviewer roles.
- **Interview Management:** View scheduled interviews and manage interview status.
- **Candidate Feedback:** Record interviewer comments and numerical ratings for post-interview evaluation.
- **Interview Recordings:** Access the recordings interface for reviewing past interview sessions.
- **Responsive Interface:** Navigate the application through a modern interface built with Tailwind CSS and reusable UI components.

## Tech Stack

| Category | Technologies |
|---|---|
| Frontend | Next.js 14, React 18, TypeScript |
| Styling | Tailwind CSS, shadcn/ui |
| Authentication | Clerk |
| Video Infrastructure | Stream Video SDK |
| Database and Backend | Convex |
| Code Editor | Monaco Editor |
| UI Icons | Lucide React |
| Date Handling | date-fns |

## Architecture Overview

- **Frontend:** Next.js and React provide the interview dashboard, scheduling interface, video meeting room, and coding workspace.
- **Authentication:** Clerk manages sign-in and user identity.
- **Video Communication:** Stream Video SDK provides real-time interview calls and meeting controls.
- **Data Layer:** Convex stores user profiles, interview schedules, interview status, and interviewer feedback.
- **Coding Workspace:** Monaco Editor provides syntax-aware editing for supported programming languages.

## Getting Started

### Prerequisites

Install the following:

- Node.js and npm
- A Clerk application
- A Convex deployment
- A Stream Video application

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/PairVanta.git
cd PairVanta
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env.local` file in the project root:

```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=

CONVEX_DEPLOYMENT=
NEXT_PUBLIC_CONVEX_URL=

NEXT_PUBLIC_STREAM_API_KEY=
STREAM_SECRET_KEY=
```

Obtain the credentials from your Clerk, Convex, and Stream dashboards. Keep secret keys private and never commit `.env.local` to GitHub.

### 4. Start Convex

In a terminal at the project root, run:

```bash
npx convex dev
```

Follow the prompts to configure the Convex deployment and ensure its environment variables are available to the application.

### 5. Start the development server

Open another terminal and run:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Project Structure

```text
PairVanta/
├── convex/
│   ├── schema.ts
│   ├── interviews.ts
│   ├── users.ts
│   └── comments.ts
├── public/
├── src/
│   ├── actions/
│   ├── app/
│   ├── components/
│   │   ├── CodeEditor.tsx
│   │   ├── MeetingRoom.tsx
│   │   ├── MeetingModal.tsx
│   │   └── CommentDialog.tsx
│   ├── constants/
│   ├── hooks/
│   └── lib/
├── package.json
└── README.md
```

## Future Enhancements

- Execute code securely in a sandboxed environment.
- Add automated test-case evaluation and execution results.
- Introduce customizable coding assessments and difficulty levels.
- Generate detailed candidate scorecards and assessment reports.
- Add interview analytics and hiring pipeline insights.

## Purpose

PairVanta aims to bring video communication, coding assessments, and candidate evaluation into a unified technical interviewing workflow.

**PairVanta — Better technical interviews, one session at a time.**