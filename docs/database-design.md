COCONUT X

Database Design Specification

Version 1.0 - MVP

1. Database Technology

Primary database: PostgreSQL through Supabase.

All sensitive operations must be validated on the server.

2. Database Tables

2.1 users

Stores user profiles.

Fields:

- id: UUID, primary key
- telegram_id: Unique Telegram user identifier
- username: Unique public username
- display_name: Public display name
- avatar_url: Profile image location
- bio: Optional biography
- preferred_language: User language
- role: user or admin
- status: active, suspended or deleted
- created_at: Creation timestamp
- updated_at: Last update timestamp

2.2 categories

Stores challenge categories.

Fields:

- id: UUID, primary key
- name: Category name
- slug: Unique category identifier
- is_active: Boolean
- created_at: Timestamp

2.3 challenges

Stores user-created challenges.

Fields:

- id: UUID, primary key
- creator_id: Reference to users
- category_id: Reference to categories
- title: Challenge title
- description: Challenge description
- rules: Participation rules
- cover_image_url: Optional image location
- status: draft, active, completed or removed
- starts_at: Start time
- ends_at: Participation deadline
- created_at: Timestamp
- updated_at: Timestamp

2.4 participants

Connects users to challenges.

Fields:

- id: UUID, primary key
- challenge_id: Reference to challenges
- user_id: Reference to users
- joined_at: Timestamp
- status: joined, withdrawn or completed

Constraint:

- A user can join each challenge only once.

2.5 submissions

Stores participant submissions.

Fields:

- id: UUID, primary key
- challenge_id: Reference to challenges
- user_id: Reference to users
- content_text: Optional text
- media_url: Optional media location
- status: pending, published, rejected or removed
- created_at: Timestamp
- updated_at: Timestamp

2.6 votes

Stores votes.

Fields:

- id: UUID, primary key
- submission_id: Reference to submissions
- voter_id: Reference to users
- created_at: Timestamp

Constraints:

- One vote per user per submission.
- Prevent duplicate votes using a database unique constraint.
- Validate voting permissions on the server.
- Prevent users from voting where challenge rules prohibit it.

2.7 reports

Stores user reports.

Fields:

- id: UUID, primary key
- reporter_id: Reference to users
- target_type: user, challenge or submission
- target_id: Target record identifier
- reason: Report reason
- status: pending, reviewed or dismissed
- created_at: Timestamp
- reviewed_at: Optional timestamp

2.8 invitations

Tracks invitations.

Fields:

- id: UUID, primary key
- inviter_id: Reference to users
- invite_code: Unique invitation code
- invited_user_id: Optional reference to users
- created_at: Timestamp
- accepted_at: Optional timestamp

2.9 admin_audit_logs

Records important administrative actions.

Fields:

- id: UUID, primary key
- admin_id: Reference to users
- action: Action description
- target_type: Target type
- target_id: Target identifier
- created_at: Timestamp

3. Relationships

- One user can create many challenges.
- One category can contain many challenges.
- One challenge can have many participants.
- One user can participate in many challenges.
- One challenge can contain many submissions.
- One submission can receive many votes.
- One user can cast many votes.
- One user can create many reports.
- One user can invite other users.
- Administrative actions must be recorded in audit logs.

4. Data Integrity

- Use UUID primary keys.
- Enforce foreign key relationships.
- Enforce unique usernames.
- Enforce unique Telegram identifiers.
- Prevent duplicate participation.
- Prevent duplicate votes.
- Validate challenge deadlines.
- Prevent unauthorized modifications.
- Use database transactions for critical operations.

5. Security and Access Control

- Enable Row Level Security (RLS).
- Users can edit only their own permitted profile fields.
- Users cannot modify their own roles.
- Users cannot directly change vote totals.
- Administrative actions require server-side authorization.
- Never expose database service-role keys to clients.
- Restrict access to private user information.

6. Media Storage

Use Supabase Storage for:

- Profile pictures
- Challenge cover images
- Submission images

Requirements:

- Validate file types.
- Limit file sizes.
- Generate safe storage paths.
- Restrict unauthorized uploads and downloads.
- Do not store large media files directly in PostgreSQL.

7. Performance

- Index frequently queried fields.
- Add indexes for challenge status and deadlines.
- Add indexes for user IDs and challenge IDs.
- Paginate challenge and submission lists.
- Avoid loading unnecessary user data.
- Optimize leaderboard queries.

8. Future Expansion

The database should allow future additions:

- More languages
- Achievement systems
- Advanced rankings
- Moderation tools
- TON payment integration
- Additional challenge formats

9. Important Rule

The database must be designed for data integrity, security, scalability and maintainability.

No fake users, fake votes or fake participation statistics are permitted.
