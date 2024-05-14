### Simple Express session demo

The first time you visit the site from a browser, your "session" is created. The Session ID is sent in the response as a Cookie (`Set-Cookie` header)

![image](https://github.com/TienSFU25/2650-express-session-demo/assets/10173141/c27784ed-7b96-4030-ae77-6f6e569fe192)

On subsequent visits, the browser sends a Cookie with the Session ID in the previous step. This Session ID uniquely identifies the "Session". Other values associated with this Session ID is stored in memory

![image](https://github.com/TienSFU25/2650-express-session-demo/assets/10173141/37854599-807c-4c68-8317-22659defa959)

Upon going to a new incognito tab, you'll see that a new Session is created

![image](https://github.com/TienSFU25/2650-express-session-demo/assets/10173141/ecb98e5d-c6a5-4ad1-8134-95a595640057)

To convince yourself that it's actually the Session Cookie that's enabling this magic, go to Network tab. Remember to check "Preserve log". You'll see the `connect.sid=` stuff in the Cookie.

![image](https://github.com/TienSFU25/2650-express-session-demo/assets/10173141/6e7e7979-d1eb-4c79-980c-c778cc40c95f)

Set the `cookie maxAge` in `server.js` to a larger number for this experiment. With the network tab open to `http://localhost:3000`, refresh till you get to 5 views. Then copy paste the Cookie content

![image](https://github.com/TienSFU25/2650-express-session-demo/assets/10173141/6d18c9c6-a191-4db3-9a9a-4228df1a08e6)

into Postman 

![image](https://github.com/TienSFU25/2650-express-session-demo/assets/10173141/d46506af-5ebe-416b-80cb-9868241763af)

Send 10 of these requests in Postman, then back to your original browser

![image](https://github.com/TienSFU25/2650-express-session-demo/assets/10173141/5bd949c9-7af4-4526-bfdf-54dfec3345ff)

Play around with the `/print-sessions` endpoint for more information.
