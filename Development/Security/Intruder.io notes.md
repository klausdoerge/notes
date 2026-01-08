
Intruder testing

Setup intruder on the updated owasptest application
create a schema for the api and add to intruder. We should test, that none of the APIs are availagle, unless the user has signed in.

Test the endpoints for sana which gives an oauth token

API scana - ask Dom if she knows how to extract a json or yaml file from swagger to upload to Intruder

Reporting
Figure out how to get status reports from Intruder, so it is continously monitored.
Perhaps we should have a sec account to gather all reports from this and azure app insigts, so evertyhing is collected centrally?

Create a todo-list of any security issues that might be reported.

Can intruder test if our sso integration is secure?

Hosting App Insights

app:
    Uptime
    Error log
    Performance
    Is it possible to gain insight/analytics on amount of users etc?

sql:
    Audit logs

sys:
    processing performance and load
    memory-load

Novo
    Always ensure that production slots are not running on the Umbraco instance
    