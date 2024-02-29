# Extension Deployment Bundle for ArkCase

This project should generally not be modified beyond tuning the POM file's ***groupId*** and ***artifactId*** values.  The design is such that with no modifications it will produce a deployable bundle that includes both the configurations and the extension code within the resulting archive, correctly organized so that this archive can be deployed directly into an ***acm-config*** (a.k.a. *.arkcase*) directory.

Dependencies to either of those projects listed on a scope other than ***provided*** will be included in this deployment bundle automatically.  As a result, care must be taken to properly manage those dependencies to avoid duplicate code, or "JAR hell".

The final artifact should conform to the following structure:

  * all configuration files from the ***config*** project (i.e. contained in ***config/src/main/resources***) should be stored in the root of the bundle archive, preserving all paths
  * the resulting JAR built from the ***extensions*** project should be stored within the archive in the ***custom/WEB-INF/lib*** directory
  * any required dependencies from the ***extensions*** project, **that are not already provided by ArkCase**, should also be stored within the archive in the ***custom/WEB-INF/lib*** directory
