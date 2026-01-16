
Requires IISNode and HTTP server to run on Azure Web-App using Windows
Sometimes the web-app needs to be manually restarted after deployment. Might not work at first, but give it time to spin-up


Health-checks can make the application break, so add the following
`const server = http.createServer((req, res) => {`
  `if (req.url === "/health") {`
    `res.writeHead(200, { "Content-Type": "text/plain" });`
    `res.end("OK");`
    `return;`
  `}`
  `if (req.url === "/") {`
    `res.writeHead(200, { "Content-Type": "text/plain" });`
    `res.end("Socket server running");`
    `return;`
  `}`
  `// Let socket.io/engine.io handle /socket.io/*`
  `res.writeHead(404);`
  `res.end();`
`});`

Start the server
`// Attach Socket.IO`
`const io = new Server(server, {`
  `connectionStateRecovery: {},`
  `cors: { origin: "*", methods: ["GET", "POST"] },`
  `transports: ["websocket"] // avoids polling+CORS complications behind IIS`
`});`


Web.Config example

`<?xml version="1.0" encoding="utf-8"?>`
`<configuration>`
  `<system.webServer>`
    `<webSocket enabled="false" />`
    `<handlers>`
      `<add name="iisnode" path="app.js" verb="*" modules="iisnode" />`
    `</handlers>`
    `<rewrite>`
      `<rules>`
        `<rule name="NodeServer" stopProcessing="true">`
          `<match url=".*" />`
          `<action type="Rewrite" url="app.js" />`
        `</rule>`
      `</rules>`
    `</rewrite>`

    `<urlCompression doStaticCompression="false" doDynamicCompression="false" />`

    `<iisnode`
      `loggingEnabled="true"`
      `devErrorsEnabled="true"`
      `flushResponse="true"`
    `/>`
  `</system.webServer>`
`</configuration>`