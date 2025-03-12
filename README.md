# try2

This API consists of two microservices: the Authentication Service and the Product Service. 

The Authentication Service, running on http://localhost:4000/, handles user registration, login, and authentication using JWT (JSON Web Token). Users can register by sending their username and password to the /api/register endpoint, where the password is securely hashed before being stored. To log in, users send their credentials to /api/login, and if authentication is successful, the server responds with a JWT token. This token must be included in the Authorization header when accessing the protected route at /api/protected. If the token is valid, the user gains access; otherwise, the request is denied.
The Product Service, running on http://localhost:5000/, manages product data. It provides two endpoints: /api/products (a GET request to retrieve all products) and a POST request to add a new product. When adding a product, users must send a JSON request body containing the product name and price. The service then assigns a unique ID to the product and stores it in an in-memory array.
These two microservices work independently, making the system modular and scalable. The Authentication Service secures user access, while the Product Service handles product management without requiring authentication. This separation of concerns allows for easier maintenance and potential expansion, such as integrating a database for persistent storage or deploying the services
