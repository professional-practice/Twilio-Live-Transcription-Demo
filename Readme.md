Explanation of application
--------------------------
Prerequisites
------------
Twilio
------

1. Create a free Twilio account (https://www.twilio.com/try-twilio)

2. Once created, navigate to the **Phone Numbers** section within the console and **Buy a Number**. A number can be purchased using the trial credits.

3. Due to Twilios trial account only allowing calls to verified call IDs, all numbers that are used for testing should be added to the **Verified Caller IDs** section under **Phone Numbers**

Google Cloud
------------
1. Create a Google Cloud account (https://cloud.google.com/)

2. Set-up a new Google Cloud Project.

3. Navigate to the **APIs and Services** Enable the Google Speech-To-Text API for your newly created GCP.

4. Create a service account under the Google Speech-To-Text API. This allows us to create a way to autenticate access to use the transcription service.

5. Navigate to your service account and open the **Keys** section. Create a new key as a JSON format. This will then download the necessary credentials to your computer.

6. In the .env file within this folder, update the field with the location of your downloaded key. Ensure this is saved as an `.env` file

Ngrok
-----
Cross-platform application to expose local server post to the internet by tunneling requests

1. Download and install Ngrok (https://ngrok.com/)

Setup
-----
1. Install the necessary dependencies and begin server:
`npm install`
`npm start`

2. Open ngrok and run the following:
`ngrok http 8080`

3. Take note of the URL which is generated, it should similiar to this:
`http://5165-193-1-57-4.ngrok.io`

4. Navigate to your **Active Numbers** in your Twilio Console and select your established number. Under the **A Call Comes In** section, ensure that the option is set to Webhook and HTTP POST. Update this field with your ngrok URL

5. Save these settings

6. Update the **<Dial>** field in the `index.js`

7. Navigate to `localhost:8080` in your browser

8. Give your established Twilio number a ring and see your voice be displayed in text


