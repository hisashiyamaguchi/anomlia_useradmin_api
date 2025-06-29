# Let's manage your Anomali users with API
The objective of the RM is to get started Anomali user administration with API within 5min.
<br>
<br>

## Prerequisite
You have some level of experiences using Postman, and Postman client has already installed on your laptop. You also has already sign-up Anomali platform as organization admin and can grab your API key.
<br>


## Hands-on
Launch your Postman client, and set your API credentials on your environments. You can grab your username and API key on the Anomali UI portal.
<br>
<div align="center">
<img src="./images/API Key.png" width=50%>
</div>
<br>
<br>

<br>
<div align="center">
<img src="./images/Postman Environment.png" width=50%>
</div>
<br>
<br>

Send a POST request to `https://api.threatstream.com/api/v1/orgadmin/` so that you can grab all users that has been signed-up your Anomali organization. Grab the user id that you want to force password change. Here comes a sample curl command. 
```
curl --location --request GET 'https://api.threatstream.com/api/v1/orgadmin/' \
--header 'Authorization: apikey anomali_nttdocomo@anomali.com:xxxx' \
--header 'Content-Type: application/json' \
--data '{
    "must_change_password": true
}'
```
<br>
<div align="center">
<img src="./images/Postman User List.png" width=50%>
</div>
<br>

Send a PATCH request to `https://api.threatstream.com/api/v1/orgadmin/{user_id}/` so that you can force password change for the user. Here comes a sample curl command. 
```
curl --location --request PATCH 'https://api.threatstream.com/api/v1/orgadmin/64773/' \
--header 'Authorization: apikey anomali_nttdocomo@anomali.com:xxxx' \
--header 'Content-Type: application/json' \
--data '{
    "must_change_password": true
}
```
<br>
<div align="center">
<img src="./images/Postman Force Password Change.png" width=50%>
</div>
<br>

Go Anomali UI portal and check the user status. You can see the user must change the password.
<br>
<div align="center">
<img src="./images/User Admin.png" width=50%>
</div>
<br>
<br>
<br>

# Issue Reporting
If you have found a bug or if you have updates request, please report them at this repository issues section.