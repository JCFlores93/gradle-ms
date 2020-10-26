# LifeCycles
  1. Initialization
     init.gradle + other.gradle  
        settings.gradle
  2. Configuration
        build.gradle 
  3. Execution
        build.gradle
    
    
# Initscript
    Files should be located at
       /Users/name/.gradle/init.d  
    or use: 
      gradle -I/--init-script
    
# This object are the same
Build.gradle = script<interface> + properties + methods => delegates to project<interface> + properties + methods
script<interface> + properties + methods => (delegates to) project<interface> + properties + methods

settings.gradle = script<interface> => (delegates to) settings<interface>
settings is a collection of projects.

init.gradle = script<interface> => (delegates to) gradle<interface>

# To sum up
   ### Runs on the configuration phase
    build.gradle(delegates to) => project
   ### Runs on the initialization phase
    settings.gradle(delegates to) => settings
   ### Runs on the initialization phase
    init.gradle(delegates to) => gradle
   ### Project and settings have access to gradle object
   
## Project object is the default context

##Gradle Properties
* gradle.properties in project root directory
* gradle.properties in GRADLE_USER_HOME directory
* system properties, 
    * e.g. when - Dgradle.user.home is set on the command line.
