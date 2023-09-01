## Cloudflare

Simple and functional email forwarding option. Currently i am able to run my root domain but still figuring out how to use subdomains. One way is to use zoho mail free plan for subdomains or improvmx email forwarding. But it's not required right now, so skipping it.

## Gmail as sending server

1. Setup 2FA on your gmail account, (aegis auth)
2. Generate an app password [here](https://myaccount.google.com/apppasswords)
3. Open Gmail and go to send mail as. 
4. A pop up would appear fill in the details as required a guide is given below

Set the Gmail SMTP server as the mail server for your forwarded alias. Change the values in fields to enter the following:

```yaml
SMTP Server: smtp.gmail.com
Port: 465
Username: Your Gmail account (the one you are logged in as)
Password: The generated Google App Password
```    

Now gmail can be used to send personalized emails.

