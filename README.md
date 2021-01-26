# Objectives
The objective of the project is to monitor a user's email account every ten minutes for new emails. If there are new emails, they should be marked read and all the attachments should be downloaded in the local system. 

After the attachements are downloaded on the local system, they should be automatically uploaded to the user's dropbox account as well. 

# Steps for Execution
### Step 1 - Enable the Gmail API
 Go to [Python Quickstart](https://developers.google.com/gmail/api/quickstart/python) the first time you start the project. Using the 'Enable the Gmail API button, you can get the credentials on the local system. Specify the prroject name and other realted options. Also, authenticate the gmail account through which you want to start this project. Add these credentials to the working directory where the project is being developed. Using this credentials, we can add multiple users to access our project.

### Step 2 - Install the Google Client Library
Run the following command to install the library using pip:
``` python
pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib
```
### Step 3 - Authorize the user account 
From [Python Quickstart](https://developers.google.com/gmail/api/quickstart/python) copy the quickstart.py link to a file in the current working directory. Run this file, and complete the authentication process. A token.pickle file will be generated. 

### Step 4 - Download the files

Using the Gmail API, access the gmail account and obtain the emails. If an attachments exists, it is downloaded in a folder in the current working directory. Once all the emails are read and the attachments are downloaded, the next function is invoked, which will upload these attachements on dropbox. 

The project holds the scope, for filtering out emails that are sent on the weekends. The maximum size of the attachments that can be downloaded is also specified. 

Email monitoring can be performed on multiple accounts. This process is automated. The user has to specify the account name, email and password. The unique token would be generated for each of these accounts. 

The code can be found in class_gmail_api.py. automate_token.py contains the code for automating the process of obtaining token. 

### Step 5 - Upload the files

Using [Create Project](https://www.dropbox.com/developers/apps) option in dropbox, create a new project. Specify the scope for the project, and using the Generate Token button, get the token to access dropbox from your account. 

After, this is done install dropbox. 
 ```python
 pip install dropbox
 ```

The next step is to upload the files to the specified location.
