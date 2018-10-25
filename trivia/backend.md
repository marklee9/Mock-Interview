# Backend Questions

Design amazon's "Customers who bought this item also bought" recommendation system.

<br/>

___

<br/>

What is ORM?

    ORM stands for Object Relational Mapping. ORM is a programming technique for 
    converting data between incompatible type systems using object-oriented programming 
    languages. This creates, in effect, a "virtual object database" that can be used from within the programming language.

<br/>

___

<br/>

What is RESTful?

    REST stands for Representational State Transfer. It is a set of design principles for making 
    network communication more scalable and flexible. 
 
    It provides a way of mapping HTTP verbs ( get, post, put, delete) and
    CRUD actions (create, read, update, delete) together.

<br/>

___

<br/>

What is CSRF (Cross-site request forgery) Attack and how do you prevent it?

    CSRF attack is a type of malicious exploit of a website where unauthorized commands are 
    transmitted from a user that the web application trusts.

How do you prevent it?

    Ex. By giving logged in user a secure token, and by checking if token before executing any action
    if it matches with the token through a hidden input.


