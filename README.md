# Extension Project for ArkCase

This project houses the overall base structure to construct an extension for [ArkCase](https://www.arkcase.com/).  It's divided into four modules, each with a different responsibility:

* [***config***](config) houses the configuration customizations applicable for the extension and assembly descriptor to construct the final configuration file.
* [***extension***](extension) houses the extension's BE code itself
* [***extension-ui***](extension-ui) houses the extension's FE code itself
* [***war***](war) houses the war overlay configuration to construct the final deployable artifact.

This is the overall structure:

```
example-extension-project
├── war
│   ├── pom.xml
│   ├── README.md
├── config
│   ├── pom.xml
│   ├── README.md
│   └── src
│       └── main
│           └── resources
│               └── all customized configuration files go here
│           └── assembly
│               └── config.xml - this assembly will join base and extension configuration.
├── extension
│   ├── pom.xml
│   ├── README.md
│   └── src
│       ├── main
│       │   ├── java
│       │   │   └── all Java source files go here
│       │   └── resources
│       │       └── any additional Java resource files go here
│       └── test
│           ├── java
│           │   └── all Java test source files go here
│           └── resources
│               └── any additional Java test resource files go here
├── extension-ui
│   ├── pom.xml
│   └── src
│       ├── main
│       │   ├── angular
│       │   │   └── all FE source files go here
│       │   └── resources
│       │       └── any additional FE resource files go here
├── pom.xml
└── README.md
```

Generally speaking, you should only need to do these things to get a working project:

* Customize the ***groupId*** and ***artifactId*** values in the POM files
* Customize the list of dependencies required by the extension JAR (we ***highly*** recommend the use of the parent POM's *dependencyManagement* section to manage dependency versions)
* Add the required configurations (*config* module) and code (*extension*, *extension-ui* modules) to be built
