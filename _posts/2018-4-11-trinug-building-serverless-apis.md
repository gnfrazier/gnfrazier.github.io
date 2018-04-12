---
layout: post
title: Trinug Meetup - Building Serverless APIs with Azure Functions with Josh Carlisle
tags: Azure API serverless
---

My notes from the April 11th meeting of TriNug. I don't go to many TriNug events, but the topic for this one was too close to where I want to go with services and jobs at work... If it runs in less than 5 minutes and we can do it in C# or Java, then function should be the first option - not the last. 

I have done minimal clean up - consider this live noting. 

* * *

### Benefits of Azure Functions

There really are servers with serverless - you just think about the servers... less Ha!  
Shorten development cycle from weeks or months to configure a box to a few minutes.  
Scale apps and instances dynamically with load. Possible with IAAS and PAAS, but functions do this by definition.
Because the functions end they are more cost effective. Only pay for what you use. Fractions of pennies at low volumes, but at a certain point they may be more expensive than a full VM.  Essentially functions are using the spare compute at the data center.  
Ideal target is variable use, infrequent use routines.

### Overview of Azure Functions

#### Building the App

-   add a function app to a resource group
-   App name becomes the root for the endpoint
    -   Name is global within azure, but you can pipe your custom domain
-   Consumption vs App Service Plan
    -   Consumption is auto-scale
    -   App Service is consistent (CPUS, etc are set)
-   Azure functions requires Azure storage
    -   Can come down to zero instances
    -   Must have storage for the app to live (logs and so on too)
-   Use Applications Insights - just do it, there is a free tier
-   Can be done in the portal or using an ARM template, CLI, Powershell, whatever
-   Can use the editor window with in the app - but don't for real projects
    -   use your own editor and source control etc
-   Publish source code, compile in the function.
-   Function.json is what defines the function
    -   Triggers only one per function 
        -   File dumped to blob
        -   API trigger
        -   Cue
        -   Messages
        -   etc
    -   Output - can be multiple
        -   Blob
        -   Table
        -   http
        -   etc

### Azure Functions Development Experience

-   Languages
    -   C#
    -   Javascript - Node
    -   F#
    -   Soon
        -   Java, Experimental, PHP, Powershell, Python
-   Local Dev support with a runtime Azure Functions CLI (same runtime as production)
    -   Does not scale
    -   Great for dev and make sure dev will run on production
    -   Runs on .Net 4.0
-   [Visual Studio Code Plugins](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)
-   VST (better for C#)
-   .Net Core support in preview - opens support for linux and Mac local run runtime

### Anatomy of a Function

[photo]
Trigger Binding - highlighted
Input Binding - highlighted
Keep in mind keys, if public then anybody can hit the endpoint

### Basic Azure Functions with VS

Designate the route within the trigger binding (endpoint)

[Azure Table storage](https://azure.microsoft.com/en-us/services/storage/tables/) - simple, cheap, easy
Functions talk directly to table storage, define it as the output variable
Can bind the table directly to the function. No extra coding needed (in C#)

In general - use the bindings for function. Saves dozens of lines of code.
      for instance Icollector or AICollector

### Visual Studio Support

-   Must be 2017
-   Must have cloud workload extension
-   Need Azure Functions and Web Jobs Tool Kits

In VST there are preset templates
    Some default Triggers like Timer etc

Trick - [Azure Storage Explorer App](https://azure.microsoft.com/en-us/features/storage-explorer/)

API development - [Postman App](https://www.getpostman.com/apps) (post and get from API's without writing custom code)

### Azure Functions Architecture Considerations

-   Be aware of down stream data storage
-   Be aware of long running functions (more than 5 minutes)
-   Ensure your functions are doing small amounts of work 
-   Breakdown large input files by a smaller number of rows
-   Queues that are implemented in at front end may impact the traditional request flow
-   Lots to orchestrate? Consider Durable Functions. Logic controller and flow controller.

### [Azure Function Proxies](https://azure.microsoft.com/en-us/updates/announcing-azure-functions-proxies-in-public-preview/)

-   The proxies acts as an interaction layer for the API
-   Prevents hardcoding for the API
-   Prevents inconsistencies in the API syntax if using multiple technologies (function vs logic app vs...)

### Speaker Contact Info

[www.joshcarlisle.io](https://www.joshcarlisle.io)
[@joshcarlisle on twitter](https://twitter.com/joshcarlisle)
