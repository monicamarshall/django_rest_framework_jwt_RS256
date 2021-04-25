# django_rest_framework_jwt_RS256

This is a demo project of the django-rest-framework-jwt by JPadilla. 

Documentation for django-rest-framework-jwt is available at:

https://github.com/jpadilla/django-rest-framework-jwt
https://github.com/jpadilla/django-rest-framework-jwt/issues/484
https://jpadilla.github.io/django-rest-framework-jwt/

This library is unmaintained and is used by the newer framework djangorestframework-simplejwt at:

https://github.com/jazzband/django-rest-framework-simplejwt
The documentation for the maintained version is at:
https://django-rest-framework-simplejwt.readthedocs.io/en/latest/

The demo projects shows 3 basic RS256 jwt capabilities:
1. Obtain a token ( with valid username and password ).  The url for obtaining a token (server running at port 8088 ): http://localhost:8088/users/api-token-auth/
2. Refresh the token ( using the access token obtained in step 1 ) The url for obtaining a token (server running at port 8088 ): http://localhost:8088/users/api-token-refresh/
3. Verify token ( using the access token from step 1 or step 2 ) The url for obtaining a token (server running at port 8088 ): http://localhost:8088/users/api-token-verify/

Prerequisite for the obtaining a token:
The username and password for the user requesting a new token must already exist in the django Users database.  For this, run the 'python manage.py createsuperuser' command
to create a user first.

The project also offers 2 services:
1. The hello service ( returns the message Hello )
2. The students service ( view/update/delete/modify students).


Current unresolved capabilities:
The framework will authorize access to the hello and student service in curl commands when the RS256 token is set in the Authorization Bearer header of the request.
The framework DOES NOT authorize access to the hello and student services when when requests for the hello and students resources are submitted via browser.  
An existing flaw in the framework does not authorize users when accessing the endpoints via URL in a web page:

1. http://localhost:8088/hello/
2. http://localhost:8088/students/
3. http://localhost:8088/students/1




