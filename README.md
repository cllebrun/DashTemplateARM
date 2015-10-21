Instructions for real time dashboard
-----------------------------------

First you need to register your ARM device to your IBM IoT Foundation organization

1. [Install the cf command-line tool](https://www.ng.bluemix.net/docs/#starters/BuildingWeb.html#install_cf).
2. [Download the real time dashboard application](https://hub.jazz.net/git/f103544/dashboardIoT-ARM-TEMPLATE).
3. Extract the package and `cd` to it. And edit the manifest.yml file with the application that you have created in Bluemix. If your application's name is 'dashboardIoT-ARM-TEMPLATE', then modify it as follows
applications:
- disk_quota: 1024M
  host: dashboardIoT-ARM-TEMPLATE
  name: dashboardIoT-ARM-TEMPLATE
  command: node app.js
  path: .
  domain: mybluemix.net
  instances: 1
  memory: 128M

4. Connect to IoT Foundation and generate an API key and token for your organization, save these credentials somewhere
5. Write your credentials in the app.js file and in routes/dashboard.js
6. Connect to Bluemix:

		cf api https://api.ng.bluemix.net

7. Log into Bluemix:

		cf login -u <your Bluemix Id>
		//optional step, not needed if you are pushing to default org and space
		cf target -o <your org> -s dev

8. Deploy your app:

		cf push <your bluemix-application-name>

9. Access your app: <your bluemix-application-name>.mybluemix.net

