Setup Instructions:
For google.makedev.com.au:

Install dependencies:

bashcomposer install

Set environment variables:

bashGOOGLE_CLIENT_ID=your_client_id
GOOGLE_CLIENT_SECRET=your_client_secret
TEAM_MAKEWEB_API_TOKEN=your_secure_token
ENCRYPTION_KEY=your_32_char_encryption_key

Configure Google OAuth:

Add https://google.makedev.com.au/oauth/callback as redirect URI in Google Console
Enable Google Drive API


Set up Apache/Nginx to route all requests to index.php

For team.makeweb.com.au:

Include the JavaScript files in your wizard
Set the API token in GoogleDriveIntegration
Add the Google Drive step to your wizard flow

Security Features:

✅ API token validation for all requests
✅ CORS protection with allowed origins
✅ OAuth state validation to prevent CSRF
✅ Encrypted token storage
✅ Automatic token refresh
✅ Input validation and sanitization

Future Expansion:
The architecture supports easy addition of:

Google Docs creation
Google Sheets integration
Calendar operations
Any other Google API services

The modular design means you can add new endpoints like:

/docs/create
/sheets/create
/calendar/event
