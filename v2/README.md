#AfterShip API

#V2 API

The AfterShip API is implemented as JSON over HTTP using all four verbs (GET/POST/PUT/DELETE). Each resource, like Tracking, Courier, has its own URL and is manipulated in isolation. In other words, we’ve tried to make the API follow the REST principles as much as possible.

All API usage happens through AfterShip applications, created by either website owners for their own sites, or by AfterShip developer for use by website owners.

Website owners can create applications for themselves through their own account -> API Key

[https://www.aftership.com/connect](https://www.aftership.com/connect)

Developers create applications through their account page.

Please note that API calls are limited to making a maximum of 100 calls to each user. This limit resets every 600 seconds. If your application needs a higher limit, contact support@aftership.com

#How To Get the API Key
* After sign in to your account:
	
	* Top Menu -> Account -> Account Summary
	* Click `Add store`
	* Choose the `API Key`
