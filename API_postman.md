---
title: Postman Collection
parent: Rest APIs
has_children: false
nav_order: 1
---

## Tandem API Postman Collection

Find the Postman  collection here: [Postman Collection](https://documenter.getpostman.com/view/15787353/UVeFMRdB)

![Postman_01](./img/postman_01.png)
![Postman_02](./img/postman_02.png)

Then import the collection into your workspace...

![Postman_03](./img/postman_03.png)

Then it should show up as a collection...

![Postman_04](./img/postman_04.png)

That should give you access to the documentation and the interactive collection.  The documentation for the REST API is only half finished, but hopefully being able to run interactively in Postman will help you figure things out.  The two major functions to READ/WRITE data are a little tricky:  
- `{{TandemBaseURL}}/modeldata/:modelID/scan`  
- `{{TandemBaseURL}}/modeldata/:modelID/mutate`  

There is a simple example saved in the Collection, but the full scope of these functions is much broader if you know all the flags to send it.  You can also cross-reference with the REST Sample code on GitHub. 

The Postman collection allows you to interactively test the Tandem REST API calls.  The collection is setup with certain environment variables that allow you to quickly substitute specific authorization tokens and model URNs in the pre-defined tests.

To set the TandemAuthToken variable, you can do the following:

Scrape an existing token from a running session of Tandem.

![Postman_05](./img/postman_05.png)
![Postman_06](./img/postman_06.png)

Paste that token into the Environment Variables in Postman.  Make sure to Save these changes.

![Postman_07](./img/postman_07.png)

Copy the URN of a specific Facility in Tandem

![Postman_08](./img/postman_08.png)

Paste the URN into the environment variable for TandemSampleFacilityURN.  Make sure to Save these changes.

![Postman_09](./img/postman_09.png)

Now go to the Collection and select a specific REST endpoint.

For a complex call like /scan, there are several variants stored as examples.  You can quickly see the call and response from previous calls I have made.  If you want to do your own dynamic call, copy the body of the request, then go into the POST entry for /scan and paste that into the body of the call, change any values you want, then hit Send to get a new result.

![Postman_10](./img/postman_10.png)


## Legal Notice

![CreativeCommons](./img/CreativeCommons.png)

Except where otherwise noted, documentation provided in connection with Tandem Model Service API is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License](https://creativecommons.org/licenses/by-nc-sa/3.0/). Please see the [Autodesk Creative Commons FAQ](https://knowledge.autodesk.com/customer-service/share-the-knowledge) for more information.
