# Authorization-Error-Multiple-Accounts
Check for the user being logged into multiple accounts

When a dialog box or sidebar first loads, a scriptlet that gets the effective user account email will run without an error and work correctly.  But when a subsequent google.script.run.myFunction call is made, that's when the authorization error occurs.  So, there is a way to use this information to check for the user being logged into multiple accounts.

Run a scriptlet when the dialog or sidebar loads, and put the user account email into a hidden HTML element.  Then when the dialog or sidebar loads, run an On Load function that makes a google.script.run.funcName call.  If the user is logged into multiple accounts, then the google.script.run.funcName call will fail and the failure handler will run.  This is how you can know if there will be an authorization error because of the user being logged into multiple accounts.

What you need to do in order to test the code, is to log into the wrong account first. So, log into an account, any Google account, that did NOT install the add-on or web app. Then log into the account that DID install the add-on / web app.

The email in the HTML tag should be an email of the default account. The default account is the account that you logged in to first.  Note the email being put into the HTML tag.  That email should be the email of the default account.
