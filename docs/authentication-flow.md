COCONUT X

Authentication and User Session Specification

Version 1.0 - MVP

1. Authentication Method

The initial version uses Telegram Mini App authentication.

Users should not need a separate COCONUT X password.

2. Login Flow

1. The user opens COCONUT X through Telegram.
2. The Telegram Mini App provides initialization data.
3. The frontend sends the initialization data to the backend.
4. The backend validates the Telegram data using the official Telegram validation procedure.
5. The backend checks the authentication timestamp and rejects expired or invalid data.
6. The backend identifies the Telegram user.
7. The backend creates a new user profile or retrieves the existing profile.
8. The backend establishes a secure application session.
9. The user is redirected to the home screen.

3. Server-Side Validation

- Never trust Telegram user information received directly from the frontend.
- Validate the initialization data on the backend.
- Verify the cryptographic signature.
- Verify the authentication timestamp.
- Reject invalid or expired authentication data.
- Protect the Telegram bot token.
- Never expose secrets in frontend code.

4. Session Management

- Use secure session management.
- Use short-lived access credentials where applicable.
- Support session expiration.
- Support logout.
- Provide a secure session renewal mechanism.
- Revoke sessions when necessary.
- Never store sensitive authentication secrets in public storage.

5. User Account Creation

For a new user:

- Create a unique internal UUID.
- Store the verified Telegram user identifier.
- Assign the default user role.
- Create a public profile.
- Set the initial preferred language.
- Set the account status to active.

For an existing user:

- Retrieve the existing account.
- Update permitted profile information.
- Preserve the internal user identifier.
- Never allow the client to change privileged account fields.

6. Authorization

- Every protected backend operation must verify the user's identity.
- Users can modify only permitted information belonging to their own account.
- Only authorized administrators can access administrative operations.
- User roles must be controlled by trusted backend processes.
- Database access policies must enforce authorization.

7. Abuse Prevention

- Apply login and API rate limits.
- Reject malformed requests.
- Prevent replay of expired authentication data.
- Log suspicious authentication attempts.
- Avoid exposing sensitive information in error messages.

8. Privacy

- Collect only information necessary for platform functionality.
- Do not expose private Telegram information publicly.
- Allow users to manage permitted profile information.
- Establish an account deletion and data retention policy.

9. Error Handling

The application should handle:

- Invalid Telegram authentication
- Expired authentication data
- Network failures
- Suspended accounts
- Expired sessions
- Unauthorized requests

Errors must be clear and must not expose internal secrets.

10. Testing Requirements

Before launch, test:

- Valid Telegram authentication
- Invalid signatures
- Expired authentication data
- Repeated authentication attempts
- Session expiration
- Logout
- Unauthorized access
- Suspended accounts
- Role escalation attempts

11. Security Principle

Authentication and authorization decisions must be enforced on the backend.

The frontend must never be treated as a trusted security boundary.
