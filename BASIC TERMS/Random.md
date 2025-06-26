🔌 What is a Port?
        A port is a virtual number (0–65535) used to identify specific applications or services on a device in a network.

        Think of it as a door number on your computer, while the IP address is the street address.

    🌐 Why Ports Are Needed:
        Your computer runs many apps (browser, server, email, etc.) — ports help send data to the right one.

        Without ports, the system won’t know which app to deliver network data to.

    🖥️ What is a Server?
        A server is a software or device that provides services, data, or resources to clients (like browsers or apps) over a network.

        In web dev, a server receives a request, processes it, and sends back a response (like HTML, JSON, etc.).

    🆚 Difference Between Server and Database

        🔹 Server	                                                                🔹 Database
        A program/system that handles requests and sends responses.	                    A system to store, manage, and retrieve data.
        Runs backend logic (e.g., authentication, API routes).	                        Stores user info, products, posts, etc.
        Example: Node.js, Express.js server.	                                        Example: MongoDB, MySQL, PostgreSQL.
        Talks to the database to fetch/update data.             	                    Doesn't handle client requests directly.

        👉 Think of the server as the manager, and the database as the storage room.

     💻 What is localhost?

        localhost = Your own computer acting as a server for testing purposes.
        It's mapped to the IP address 127.0.0.1.
        When you go to http://localhost:3000, you’re accessing a server running on your PC, on port 3000.

        💡 Used for development — like running React or Node apps locally before deploying.

    🔌 API (Application Programming Interface)

        A set of rules that lets different software applications communicate.
        Think of it as a waiter that takes your request to the kitchen and brings back your food.
        Example: When you call GET /weather, the API fetches weather data from the server.

     🌐 HTTP vs HTTPS

        HTTP	                                                    HTTPS (Secure)
        Stands for HyperText Transfer Protocol              	HyperText Transfer Protocol Secure
        No encryption                                       	Data is encrypted via SSL/TLS
        Vulnerable to attacks                               	Safer (uses certificates)
        Port 80	                                                    Port 443

        HTTPS is essential for login forms, payments, etc.



    🖥️ Localhost        vs                      127.0.0.1

        Hostname (like a nickname)	            IP address of local machine
        Resolved by OS                      	Actual IP
        Both refer to your own computer	         Same in most cases,     but localhost can be mapped differently (e.g., in DNS)
           
     🌐 Port         vs                        IP

        IP (Internet Protocol)	                Port Number
        Identifies device on a network	I       dentifies specific process/service on that device
        Like a house address	                Like a specific room in that house
        E.g., 192.168.1.5	                    E.g., :3000, :80 (port 80 = HTTP)

        🔐 SSL          vs                           TLS

        SSL (Secure Sockets Layer)              	TLS (Transport Layer Security)
        Older protocol	                            Newer, more secure version of SSL
        Vulnerable to attacks                   	Replaces SSL in modern systems
        Now considered obsolete	                    Used in HTTPS for encryption

        🔑 Purpose: Both encrypt data sent over the internet (e.g., login forms, payments).

    📄 Certificates (SSL/TLS Certificates)

            Digital proof that a website is real and secure.
            Issued by a Certificate Authority (CA).
            Contains:
            Website's public key 🔑
            Website domain name
            Expiration date
            CA's signature

            ✅ When you visit an HTTPS site, your browser checks the certificate to make sure the site is trusted and safe.

    🧠 Stateless

        Each request is independent.
        The server does not remember anything from previous requests.
        Used in REST APIs.
        Example: Every time you refresh Instagram, it doesn’t "remember" past clicks—it only reacts to your current request.

    🌍 URLs (Uniform Resource Locator)

        The web address used to access a resource.
        Example:
        https://myapp.com/products?id=10

        https    → Protocol
        myapp.com → Domain
        /products → Path
        ?id=10    → Query


