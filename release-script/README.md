
# Scripts for uploading;



For libraries which wants to upload artifacts, some properties should be added in `gradle.properties` file under library project dir:

- PROJECT_VERSION

version of the library, e.g. `1.0.0`

- PROJECT_VERSION_CODE

version code of the library, e.g. 1, 2, 3 ...

- PROJECT_POM_NAME

project name will be declared in `pom.xml`.

- PROJECT_POM_ARTIFACT_ID

project artifact id will be declared in `pom.xml`.

- PROJECT_POM_PACKAGING

project packaging type will be declared in `pom.xml`. e.g. aar

- PROJECT_POM_DESCRIPTION

project description will be declared in `pom.xml`.

