I created a program for online registration in hospitals, and also the output of the records for each hospital will be shown in Google Sheets. So if you want to use it and display all information to your own google sheets, I will write all steps to modify it for your personal usage.
**1. Set Google Sheets Api:**
   Create a project in the Google Cloud Console
  Go to the Google Cloud Console.
  Log in to your Google account.
  Click the menu icon in the upper left corner and select "Select project".
  Click the "Create project" button.
  Enter a name for the project (e.g. "VetClinicAppointments") and select an organization and location (if required).
  Click "Create".
**2. Enable APIs**
  From the left menu, select "Library".
  Find and enable the following APIs:
  Google Sheets API
  Google Drive API
**3. Create credentials to access the API**
  Go to "APIs & services" > "Credentials".
  Click "Create credentials" and select "Service account".
  Enter a name for the service account and click "Create and continue".
  Assign the "Editor" role to this account and click "Continue".
  Click "Done".
  In the list of service accounts, find the account you created and click on it.
  Go to the "Keys" tab, click "Add Key" and select "Create New Key".
  Select the JSON format and click "Create". The credentials file will be downloaded to your computer.
**4. Prepare a spreadsheet in Google Sheets**
  Go to Google Sheets and create a new spreadsheet.
  Copy the spreadsheet ID from the URL (the part after /d/ and before /edit).
  Share the spreadsheet with the service account email (from the JSON file). To do this, click "Share" in the upper right corner of the spreadsheet, enter the email and grant "Editor" access.

Also at the server.js file you should replace:
const CREDENTIALS_PATH = 'path/to/your/credentials.json';
const SPREADSHEET_ID = 'your_spreadsheet_id';

Furthemore download some libraries for Google Sheets integretaion: 
mkdir vet-clinic-appointments
cd vet-clinic-appointments
npm init -y
npm install googleapis
npm install --save @google-cloud/local-auth
