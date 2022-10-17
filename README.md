# New Branch Protection and Notification

## GitHub set up actions:
- Create Organization
- set up authentication (MFA)
- create access token
- create an Organization level webhook to send payload to an external URL upon "repositories" event

## Web Server or Web Service
- create a web server to listen on a specific URL (above) and process incoming HTTP POST (event)
  - Could use AWS Lambda or AWS API Gateway as well

## Event handler logic (based upon Zack Koppert(GitHub) Auto-branch-protect):
- If the HTTP Post is valid (has JSON), process its payload
- make sure the access token exported as an environment variable
  - If "repository created" event found
    - update protection rules on the "main" branch
    - create new issue assigned to the user id that created the repositiry
    - in the issue decription, mention the repo creator, following @mention notation
