 1. **Google OAuth Middleware Service** (google.makedev.com.au)

This PHP-based service handles:
- **Secure API token authentication** - Only authorized requests from team.makeweb.com.au
- **Google OAuth flow** - Complete OAuth2 implementation with state validation
- **Google Drive operations** - Create folders, list folders
- **Token storage** - Encrypted token storage with refresh capability
- **CORS support** - Properly configured for cross-origin requests

Key features:
- Modular architecture with separate classes for Security, Auth, Drive operations
- Encrypted token storage
- Automatic token refresh
- RESTful API endpoints
- Comprehensive error handling

## 2. **Team MakeWeb Integration** (JavaScript)

This provides:
- **GoogleDriveIntegration class** - Easy-to-use client for the middleware
- **WizardGoogleDriveStep class** - Drop-in wizard step for your existing wizard
- **Automatic auth flow** - Handles OAuth popup and completion detection
- **Folder creation UI** - Complete form with parent folder selection

## Setup Instructions:

### For google.makedev.com.au:

1. **Install dependencies:**
```bash
composer install
```

2. **Set environment variables:**
```bash
GOOGLE_CLIENT_ID=your_client_id
GOOGLE_CLIENT_SECRET=your_client_secret
TEAM_MAKEWEB_API_TOKEN=your_secure_token
ENCRYPTION_KEY=your_32_char_encryption_key
```

3. **Configure Google OAuth:**
   - Add `https://google.makedev.com.au/oauth/callback` as redirect URI in Google Console
   - Enable Google Drive API

4. **Set up Apache/Nginx** to route all requests to index.php

### For team.makeweb.com.au:

1. **Include the JavaScript files** in your wizard
2. **Set the API token** in GoogleDriveIntegration
3. **Add the Google Drive step** to your wizard flow

## Security Features:

- ✅ API token validation for all requests
- ✅ CORS protection with allowed origins
- ✅ OAuth state validation to prevent CSRF
- ✅ Encrypted token storage
- ✅ Automatic token refresh
- ✅ Input validation and sanitization

## Future Expansion:

The architecture supports easy addition of:
- Google Docs creation
- Google Sheets integration
- Calendar operations
- Any other Google API services

The modular design means you can add new endpoints like:
- `/docs/create`
- `/sheets/create`
- `/calendar/event`

