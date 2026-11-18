
# COCONUT X
## Product Requirements Document (PRD)
### Version 1.0 - MVP

## 1. Product Vision
COCONUT X is a global social challenge platform where people create challenges, participate, share submissions, vote and compete through rankings.

The platform aims to make social competition simple, engaging and accessible worldwide.

## 2. Target Platforms
- Telegram Mini App for the initial release
- Mobile-friendly responsive interface
- Future independent website
- Future Android and iOS applications

## 3. Initial Languages
- Persian (Farsi)
- English

The system must support adding more languages later.

## 4. User Accounts
Users should be able to:
- Sign in through Telegram
- Create a public profile
- Choose a username
- Add a profile picture
- View their participation history
- View their rankings

Telegram authentication must be validated securely on the server.

## 5. Challenge System
Users should be able to:
- Create a challenge
- Add a title and description
- Select a challenge category
- Set participation rules
- Set a participation deadline
- View active and completed challenges
- Share challenge links

## 6. Participation System
Participants should be able to:
- Join an available challenge
- Submit text or images
- Edit or delete submissions when permitted by challenge rules
- View their submission status
- View other permitted submissions

## 7. Voting System
The platform should support:
- Voting on eligible submissions
- One valid vote per user per submission
- Server-side vote validation
- Duplicate vote prevention
- Suspicious voting detection
- Transparent voting results

## 8. Ranking System
The platform should provide:
- Challenge rankings
- User rankings
- Global leaderboard
- Category-based rankings

Ranking calculations must be performed and validated on the server.

## 9. Social Features
Initial social features:
- Share challenges
- Invite friends
- View public profiles
- Report inappropriate content

Private messaging is not included in the MVP.

## 10. Administration
Administrators should be able to:
- Review reported content
- Remove rule-breaking submissions
- Suspend abusive accounts
- Manage challenge categories
- Review suspicious voting activity

Administrative actions must be protected and logged.

## 11. MVP Limitations
The first version will not include:
- Paid competitions
- Cash prizes
- Cryptocurrency payments
- TON or Tonkeeper integration
- Private messaging
- Live streaming
- Large video uploads

## 12. Design Direction
The interface should be:
- Modern
- Professional
- Responsive
- Easy to understand
- Suitable for international users

Visual identity:
- Midnight background: #10101C
- Neon pink: #FF63B5
- Turquoise: #54E7F0
- Purple: #A78BFA
- Soft orange: #FFAD82

The design should be original and inspired by the atmosphere of modern premium entertainment interfaces.

## 13. Security Requirements
- Validate all authentication on the server.
- Enforce authorization for every protected action.
- Prevent duplicate voting.
- Apply rate limits.
- Validate uploaded files.
- Protect personal information.
- Keep secret keys outside the repository.
- Use database access policies.

## 14. Future Expansion
After the MVP is tested:
- Add more languages.
- Launch independent web access.
- Develop Android and iOS apps.
- Evaluate TON and Tonkeeper integration.
- Explore additional challenge formats.

## 15. Main Success Goal
Launch a secure and usable MVP, attract initial users, measure engagement and improve the platform based on real user feedback.
