COCONUT X

Admin Panel and Moderation Specification

Version 1.0 - MVP

1. Purpose

The Admin Panel provides authorized administrators with tools to manage users, challenges, reports and platform safety.

2. Admin Dashboard

The dashboard should display:

- Total registered users
- Active challenges
- Completed challenges
- Pending reports
- Recent moderation actions
- Suspicious activity alerts

All statistics must come from real database records.

3. User Management

Administrators should be able to:

- Search users
- View public user profiles
- View account status
- Suspend accounts
- Restore suspended accounts
- Review reported users

Administrators must not be able to view user passwords or private authentication secrets.

4. Challenge Management

Administrators should be able to:

- View all challenges
- Search and filter challenges
- Review reported challenges
- Remove content that violates platform rules
- Restore content when appropriate
- Review challenge status

5. Submission Moderation

Administrators should be able to:

- Review reported submissions
- Remove prohibited content
- Reject submissions that violate challenge rules
- Restore incorrectly removed submissions
- Record moderation reasons

6. Report Management

The report system should support:

- User reports
- Challenge reports
- Submission reports
- Report categories
- Report status
- Moderator notes
- Review timestamps

Report statuses:

- Pending
- Under review
- Resolved
- Dismissed

7. Voting Abuse Monitoring

The system should help administrators identify:

- Unusual voting patterns
- Repeated suspicious activity
- Automated voting attempts
- Potential vote manipulation

Suspicious activity must be reviewed before penalties are applied.

8. Administrator Roles

Initial roles:

- Super Admin
- Moderator

Super Admin:

- Full administrative permissions
- Manage administrator access
- Manage platform settings

Moderator:

- Review reports
- Moderate challenges and submissions
- Apply permitted moderation actions

Use least-privilege access.

9. Audit Logs

Record important administrative actions:

- Administrator identity
- Action performed
- Target record
- Action reason
- Timestamp

Audit logs must be protected against unauthorized modification.

10. Security

- Require server-side authorization.
- Never trust frontend role information.
- Protect administrative endpoints.
- Apply rate limits.
- Log sensitive administrative actions.
- Require confirmation for destructive actions.
- Never expose service-role keys to the browser.

11. Admin Interface Design

Use the COCONUT X visual identity:

- Background: #10101C
- Neon pink: #FF63B5
- Turquoise: #54E7F0
- Purple: #A78BFA
- Soft orange: #FFAD82

The interface must be:

- Simple
- Responsive
- Mobile-friendly
- Easy to navigate
- Consistent with the main platform

12. MVP Scope

The first release includes:

- User search and account status
- Challenge moderation
- Submission moderation
- Report management
- Basic audit logs

Advanced analytics and automated moderation can be added later.

13. Important Principles

- Moderation decisions must be traceable.
- Users should be treated fairly.
- Administrators must have only the permissions they need.
- Fake statistics are prohibited.
- Critical actions must be logged.
