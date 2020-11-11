# React Sample Applications for Okta

This repository contains several sample applications that demonstrate various Okta use-cases in your React application.

Each sample makes use of the [Okta React Library][].

If you haven't done so already, register for a free account at [developer.okta.com](https://developer.okta.com/). Select **Create Free Account** and fill in the forms to complete the registration process. Once you are done and logged in, you will see your Okta Developer Console. 

> **Tip**: You can also create an account using the [Okta CLI](https://github.com/oktadeveloper/okta-cli) and `okta register`. To create an app, run `okta apps create` and use the settings below.

Register your application by selecting **Applications** > **Add Application**. On the next screen, choose **Single Page App** and click **Next**.

On the following screen, edit the application settings. For React applications running in developer mode, the port number should be 8080. Configure your app as follows:

* **Base URI**: `http://localhost:8080`
* **Login redirect URI**: `http://localhost:8080/login/callback` 
* **Logout redirect URI**: `http://localhost:8080` 

Once you have completed the form, you will be given a **client ID**. You will also need the **issuer** value for your Okta org. 

The **issuer** is the URL of the authorization server that will perform authentication.  All Developer Accounts have a "default" authorization server.  The issuer is a combination of your Org URL (found in the upper right of the console home page) and `/oauth2/default`. For example, `https://dev-133337.okta.com/oauth2/default`.

These values must exist as environment variables. They can be exported in the shell, or saved in a file named `testenv`, located in the same directory as this README. See [dotenv](https://www.npmjs.com/package/dotenv) for more details on this file format.

```ini
ISSUER=https://yourOktaDomain.com/oauth2/default
CLIENT_ID=123xxxxx123
```

## Running the server

```
npm install
cd okta-hosted-login
npm install
npm start
```

**NOTE**: The test suite expects you to use `8080` for your port number. Make sure your Okta app has the redirect URI if you want to test these samples.

With these variables set, you should be able to run `npm test` and bask in the glory of passing tests.
