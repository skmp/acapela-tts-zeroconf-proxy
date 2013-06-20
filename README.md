acapela-tts-zeroconf-proxy
===========

A super-simple to setup proxy for acapela. Uses Acapela's demo/test page to actually get the mp3,
and this way gets around the more complicated license and setup. This is likely to break whenever
acapela updates the test page.

Test page url: http://acapela-group.com/text-to-speech-interactive-demo.html

Acapela has an *AWESOME* tts service, and they do offer free keys, so if don't use this for anything
that's not a 2-hour-long-hack that you can't affort to setup their API/KEY stuff :).

@Acapela, you guys need to give a simpler to use (js-only preferably) interface. It'll help to get 
your amazing TTS service to a wider public. Something like, rate limited per ip and per referer 
host would work just fine from a throttling perspective!


Using this
----------

After installing, just query with ?q="text" and it'll return the mp3 file in a json formated reply.

Example requiest
    http://tts.openert.com/?q=Haiz

Example reply
    { "success": true, "data":"http://vaassl3.acapela-group.com/MESSAGES/012099097112101108097071114111117112/AcapelaGroup_WebDemo_HTML/sounds/90862211_d14fac49b1bb9.mp3" }

You can also specift the sonid id via s= and voice with v= (see the test page's source for the mappings)

Example request
    http://tts.openert.com/?q=Haiz&s=sonid8&v=Nizareng

(Reply has exactly the same format)


Parameters
----------

All parameters are GET encoded

q - text to synthesize - defaults to "Hello, world!"
s - sonid to use - defaults to "sonid9" (english, USA)
v - voice to use - detaults to "Heather"



