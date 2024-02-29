# Server Side Rendering in React18

1. Create a server folder in root of your project
2. Create two files inside server folder - index.js and server.js
3. Inside index.js - write code to import server, babel and ignore-styles. This will allow the server to translate the React Components to generate HTML.
4. Inside server.js, set up the express server and write code to handle all the requests made by user and inside of it use ReactDomServer.renderToPipeableStream API to implement ServerSide Rendering.
5. The renderToPipeableStream API accepts two parameters - 1. React Node (<App/>) and the second one is an optional streaming object(bootstrapScripts, onShellReady(), onShellError()) and returns an object with two functions - pipe, abort. pipe method is used to send the HTML response in onShellReady function. onShellReady() trigggered when server side rendering completes successfully and ready for client transmission.
6. On the other hand, onShellError get triggered when some problem occured during server side rendering and could not complete.
7. Now, inside index.js file, use hydrateRoot instead of createRoot method
8. Also, in package.json, add script => ssr:npm run build && node server/index.js
   
