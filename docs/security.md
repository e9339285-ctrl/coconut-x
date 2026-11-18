# COCONUT X - Security Policy

## 1. Authentication
- Validate Telegram initData on the server.
- Never trust client-side authentication data.
- Protect user sessions.

## 2. API Security
- Apply rate limiting.
- Validate all incoming requests.
- Prevent unauthorized access.
- Use secure error handling.

## 3. Database Security
- Enable Row Level Security (RLS).
- Apply least-privilege access.
- Protect private user information.
- Never expose service role keys.

## 4. Voting Security
- Prevent duplicate votes.
- Validate voting permissions on the server.
- Store votes securely.
- Protect ranking calculations from manipulation.

## 5. File Upload Security
- Validate file types and sizes.
- Reject dangerous file formats.
- Restrict upload permissions.
- Protect stored user content.

## 6. Secrets Management
- Never commit API keys or passwords.
- Store secrets in secure environment variables.
- Rotate compromised credentials.

## 7. Monitoring
- Record important security events.
- Monitor suspicious activity.
- Prepare database backups.
- Maintain an incident response plan.

## 8. Development Rules
- Review code before deployment.
- Test authentication and authorization.
- Test database access policies.
- Never claim the platform is completely hack-proof.
