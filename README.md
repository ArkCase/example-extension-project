# Extension Project for ArkCase

This project houses the overall base structure to construct an extension for [ArkCase](https://www.arkcase.com/).  It's divided into three subprojects, each with a different responsibility:

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
