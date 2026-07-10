# airline-analytics-snowflake

Things that did not run smoothly:
- copying from Notion
-
- devcontainer.json:
- there were some markdown texts that were not valid json (backticks, url, etc)
- some of the text had overflown outside of the code block so it was not part of the copied text. it omitten closing quotes, etc.
- I used Claude to help me fix the errors

- Because I already had the codespace active, I needed to learn how to update the codespace after changes to devcontaier.json
- by making changes in github and pulling into the codespace with "git pull" from the CLI in the codespace
- followed by  rebuilding the codespace (had to learn how to bring up the command pallette in code spaces

Getting this error:
An environment file is configured but terminal environment injection is disabled. Enable "python.terminal.useEnvFile" to use environment variables from .env files in terminals.
Fix:
Enable the VS Code Python terminal env-file feature:

Open your settings JSON:

Ctrl+Shift+P → Preferences: Open Settings (JSON)
Add this setting:
"python.terminal.useEnvFile": true

# Authentication
Initially, my authentication was based on username and password which I had maintained in the .env file. Later snowflake asked me to implement MFA for secure account access. WIth the activation of the MFA, 
I could not continue to use a username and password authentication for automation (I wouldn't be online at 2am to complete MFA!) so I had to change the authentication methode.
I have 2 options:
RSA key pair
or using a programatic access token (PAT) which has the disadvantage that it expires within 15 minutes and would need to be continuously renewed - although this could probably be reolved with a python script.
