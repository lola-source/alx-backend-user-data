# 0x03-user_authentication_service

In the industry, you should not implement your own authentication system and use a module or framework that doing it for you (like in Python-Flask: Flask-User). Here, for the learning purpose, we will walk through each step of this mechanism to understand it by doing.

[0. User model](https://github.com/lola-source/alx-backend-user-data/blob/master/0x03-user_authentication_service/user.py)
In this task you will create a SQLAlchemy model named User for a database table named users (by using the mapping declaration of SQLAlchemy).

The model will have the following attributes:
id, the integer primary key
email, a non-nullable string
hashed_password, a non-nullable string
session_id, a nullable string
reset_token, a nullable string

[1. create user](https://github.com/lola-source/alx-backend-user-data/blob/master/0x03-user_authentication_service/db.py)
In this task, you will complete the DB class provided below to implement the add_user method.

[2. Find user](https://github.com/lola-source/alx-backend-user-data/blob/master/0x03-user_authentication_service/db.py)
In this task you will implement the DB.find_user_by method. This method takes in arbitrary keyword arguments and returns the first row found in the users table as filtered by the method’s input arguments. No validation of input arguments required at this point.

Make sure that SQLAlchemy’s NoResultFound and InvalidRequestError are raised when no results are found, or when wrong query arguments are passed, respectively.

[3. update user](https://github.com/lola-source/alx-backend-user-data/blob/master/0x03-user_authentication_service/db.py)

In this task, you will implement the DB.update_user method that takes as argument a required user_id integer and arbitrary keyword arguments, and returns None.

The method will use find_user_by to locate the user to update, then will update the user’s attributes as passed in the method’s arguments then commit changes to the database.

If an argument that does not correspond to a user attribute is passed, raise a ValueError.

[4. Hash password](https://github.com/lola-source/alx-backend-user-data/blob/master/0x03-user_authentication_service/auth.py)
In this task you will define a _hash_password method that takes in a password string arguments and returns bytes.

The returned bytes is a salted hash of the input password, hashed with bcrypt.hashpw.
