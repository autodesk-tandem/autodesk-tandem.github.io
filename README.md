![Tandem API](./img/TandemLogo.png)

# Autodesk Tandem APIs

_Autodesk Tandem API is currently released under a beta program and subject to Autodesk Tandem API Public Beta Program Terms. To learn more, please go to Tandem API page at Autodesk Feedback Community:_ [Tandem Feedback Community](https://feedback.autodesk.com/project/home.html?cap=0951fbaea16047758976fdb0db4d4502)

Tandem digital twins represent a hub of information about your facility and they establish the existence and location of assets within that facility. That foundation is critical, but any good digital twin will include integrations with other systems and will support programmatic management of the asset data. Therefore, API access to the Tandem data model is essential.  Over time, we plan to offer comprehensive APIs in several contexts to help developers customize and extend the foundational capabilities that the Tandem product provides.

![API Contexts](./img/API_contexts.png)

Sample code for each API context exists on GitHub: [Tandem API Samples](https://github.com/autodesk-tandem)

_NOTE: Currently, these samples are marked "Private". To gain access, you will need to request that we add your GitHub username to the repository._

The main read/write functions will not be very interesting until you learn how to setup a Facility, create user-defined Parameters, and map those parameters to assets using Classifications in a Facility Template.  To learn how to do that and to get started with the product, visit: [intandem.autodesk.com](https://intandem.autodesk.com/)

## REST API
The REST API is the first one that will be officially supported.  It is the base level API that communicates with the Tandem data server and manages `create/read/write/delete` of property data for assets. These asset properties are also called "parameters" in the Tandem client app, and those names are interchangeable in this documentation.

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

## Javascript SDK

The Javascript SDK allows you to interact with the Tandem database via Javascript and in "Embedded Viewer" scenarios, similar to how developers use the Forge Viewer.

This API is usable now (in fact the Tandem client uses it), but it is not officially released yet.  There will be some re-factoring to make it usable without instantiating the viewer itself, and some new abstractions and helper functions will be added to make it easy to communicate with the Tandem database.

Developers with experience using the Forge Viewer will be able to quickly get up to speed because the presentation layer is mostly the same.  However, the Tandem Viewer expects there to always be mulitple models loaded, so you should avoid any specific functions that assume only a single model. Accessing the data behind the visual geometry is powered by the Tandem Database instead of the traditional SVF format used by the Forge Viewer. That gives you access to things like Room and Space information, even when it spans across multiple source models. Using the Tandem database also means it is easy to add your own user-defined properties to assets in the model.

The Javascript SDK is not officially documented yet, but an interactive learning tool has been provided to help you experiment with the API. That learning tool and its source code can be found here: [Embedded Viewer Sample](https://github.com/autodesk-tandem/tandem-sample-emb-viewer)


## Tandem Plug-ins

Direct plug-ins to the Tandem product itself are envisioned for the future, but are not yet supported. There have been some experiments with lightweight integrations via a Crome browser plug-in.  A sample project has been included here: [Chrome Plugin Sample](https://github.com/autodesk-tandem/tandem-sample-chrome-ext).

Autodesk does not support Tandem plug-ins at this time, however, so this sample is only provided as-is, with no support or guarantees.
