# Extension Project for ArkCase

This project houses the overall base structure to construct an extension for [ArkCase](https://www.arkcase.com/).  It's divided into three modules, each with a different responsibility:

* [***config***](config) houses the configuration customizations applicable for the extension
* [***extension***](extension) houses the extension's code itself
* [***bundle***](bundle) houses the assembly descriptor to construct the final deployable artifact.

This is the overall structure:

```
example-extension-project
├── bundle
│   ├── pom.xml
│   ├── README.md
│   └── src
│       └── main
│           └── assembly
│               └── main.xml
├── config
│   ├── pom.xml
│   ├── README.md
│   └── src
│       └── main
│           └── resources
│               └── all customized configuration files go here
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
├── pom.xml
└── README.md
```

Generally speaking, you should only need to do these things to get a working project:

* Customize the ***groupId*** and ***artifactId*** values in the POM files
* Customize the list of dependencies required by the extension JAR (we ***highly*** recommend the use of the parent POM's *dependencyManagement* section to manage dependency versions)
* Add the required configurations (*config* module) and code (*extension* module) to be built
