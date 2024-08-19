# CryptoManagerServer
A Node.JS Server For My Crypto Currency Manager
I am currently building a cryptocurrency visualisation and data management tool to learn about WebSockets, Node.JS and Blazor WASM.
This Node.JS server will act as the backend for that site, with WebSockets to Binance and the Front-End to create a seemless, live data manipulation and analysis tool

This is the list of Tasks I think I need to work through for this project

Current Task List:
1. Set Up the Development Environment
   
    Install Node.js and npm on Development Laptop:
    
        Download and install Node.js and npm (Node Package Manager).
        Verify installation with node -v and npm -v.
        Initialize the Node.js Project:
        
        Create a new project directory on your development laptop.
        Run npm init -y to create a package.json file.
        Install Project Dependencies:
        
        Install necessary Node.js packages using npm:
        Express.js for creating the web server: npm install express
        Sequelize for ORM (Object-Relational Mapping): npm install sequelize
        MySQL2 for connecting to MySQL: npm install mysql2
        dotenv for environment variable management: npm install dotenv
        nodemon for auto-restarting the server during development: npm install --save-dev nodemon
        pm2 for process management (optional, for production): npm install -g pm2
        ws for basic WebSocket support: npm install ws (or socket.io for a more feature-rich solution)
        Set Up Git for Version Control:
        
        Initialize a Git repository in your project directory: git init
        Create a .gitignore file to exclude node_modules, .env, and other unnecessary files.
        Commit your initial files: git add . and git commit -m "Initial commit"
        Set Up MySQL Database on Development Laptop:
        
        Install MySQL on your development laptop.
        Create a new database for your project (e.g., my_crypto_db).
        Optionally, use a GUI tool like MySQL Workbench for easier management.
        Install and Configure Sequelize:
        
        Set up Sequelize to connect to your MySQL database.
        Create Sequelize models to map JavaScript objects to database tables.
        Create migration files if needed, to manage database schema changes over time.
        Create Environment Variables:
        
        Create a .env file for your development environment with variables like DB_HOST, DB_USER, DB_PASSWORD, API_URL, etc.
        Prepare a .env.production file for production, which will have different values suitable for the live environment.
        Develop the Node.js Server:
        
        Set up the Express server in app.js or a similar entry file.
        Create routes and controllers for handling API requests.
        Integrate Sequelize for database interactions (CRUD operations).
        Implement error handling and logging.
        Set up the necessary middleware (e.g., for parsing JSON, handling CORS).
2. Set Up the Hosting Environment
   
    Install Node.js and npm on Host PC:
    
        Install Node.js and npm on your hosting machine.
        Verify the installation with node -v and npm -v.
        Set Up MySQL (or Alternative) on Host PC:
        
        Install MySQL or an alternative like SQL Express if you're using that for database management.
        Ensure the database schema matches what you've set up in development (use Sequelize migrations if applicable).
        Set Up Environment Variables on Host PC:
        
        Create a .env file on the hosting machine with production-specific values.
        Ensure sensitive information (e.g., database credentials, API keys) is securely managed.
        Check and Configure Dynamic DNS (DDNS) on Orbi Router:
        
        Access the Orbi router’s web interface at http://orbilogin.com or http://192.168.1.1.
        Log in with your router’s admin credentials.
        Navigate to the Advanced Setup or Advanced section and find Dynamic DNS or DDNS.
        Set up a DDNS service (e.g., No-IP, DynDNS) with your account details.
        Verify that the DDNS is correctly configured by accessing your server through the provided domain name.
        Configure port forwarding on the Orbi router to allow external access to your Node.js server.
3. Implement WebSocket Support
   
    Connect to Binance’s WebSocket API:
    
        Use a WebSocket client (like ws) to connect to Binance’s WebSocket API and receive live market data.
        Handle incoming data from Binance, such as price updates, and process it as needed.
        Set Up WebSocket Server on Node.js:
        
        Install a WebSocket library (ws or Socket.IO) on your Node.js server.
        Create a WebSocket server to handle connections from front-end clients.
        Implement broadcasting of Binance data to connected clients in real-time.
        Update Front-End to Use WebSockets:
        
        Modify the front-end code to connect to the WebSocket server on your Node.js backend.
        Handle real-time data updates from the WebSocket connection and update the UI accordingly.
        Test Real-Time Data Flow:
        
        Test the full data flow from Binance to your Node.js server, and then to the front-end via WebSockets.
        Ensure that updates are received in real-time and displayed correctly in the UI.
4. Implement Rate Limiting and Security Best Practices
   
    Implement Rate Limiting on the Node.js Server:
    
        Install and configure express-rate-limit middleware to limit the rate of incoming HTTP requests to your Node.js server.
        Implement custom rate limiting or throttling for WebSocket connections to prevent abuse or excessive usage.
        Review and Implement Security Best Practices:
        
        Environment Variable Management: Ensure sensitive information is stored in environment variables and not hard-coded. Use the dotenv package for managing environment variables.
        Input Validation and Sanitization: Validate and sanitize all inputs to prevent injection attacks.
        Use HTTPS: Set up SSL/TLS using Let’s Encrypt to ensure all communications between the client and server are encrypted.
        Implement CORS: Configure CORS (Cross-Origin Resource Sharing) to control which domains can access your API.
        Test and Validate Security Implementations:
        
        Conduct a security review of your application, ensuring that all best practices are followed.
        Perform penetration testing or use tools like OWASP ZAP to identify and fix any vulnerabilities.
5. Deploy and Run the Application
    
    Publish the Node.js Server to GitHub:
    
        Commit your changes to the Git repository.
        Push the repository to GitHub (or another remote Git repository).
        Pull the Node.js Server to Host PC:
        
        On your hosting machine, clone the Git repository or pull the latest changes.
        Run npm install to install all dependencies listed in package.json.
        Initialize and Start the Node.js Server on Host PC:
        
        Use pm2 to start the Node.js server and ensure it runs in the background:
        pm2 start src/app.js --name my-app
        pm2 save to save the process list.
        pm2 startup to ensure the server starts on reboot.
        Set Up Port Forwarding and Firewall Rules:
        
        Configure your router to forward incoming traffic on port 80 (HTTP) or 443 (HTTPS) to your hosting machine.
        Adjust firewall settings on your host PC to allow traffic on these ports.
        Configure SSL/TLS (Optional but Recommended):
        
        Use Let’s Encrypt with Certbot to obtain a free SSL certificate.
        Configure your Node.js server to serve traffic over HTTPS.
6. Update the Front-End
    
    Update Front-End Code to Use Node.js Server:
    
        Modify the front-end code to point to the Node.js server’s API instead of the previous API.
        Ensure the front end uses environment variables to switch between the development and production API URLs.
        Test and Deploy Front-End Changes:
        
        Test the front end locally with the new API.
        Deploy the updated front end to Hostinger, ensuring it points to the production Node.js server.
        Monitor and Maintain the Application:
        
        Monitor server logs and performance using pm2 or other monitoring tools.
        Regularly update dependencies and Node.js to ensure security.
        Handle database backups and migrations as needed.
