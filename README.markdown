Geoloqi library for Node.js
===
Powerful, flexible, lightweight interface to the Geoloqi Platform API, written in JavaScript for Node.js!

This library was developed with two goals in mind: to be as simple as possible, but also to be very powerful to allow for much higher-end development (multiple Geoloqi apps per instance, concurrency, performance).

Installation
---

    npm install geoloqi

Basic Usage
---
First, retrieve an application access token from one of your applications on the [applications page](https://developers.geoloqi.com/account/applications). 

Here is an example to create a geotrigger:

    var geoloqi = require('geoloqi');
    var session = new geoloqi.Session({'access_token':'YOUR APPLICATION ACCESS TOKEN'});
    
    session.post('/trigger/create', {
      "place_name": "Powell's Books",
      "key":        "powells_books",
      "type":       "message",
      "text":       "Welcome to Powell's Books!",
      "latitude":   45.523334,
      "longitude":  122.681612,
      "radius":     150,
      "trigger_on": "enter"
    }, function(result, err) {
      if(err) {
        throw new Error('There has been an error! '+err);
      } else {
        console.log(result.trigger_id);
      }
    });


Found a bug?
---
Let us know! Send a pull request or a patch. Questions? Ask! We're here to help. File issues, we'll respond to them!

Authors
---
* Patrick Arlt
* Kyle Drake
* Aaron Parecki
