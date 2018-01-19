<!-- Answers to the Short Answer Essay Questions go here -->
# 1 Describe Middleware, Sessions (as we know them in express), bcrypt and JWT.
Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.

Middleware functions can perform the following tasks:

* Execute any code.
* Make changes to the request and the response objects.
* End the request-response cycle.
* Call the next middleware function in the stack.
* If the current middleware function does not end the request-response cycle, it must call next() to pass control to    the next middleware function. Otherwise, the request will be left hanging.

An Express application can use the following types of middleware:

* Application-level middleware
* Router-level middleware
* Error-handling middleware
* Built-in middleware
* Third-party middleware
* You can load application-level and router-level middleware with an optional mount path. You can also load a series    of middleware functions together, which creates a sub-stack of the middleware system at a mount point.
# 2 What does bcrypt do in order to prevent attacks?
bcrypt is a password hashing function. Besides incorporating a salt to protect against rainbow table attacks, bcrypt is an adaptive function: over time, the iteration count can be increased to make it slower, so it remains resistant to brute-force search attacks even with increasing computation power.
# 3 What are the three parts of the JSON Web Token?
* Header. The header typically consists of two parts: the type of the token, which is JWT, and the hashing algorithm being used
* Payload. The second part of the token is the payload, which contains the claims. Claims are statements about an entity (typically, the user) and additional metadata.
* Signature.
To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that. 