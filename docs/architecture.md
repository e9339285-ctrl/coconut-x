# COCONUT X
## Technical Architecture

### 1. Project Overview
COCONUT X is a global social challenge platform.

Users can:
- Create challenges
- Participate in challenges
- Submit content
- Vote on submissions
- Earn rankings
- Invite friends

### 2. Architecture
The first version uses a Serverless architecture.

Main technologies:

- Telegram Mini App: User interface
- Cloudflare Workers: Backend API
- Supabase: PostgreSQL database
- Supabase Auth: Authentication where appropriate
- Supabase Storage: File storage
- GitHub: Source code management

### 3. Initial Languages
- Persian
- English

The architecture must support additional languages.

### 4. Security
- Validate Telegram authentication data on the server.
- Protect secret keys.
- Apply rate limiting.
- Prevent duplicate votes.
- Enforce database access policies.
- Log important security events.

### 5. MVP Features
- User profiles
- Challenge creation
- Challenge participation
- Text and image submissions
- Voting
- Rankings
- User reporting
- Admin moderation

### 6. Future Development
- Independent website
- Android application
- iOS application
- Additional languages
- TON and Tonkeeper integration after security review

### 7. Initial Restrictions
- No paid competitions
- No cash prizes
- No private messaging
- No live streaming
- No large video uploads

### 8. Main Goal
Build a secure, scalable and globally accessible social challenge platform.
