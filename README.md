# template-scripts
gradle scripts for libraries in androidrubick



- `settings.gradle` under root project applies from file `androidrubick.include.gradle`, and contents as below:

```
include ':app'

include ':library'

// apply script, to import sub modules
apply from: './androidrubick-project-scripts/androidrubick.include.gradle'
```

- `build.gradle` under root project applies from file `androidrubick.build.gradle`, and contents as below:

```
// Top-level build file where you can add configuration options common to all sub-projects/modules.

buildscript {
    Properties properties = new Properties()
    properties.load(file('./androidrubick-project-scripts/build-script/build-config.properties').newReader())

    def AVAILABLE_MAVEN_REPO = properties.getProperty('AVAILABLE_MAVEN_REPO').split(';')
    def ANDROID_BUILD_GRADLE_PLUGIN = properties.getProperty('ANDROID_BUILD_GRADLE_PLUGIN')
    repositories {
        AVAILABLE_MAVEN_REPO.each { mavenUrl ->
            maven { url mavenUrl }
        }
        jcenter()
    }

    dependencies {
        classpath ANDROID_BUILD_GRADLE_PLUGIN

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

apply from: file('./androidrubick-project-scripts/androidrubick.build.gradle')

```


- `build.gradle` of android library module, applies from `AR_EXTRAS.LIB_MODULE_TEMPLATE_SCRIPT`

- `build.gradle` of android application module, applies from `AR_EXTRAS.APP_MODULE_TEMPLATE_SCRIPT`


