#### **Requirements and recommendations**
To avoid having to set and call cookies it is recommended you install the Postman Interceptor browser plugin and allow Postman to share cookies with your browser. You can then login to your BackBox server web UI and grab the cookies you need before sending API calls from Postman.

I would strongly recommend you use the BackBox UI to generate an API Key, and use that for authentication here. You will see the authorization at the top level is set up for API key, and all calls below that inherit those values.

Set the {{bb-server}} variable to your BackBox server

#### **Disclaimers and caveats!**
This is very much work in progress, please feel free to provide feedback directly to me at devops@backbox.com. 

Please also refer to the Swagger documentation on your BackBox server:

https:///rest/data/swagger-ui.html#/

The following currently available external API calls are not included in this library:

1. Discovery: There are additional discovery APIs being moved to the external library which made it pointless adding these two calls for now.
    1. addDiscoveryJob
    2. updateDiscoveryJob
2. getNetDBSupermacInfo: I need to better understand the use case for this
3. getTaskJobsPageQueue: Will likely be deprecated in favour of a better call
4. deleteReport: This appears to not be working and has been raised with engineering
5. addAuthenticationTemplate: I need to understand the minimum requirements for this call
