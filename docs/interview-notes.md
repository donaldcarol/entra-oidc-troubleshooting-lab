# Interview Notes

## What this lab demonstrates
- OpenID Connect authentication with Microsoft Entra ID
- Authorization Code flow concepts
- Local session creation after authentication
- Delegated access token acquisition for a downstream API
- Troubleshooting across identity, session and token boundaries

## Key distinctions
- ID token: used by the client application to identify the signed-in user
- Access token: used to access protected APIs
- Authentication: proving who the user is
- Authorization: determining what the user or application can access

## Important lessons learned
- Successful login does not automatically mean successful API authorization
- Token audience must match the target API
- Session handling issues can look like authentication issues
- Many IAM issues are caused by configuration mismatches rather than platform failure
