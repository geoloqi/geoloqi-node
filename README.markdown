Geoloqi library for Node.js
===
Powerful, flexible, lightweight interface to the Geoloqi Platform API, written in JavaScript for Node.js!

This library was developed with two goals in mind: to be as simple as possible, but also to be very powerful to allow for much higher-end development (multiple Geoloqi apps per instance, concurrency, performance).

Installation
---

    npm install geoloqi

Basic Usage
---
Geoloqi uses OAuth2 for authentication, but if you're only working with your own account, you don't need to go through the authorization steps! Simply go to your account settings on the [Geoloqi site](http://geoloqi.com), click on "Connections" and copy the OAuth 2 Access Token. You can use this token to run the following examples.

In Node.js:

    var geoloqi = require('geoloqi');
    var session = new geoloqi.Session({'access_token':'YOUR ACCESS TOKEN'});
    
    session.get('/account/username', function(result, err) {
      if(err) {
        throw new Error('There has been an error! '+err);
      } else {
        console.log(result.username);
      }
    }

For a post:

    var geoloqi = require('geoloqi');
    var session = new geoloqi.Session({'access_token':'YOUR ACCESS TOKEN'});

    session.post('/account/profile', {'name':'Baron Ünderbheit'}, function(result, err) {
      if(err) {
        throw new Error('There has been an error! '+err);
      } else {
        console.log(result);
      }
    }

Found a bug?
---
Let us know! Send a pull request or a patch. Questions? Ask! We're here to help. File issues, we'll respond to them!

Authors
---
* Patrick Arlt
* Kyle Drake
* Aaron Parecki

TODO
---
* OAuth2 (right now you can only use an access token)
* Plugin for Express
* Lots of stuff
