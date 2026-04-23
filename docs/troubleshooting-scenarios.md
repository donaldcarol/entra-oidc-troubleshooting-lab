# Troubleshooting Scenarios

## 1. Redirect URI mismatch
**Symptom:** Authentication fails before returning to the application.  
**Cause:** The redirect URI configured in the application does not exactly match the one configured in Microsoft Entra ID.  
**Fix:** Ensure an exact match, including scheme, host, port and path.

## 2. Invalid client secret
**Symptom:** Token acquisition fails with an invalid_client error.  
**Cause:** The application sends an incorrect client secret, often because the secret ID was used instead of the secret value.  
**Fix:** Create a new client secret if needed and use the secret value in the application configuration.

## 3. Session not persisted
**Symptom:** The user signs in successfully but is repeatedly redirected back to login.  
**Cause:** The local application session is not stored or not restored correctly.  
**Fix:** Verify session middleware configuration, cookies and session lifecycle.

## 4. Access token has wrong audience
**Symptom:** The API rejects the token even though authentication succeeded.  
**Cause:** The token was issued for the client application rather than the downstream API.  
**Fix:** Request a token for the correct API scope and verify the `aud` claim.

## 5. Missing scope or consent
**Symptom:** Authentication works, but the application cannot acquire or use an API access token.  
**Cause:** The downstream API scope was not granted, consented to or requested correctly.  
**Fix:** Expose the API scope, grant consent where needed and request the correct delegated scope.
