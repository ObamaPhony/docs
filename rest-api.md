RESTful API for ObamaPhony
==========================

## This file is merely a outline of the RESTful API. The table is likely to be changed, deleted or modified at any point.
## If you have any changes to make, could I suggest doing a PR before we merge anything? :-)

The RESTful API is standalone, it is called from the [frontend](https://github.com/ObamaPhony/frontend) with the URL prefix,
It can also be called as-is by developers wishing to use our project.

The routes of the RESTful API is as follows, assuming it starts after 'http://server/api/v1/'

Route ID|Description|Callback
--------|-----------|--------
/speechgen/speeches|This is a route for the API which returns a JSON object containing a list of Speeches we have cached already. This is called with a HTTP POST request.|Possibly a k:v store with a list of speeches cached, or a MongoDB store which is easier to access.
/speechgen/genspeech/{speech_id}|This a route for the API which calls the Python speech-analysis module, asynchronously, so the server doesn't hang during execution. It takes an ID from the speeches route previously mentioned. 
/speechgen/retrieve/{speech_id}
