Create Organization
set up authentication (MFA)
create an Organization level webhook to send payload to a GitHub App upon new repository created event
create a GitHub App to listen on a specific URL and process incoming HTTP Post
If the HTTP Post is valid, then process payload and update protection rules on the "main" branch and create new issue assigned to the user id that created the repositiry
