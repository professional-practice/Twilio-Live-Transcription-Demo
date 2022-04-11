Explanation of application
--------------------------
Requirements
------------
Twilio Account and Phone Number
ngrok - Cross-platform application to expose local server post to the internet (moreso for demo purposes)
Google Cloud Account (which has Google Speech-To-Text API enabled, and a service account generated with an access key)
Google Cloud SDK

Dependencies
------------
Express

Websocket

Google Cloud Speech-To-Text

dot.env

1. When a call comes through to our twilio number it make a HTTP POST request to a ngrok url, tunneling to the localhost
2. The server then sends a TwiML response to the request, which in turn begins our audio stream
3. Through the use of Websockets, we can handle the audio stream which is passed to the server by Twilio.
4. This stream is then passed to the Google Speech-To-Text APi which is then displayed to the console and the browser

Problems
--------
We can currently retrieve both streams, however it is extremely slow and not as reliable as we hoped. The application also throws an error in the console after a certain length of time on the call. This is an issue we are currently trying to fix.
