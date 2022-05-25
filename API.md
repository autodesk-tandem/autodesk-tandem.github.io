---
title: Rest APIs
has_children: true
nav_order: 2
---

# REST API 

## Autodesk Tandem Model Service API (BETA)

The REST API is the first context that will be officially supported.  It is the base level API that communicates with the Tandem data server and manages `create/read/write/delete` of property data for assets. These asset properties are also called "parameters" in the Tandem client app, and those names are interchangeable in this documentation.

The REST API is a thin layer over the underlying Tandem database.  It is designed to be very efficient and powerful, but with that comes some slightly cryptic payloads and some calls that could cause unwanted changes to the facility data if not constructed properly.  We advise that you avoid calling endpoints that we mark with WARNINGs, and we advise that you do comprehensive testing on datasets that you can afford to recreate before deploying on critical datasets.

In general, the recommendation is to use the Tandem client application to setup Facilities and create Parameters. Then once a Facility is setup, use the REST API to read/write asset properties or assign classifications to assets.

A Postman collection is provided to allow interactive testing of the REST APIs.  It also has sample payloads that explain the various options. Details on how to use the Postman collection can be found here: [Tandem Postman Collection](API_postman.md).  The Postman collection also includes basic documentation for each REST endpoint.

Additional notes about calling the most commonly used endpoints for read/write of asset properties, and for assigning classifications to assets can be found here:

- Read/Query properties (/scan): [Read](API_scan.md)
- Write properties (/mutate): [Write](API_mutate.md)
- Classification and Parameter assignment: [Classification](API_classification.md)
- Qualified Property Names (/attrs): [QualifiedProperties](API_attrs.md)
- Documents: [Documents](API_docs.md)

A sample project using the REST API can be found here: [REST Sample](https://github.com/autodesk-tandem/tandem-sample-rest)

## Javascript SDK (ALPHA)

The Javascript SDK allows you to interact with the Tandem database via Javascript and in "Embedded Viewer" scenarios, similar to how developers use the Forge Viewer.

This API is usable now (in fact the Tandem client application uses it), but it is not officially released yet. As with other ALPHA releases, you should use only for prototyping purposes and not expect to release an official product. There will likely be some re-factoring to make it usable without instantiating the viewer itself, and there will likely be some new abstractions and helper functions added to make it easy to communicate with the Tandem database.

Developers with experience using the Forge Viewer will be able to quickly get up to speed because the presentation layer is mostly the same.  However, the Tandem Viewer expects there to always be multiple models loaded, so you should avoid any specific functions that assume only a single model. Accessing the data behind the visual geometry is powered by the Tandem Database instead of the traditional SVF format used by the Forge Viewer. That gives you access to things like Room and Space information, even when it spans across multiple source models. Using the Tandem database also means it is easy to add your own user-defined properties to assets in the model.

The Javascript SDK is not officially documented yet, but an interactive learning tool has been provided to help you experiment with the API. That learning tool and its source code can be found here: [Embedded Viewer Sample](https://github.com/autodesk-tandem/tandem-sample-emb-viewer)


## Tandem Plug-ins (FUTURE)

Direct plug-ins to the Tandem product itself are envisioned for the future, but are not yet supported. There have been some experiments with lightweight integrations via a Crome browser plug-in.  A sample project has been included here: [Chrome Plugin Sample](https://github.com/autodesk-tandem/tandem-sample-chrome-ext).

Autodesk does not support Tandem plug-ins at this time, however, so this sample is provided as-is, with no support or guarantees.


## Legal Notice

Autodesk Tandem APIs are released as a public beta under the _AUTODESK TANDEM API PUBLIC BETA PROGRAM TERMS_. To learn more, please go to the Tandem API page at Autodesk Feedback Community: [Tandem Feedback Community](https://feedback.autodesk.com/project/home.html?cap=0951fbaea16047758976fdb0db4d4502)

Please note, when you sign up for an Autodesk Forge account, you’ve agreed to [Autodesk Forge Developer Terms of Service](https://www.autodesk.com/company/legal-notices-trademarks/terms-of-service-autodesk360-web-services/forge-platform-web-services-api-terms-of-service).

![CreativeCommons](./img/CreativeCommons.png)

Any related documentation is released under a [Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License](https://creativecommons.org/licenses/by-nc-sa/3.0/). Please see the [Autodesk Creative Commons FAQ](https://knowledge.autodesk.com/customer-service/share-the-knowledge) for more information.

Any related sample code is released on [GitHub](https://github.com/autodesk-tandem) under the Apache 2.0 license.

Roadmaps are plans, not promises. The development, release, and timing of any features or functionality remains at our sole discretion. Roadmaps should not be used to make purchasing decisions.
