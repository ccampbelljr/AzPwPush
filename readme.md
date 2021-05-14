# AzPWPush

AzPwPush is a password push tool that can be used to generate URLs with a one-time password. Use cases are sharing temporary credentials or validating someone's access.

It's possible to use both generated passwords, or self-entered passwords.

## How it works

When deploying this function to Azure, the function will have 2 URLS

/Create - Creates a unique password and URL. Can either type in a password and it will create a URL, or click Create button and it will generate one using the SimplePass API plus 2 extra random characters

/Get - allows you to retrieve the password. The password will also immediately be destroyed, invalidating the URL for future use.

A Cleanup function runs every hour to clean up the old password files. This is done based on the Maximum Age.
