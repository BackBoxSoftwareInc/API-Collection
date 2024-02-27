#### **Requirements and recommendations**
There are three methods of authenticating API calls:
1. Cookies. If calling the API with curl you will need to get and store cookies, see the swagger page for instruction on how to do that. When using Postman, to avoid having to set and call cookies it is recommended you install the Postman Interceptor browser plugin and allow Postman to share cookies with your browser. You can then login to your BackBox server web UI and grab the cookies you need before sending API calls from Postman.
2. Short term API key (30 minutes) Use the "Get Short Term API Key" request. Note that there is currently a bug which means you'll receive a 403, but you will have an Auth: header in the response containing a key. Grab that and put it in the top level auth section of this collection.
3. Long term API key (up to 180 days). You can only generate these through the web UI. Once you are comfortable transferring API calls from Postman into your scripting language of choice, I would recommend using the long term API key when exploring the API through Postman

#### **Variables**
* Set the {{bb-server}} variable to your BackBox server
* Set the {{path_to_endpoint}} variable to suit your needs:
** https://{{bb_server}}/rest/data/token/api/ if using a token
** https://{{bb_server}}/rest/data/api/ if using cookies



#### **Disclaimers and caveats!**
This is very much work in progress, please feel free to provide feedback directly to devops@backbox.com. 

Please also refer to the Swagger documentation on your BackBox server:

https://{{bb-server}}/rest/data/swagger-ui.html#/

The following currently available external API calls are not included in this library:

1. Discovery: There are additional discovery APIs being moved to the external library which made it pointless adding these two calls for now.
    1. addDiscoveryJob
    2. updateDiscoveryJob
2. getNetDBSupermacInfo: Need to better understand the use case for this
3. getTaskJobsPageQueue: Will likely be deprecated in favour of a better call
4. deleteReport: Currently not working, bug raised with engineering
