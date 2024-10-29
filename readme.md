Django Sample Project for Azure SSO


# Prerequisites
Install Python 3.12.x or later

Create Azure App with MS Azure Protal "App registrations".
These information from Azure App are required.
- Directory (tenant) ID (Overview)
- Application (client) ID (Overview)
- Client secret (Manage - Certificates & secrets)
- scopes (Manage - API permissions)
- redirect url (Manage - Authentication - Web Redirect URIs)

redirect url for this sample is:
http://localhost:8000/sso_login_callback/
(Can be vary depending on port. it is assumed that port will be 8000 for this sample.)

# Installation

#### Download source code
```
git clone https://github.com/shineum/py_mssso_sample.git
```

#### Set environment variables
copy sample.env to .env
fill in the required values


#### Setup vritual environment
```
python -m venv .venv
```

#### Activate vritual environment
For linux or macos
```
source ./.venv/bin/activate
```
For windows (cmd)
```
.\.venv\Scripts\activate.bat
```

#### Install modules
```
python -m pip install -r requirements.txt
```

#### init DB
```
python manage.py migrate
```

#### Run server
```
python manage.py runserver
```

# Test
Open browser and type in url
http://localhost:8000

According to the login status text will be different.
When you click sso login link, it will redirect to MS login page.
Login with ms account, then it will be back to redirect url.