# Project Title

Python Lambda function to automatically download Papa Johns reports and email.

## Getting Started

included in the repository is the lambda code (Lambda.py) to download reports, parse them and send them to an email. 

### Packages required
The code requires additional python3 packages Robobrowser, boto3 and email. However they have been packages in the zip file in the repository so you just need to upload the zip file to aws lambda to run the function.

## Parameters

EmailPassword: Encrypted password for the email senders email address.

EmailRecipient: Receiver of the report email.

EmailSender: Senders email address.

LoginEmail: New Relice Email

LoginPassword: Encrypted New Relic Password

AccountId: New relic client account id

smtphost: Smtphost for desired email service.

smtpport: Smtp Port

urlappend: List of reports characters that are going to be downloaded. default value is week,days,months which downloads all three files.
default: week,days,months

## Installation.

1. Create a lambda function with Python 3.6 compiler and a role having access to KMS.
2. Upload package.
3. Create parameters as environment variables and their values.
4. Paste "lambda.lambda_handler" in handler without quotes.
5. Save and test the function. 

## Encrypting parameters
To encrypt paramters use aws cli. Example:

aws kms encrypt --key-id 1234abcd-12ab-34cd-56ef-1234567890ab --plaintext TextToEncrypt --output text --query CiphertextBlob | base64 --decode > ExampleEncryptedFile

You will have encrypted string in the file ExampleEncryptedFile

