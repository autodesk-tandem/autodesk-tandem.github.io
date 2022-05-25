---
title: Javascript SDK
has_children: false
nav_order: 3
---
# Javascript SDK

The Javascript SDK allows you to interact with the Tandem database via Javascript and in "Embedded Viewer" scenarios, similar to how developers use the Forge Viewer.

This API is usable now (in fact the Tandem client application uses it), but it is not officially released yet. As with other ALPHA releases, you should use only for prototyping purposes and not expect to release an official product. There will likely be some re-factoring to make it usable without instantiating the viewer itself, and there will likely be some new abstractions and helper functions added to make it easy to communicate with the Tandem database.

Developers with experience using the Forge Viewer will be able to quickly get up to speed because the presentation layer is mostly the same.  However, the Tandem Viewer expects there to always be multiple models loaded, so you should avoid any specific functions that assume only a single model. Accessing the data behind the visual geometry is powered by the Tandem Database instead of the traditional SVF format used by the Forge Viewer. That gives you access to things like Room and Space information, even when it spans across multiple source models. Using the Tandem database also means it is easy to add your own user-defined properties to assets in the model.

The Javascript SDK is not officially documented yet, but an interactive learning tool has been provided to help you experiment with the API. That learning tool and its source code can be found here: [Embedded Viewer Sample](https://github.com/autodesk-tandem/tandem-sample-emb-viewer)
