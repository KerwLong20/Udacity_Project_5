Resource Group
Resource Group Name: fms
2. SQL Database
DB name: fmsdb
Server: fmsserver1.database.windows.net
DB region: us-east
Admin login: cmsadmin
Admin password: CMS4dmin
Resource group: fms
DB workload env: Development
DB compute + storage: DTU - Basic
Press the "Next: Networking" button, then select "Public Endpoint", and set both of the Firewall rules that appear to "Yes".
Set everything else to default
Run SQL queries in sql_scripts/ directory after completion, starting from the users table. Don't forget to take screenshots.
3. Storage Account
Resource group: fms
Storage account name: fmsimages (needs to be unique)
Advanced - Allow enabling anonymous access on individual containers: Enable
Advanced - Access tier: Cool
Network access: Enable public access from all networks (the default)
Create container named "images". Set its access level to Container.
From Security + networking > Access keys:
Blob Storage key: 0Uz437lhqkXxigzFlbiOrbTVQSeHo/ATIYzFrZdgOkDn2zEzjQ3gH63EzVH08TuTd0Q0jJFaQX6I+AStU4zf3g==

4. Microsoft Entra ID
4.1. App Registration
Name: fmsEntraID
Who can use? "Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)"
4.2. Secret Creation
Secret description: test
Secret Key: 10257b26-789e-4c6a-af01-62511cdb0fe2
Client Secret: H1s8Q~TW~sIrcQDCB6wxsdJrC8GSAZFZeRnZdck1
Application (client) ID: e738d0b0-5190-4d36-90e2-b6bc8ed5c0c9

Application
Name: udacityfms.azurewebsites.net
Runtime stack: Python 3.10
Pricing Plan: Free F1
If you are getting a "Validation failed for a resource" error, pick a different region.
After creation:

Settings -> Environment variables - Add the following variables (sample values are included, replace them with your values):
BLOB_ACCOUNT: fmsimages
BLOB_CONTAINER: images
BLOB_STORAGE_KEY: 0Uz437lhqkXxigzFlbiOrbTVQSeHo/ATIYzFrZdgOkDn2zEzjQ3gH63EzVH08TuTd0Q0jJFaQX6I+AStU4zf3g==

SQL_SERVER: fmsserver1.database.windows.net
SQL_DATABASE: fmsdb
SQL_USER_NAME: cmsadmin
SQL_PASSWORD: CMS4dmin
CLIENT_SECRET: H1s8Q~TW~sIrcQDCB6wxsdJrC8GSAZFZeRnZdck1
SECRET_KEY: 10257b26-789e-4c6a-af01-62511cdb0fe2
CLIENT_ID: e738d0b0-5190-4d36-90e2-b6bc8ed5c0c9
Deployment Center
Source: GitHub
Pick the repo that contains the starter files.
6. Setting up OAuth2
At this point, your application should already be running. You should already be able to log in with username admin and password pass and you can create new posts or update existing ones.

The next part is getting the OAuth2 login to work.

Go to Microsoft Entra ID > App Registrations, click on the App Registration created earlier, and then pick Authentication from the left sidebar.

6.1. Microsoft Entra ID - Authentication - Add a Platform - Web
Redirect URIs: https://[IP ADDRESS FROM VM or WEB APP ADDRESS]/getAToken
logout URL: https://[IP ADDRESS FROM VM or WEB APP ADDRESS]/login
