---
breadcrumbs: /ro-crate-java/news/
layout: default
repository_url: https://github.com/kit-data-manager/ro-crate-java
repository_name: kit-data-manager/ro-crate-java
description: A library to create and modify valid RO-Crates.
no_nav: true
tags: ro-crate-java
title:  "ro-crate-java v2.0.0 released"
date: 2024-09-13
---

# ro-crate-java v2.0.0 released

With this major release, it will be easier to describe your data in some cases. The integration of ro-crate-java into your application will be easier if you use the ZipReader. Some APIs have slightly changed in order to avoid the accidental creation of invalid crates in some cases. All known bugs are now fixed and everything complies, to our knowledge, to the specification. Here are some changes we want to highlight in order to help with migration. Please refer to the Javadoc for details.

## Highlights 🚀 

### The ZipReader is now customizable

The ZipReader unpacks the zip file into a temporary folder in order to access the files inside. This folder is, by default, located in the location where the application using ro-crate-java runs in. This can now be customized using a new ZipReader constructor. The default path also changed slightly in order to avoid collisions.

By default, the temporary folders are being removed if the Java Virtual Machine stops running. If you have a long-running application or want to manage space manually, you can now get all information to do this using getter-Methods within the ZipReader class.

Take a look into the ZipReader documentation for details.

### Avoid false-positive warnings if a term is not defined in the context

We do now support full URIs which do not need to be defined in the context, as well as the `@id` and `@json` values for the `@type` attribute. This way you should in practice get less warnings which you could have ignored anyway.

### Detect all data entities as such

When adding a data entity using ro-crate-java, we implicitly connect it to the root data entity using the `hasPart` property. It is up to the user to make more connections, but this is one we currently enforce, to ensure this is recognized as a data entity. If you have the need to handle this differently, please open an issue. When reading crates, we made the same assumption: that the crate will have all data entities in the `hasPart` property. In practice, this may not be the case. We now traverse the graph consisting of `hasPart` (and `isPartOf`) properties in order to find all data entities. When you now use `crate.getAllDataEntities()` and `crate.getAllContextEntities()`, you may get slightly different (meaning correct) results.

### Encoded file paths now work as defined in the specification

We now support encoded file paths and encode them for you without any additional line of code on your side. We used the examples from the specification to ensure maintaining readability, if possible, and only fully encode when all our heuristics did not work out. This will usually keep most characters readable, like Kanji and others.

### Easier provenance descriptions using the ActionEntityBuilder

We now provide an ActionEntityBuilder in order to make it easy to describe the provenance of your data.

## What's Changed
* fix: RootDataEntity identifier is not allowed for other entities. by @Pfeil in https://github.com/kit-data-manager/ro-crate-java/pull/185
* Fix handling of possible loops in data graphs by @Pfeil in https://github.com/kit-data-manager/ro-crate-java/pull/187
* Fix invalid context check warnings by @Pfeil in https://github.com/kit-data-manager/ro-crate-java/pull/188
* Unpack zipped crates into unique temporary folder by @Code42Cate in https://github.com/kit-data-manager/ro-crate-java/pull/83


**Full Changelog (since v2.0.0-rc4)**: https://github.com/kit-data-manager/ro-crate-java/compare/v2.0.0-rc4...v2.0.0

**Full Changelog (since v1.1.0)**: https://github.com/kit-data-manager/ro-crate-java/compare/v1.1.0...v2.0.0