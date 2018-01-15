# Load external urls within your Action

Kaizala enables Action developers to load https urls within an Action. In scenarios, where Action developer wants to open a webpage, they can use ‘externalUrls’ to load webpages within immersive views.
In order to enable loading of webpage within an Action, Action developer needs to whitelist the urls and add them in the Package.json file for the Action.

## Whitelisting external URL

In your ‘Package.json’ file for your Action
* Add a new tag **‘externalUrls’**.
* Add list of URLs which you want to whitelist in this tag. Please find the part of the sample code below. 
```
  "externalUrls": [
    { "url" : "https://www.example-url.com" },
    { "url" : "https://another-example-url.com" },
  ],
```
* Each url should be a valid complete url.
* Each url should be an https url.

