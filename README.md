# blog
 
## Authorization. 
1. User enters their log in credentials(typicall username/password).
2. The server verifies the credentials are corret and generates a serssion object that is then stored in the database.
3. The server sends the client a sessionID - not the session object itself. which is stored as a cookie on the browser. 
4. On all future requests, the session ID is included as an HTTP header and, if verified by the database, the request proceeds. 
5. Once the user logs out of an application, the session ID is destroyed by both the client and the server. 
6. If the user later logs in again, an new session ID is generated and stored as a cookie on the client. 

Session ID  - this is when the user sends in username/password and an unique ID is created using base64 encoding. only works from the browser the client is calling in from.
Token based - this is also stateless. This will form a token using all information about a client. 
This can also allow for multipel frontends calling into our server and still maintian the same user. Ususally stored in cookie. httpOnly and Secure cookie flag. genrates one token per user. 
Token does not expire, but the functionality can be added. 

login: http://127.0.0.1:8000/api/v1/rest-auth/login/
logout: http://127.0.0.1:8000/api/v1/rest-auth/logout/
password reset: http://127.0.0.1:8000/api/v1/rest-auth/password/reset
Passwrod Reset confirm: http://127.0.0.1:8000/api/v1/rest-auth/password/reset/confirm.