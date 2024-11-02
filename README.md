# Fcnm_laboratory_system
Computer loan system for Espol students in the laboratories of the FCNM faculty, registration of teaching assistant hours for assistants.<br>
# Development environment setup
## Backend with Node.js and Express
Initialize node.js project<br>
```bash
  npm init -y
```
Install Express and other necessary packages<br>
```bash
  npm install express cors dotenv
```
Node.js version<br>
```
npm version -- 10.9.0
```
.env file for port variables<br>
```plaintext
PORT=5000
```
## Frondtend with React
Create principal project<br>
``` bash
npx create-react-app client
```
Install Axios for HTTP requests on the frontend<br>
``` bash
cd client
npm install axios
```
Rect version<br>
```
18.3.1
```
To avoid CORS issues in development, add a proxy in the client/package.json file<br>
```json
{
  "proxy": "http://localhost:5000"
}
```
## Scripts to Run Both Servers

Open file "package.json"<br>
```json
"scripts": {
  "start": "node server.js",
  "client": "cd client && npm start",
  "dev": "concurrently \"npm run start\" \"npm run client\""
}

```

Open file "client/package.jon"<br>
Change the startup script to include the NODE_OPTIONS variable with the value --openssl-legacy-provider:<br>
```json
"scripts": {
  "start": "react-scripts --openssl-legacy-provider start",
  "build": "react-scripts --openssl-legacy-provider build",
  "test": "react-scripts --openssl-legacy-provider test",
  "eject": "react-scripts eject"
}
```

Then, install concurrently to run both servers together:<br>
```bash
npm install concurrently
```
Now you can start the whole project by running:<br>
```bash
npm run dev
```
