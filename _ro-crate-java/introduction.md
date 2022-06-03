---
title: Introduction
breadcrumbs: /ro-crate-java/introduction
layout: default
description: How to use the library.
repository_url: https://github.com/kit-data-manager/ro-crate-java
repository_name: kit-data-manager/ro-crate-java
navigation_id: ro-crate-java_index
---

# {{ page.title }}

Build and run tests: `./gradlew build`  
Build documentation: `./gradlew javadoc`

On windows, replace `./gradlew` with `gradlew.bat`.

## Quickstart
### Example for a basic crate from [RO-Crate website](https://www.researchobject.org/ro-crate/1.1/root-data-entity.html#ro-crate-metadata-file-descriptor)
```java
RoCrate roCrate = new RoCrateBuilder("name", "description").build();
```

### Example adding a File (Data Entity) and a context pair
```java
RoCrate roCrate = new RoCrateBuilder("name", "description")
    .addValuePairToContext("Station", "www.station.com")
    .addUrlToContext("contextUrl")
    .addDataEntity(
      new FileEntity.FileEntityBuilder()
        .setId("survey-responses-2019.csv")
        .addProperty("name", "Survey responses")
        .addProperty("contentSize", "26452")
        .addProperty("encodingFormat", "text/csv")
        .build()
    )
    .addDataEntity(...)
    ...
    .addContextualEntity(...)
    ...
    .build();
```

Note: Adding an entity with an ID ("@id") which is already being used by another entity in the crate, the old entity will be overwritten.

The library currently comes with three specialized DataEntities:

1. `DataSetEntity`
2. `FileEntity` (used in the example above)
3. `WorkflowEntity`

If another type of `DataEntity` is required, the base class `DataEntity` can be used. Example:
```java
new DataEntity.DataEntityBuilder()
    .addType("CreativeWork")
    .setId("ID")
    .addProperty("property from schema.org/Creativework", "value")
    .build();
```
Note that here you are supposed to add the type of your `DataEntity` because it is not known.

A `DataEntity` and its subclasses can have a local file associated with them,
instead of one located on the web (which link is the ID of the data entity). Example:

Example adding file:
```java
new FileEntity.FileEntityBuilder()
    .setId("new_file.txt")
    .setSource(new File("file"))
    .addProperty("description", "my new file that I added")
    .build();
```

### Contextual Entities

Contextual entities cannot be associated with a file (they are pure metadata).

To add a contextual entity to a crate you use the function `.addContextualEntity(ContextualEntity entity)`.
Some types of derived/specializes entities are:
1. `OrganizationEntity`
2. `PersonEntity`
3. `PlaceEntity`

If you need another type of contextual entity, use the base class `ContextualEntity`.

The library provides a way to automatically create contextual entities from external providers. Currently, support for [ORCID](https://orcid.org/) and [ROR](https://ror.org/) is implemented. Example:
```java
PersonEntity person = ORCIDProvider.getPerson("https://orcid.org/*")
OrganizationEntity organization = RORProvider.getOrganization("https://ror.org/*");
```

### Writing Crate to folder or zip file

Writing to folder:
```java
RoCrateWriter folderRoCrateWriter = new RoCrateWriter(new FolderWriter());
folderRoCrateWriter.save(roCrate, "destination");
```

Writing to zip file:
```java
RoCrateWriter roCrateZipWriter = new RoCrateWriter(new ZipWriter());
roCrateZipWriter.save(roCrate, "destination");
```

More writing strategies can be implemented, if required.

### Reading / importing Crate from folder or zip

Reading from folder:
```java
RoCrateReader roCrateFolderReader = new RoCrateReader(new FolderReader());
RoCrate res = roCrateFolderReader.readCrate("source");
```

Reading from zip file:
```java
RoCrateReader roCrateFolderReader = new RoCrateReader(new ZipReader());
RoCrate crate = roCrateFolderReader.readCrate("source");
```

### RO-Crate Website (HTML preview file)
By setting the preview to an `AutomaticPreview`, the library will automatically create a preview using the [ro-crate-html-js](https://www.npmjs.com/package/ro-crate-html-js) tool.
It has to be installed using `npm install --global ro-crate-html-js` in order to use it.
If you want to use a custom-made preview, you can set it using the `CustomPreview` class. `AutomaticPreview` is currently **not** set by default.
```java
RoCrate roCrate = new RoCrateBuilder("name", "description")
    .setPreview(new AutomaticPreview())
    .build();
```

### RO-Crate validation (machine-readable crate profiles)
Right now, the only implemented way of validating a RO-crate is to use a [JSON-Schema](https://json-schema.org/) that the crates metadata JSON file should match. JSON-Schema is an established standard and therefore a good choice for a crate profile. Example:

```java
Validator validator = new Validator(new JsonSchemaValidation("./schema.json"));
boolean valid = validator.validate(crate);
```
