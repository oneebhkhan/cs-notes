### What is Gradle
- Build automation tool that is used to build test deploy and relsease software
- Comes with rich build description language as groovy and kotlin
- Build by princple
- No POM files in Gradle.

### Gradle vs [[Maven]]
#### Advantages 
- tasks on going tasks and not input and output tasks
- parallel test execution
- highly customizable
- uses cache for faster and efficient builds
- flexible
- UI
- incremental builds - only the changes get compiled

#### Disadvantages

### Kotlin DSL (Domain Specific Language)
- same language for build scripts and application
- type-safe. error caught at compule time
- kotlin code is faster than groovy code
- better IDE support

### Gradle Files & Directories
Files
- settings.gradle.kts
- build.gradle.kts
- gradle.properties
Directories
- Project root directory
- User home directory (.gradle)

### Multi Project Builds
Gradle Build vs. Gradle Project

#### Configuring Project Builds
**Tasks**: 
* represents an atomic piece of work within a build
Types:
- Lifecycle tasks
	- `dependsOn` defines sequence of tasks
	- Lifecycle tasks determine order of tasks in a build
- Actionable tasks
Task dependencies

Gradle builds a DAG of tasks
#Question what is clean, verify, build in Gradle and Maven?

**Plugins**
- Extend project build capabilities.
- Can be defined in settings file - applies to all projects 
- Can be define in build file - applies to specific project
Types:
- Core plugins - shipped with gradle
- Community plugins - available in gradle community portal _and_ maven central
	- We need to specify their versions
- Convention plugins - we write and maintain it. Meant to encapsulate custome build logic

### The Build Lifecycle
1. Intitialization
2. Configuration
	Fetches build scripts of all dependencies
3. Execution
	Which specific tasks within a DAG need to be run

### Gradle Cache
1. Configuration cache
	Cache of configuration
2. Build cache 
	Cache of execution part

### Dependencies
* Resolution of dependencies

* Gradle Configurations
	* Synonymous to "Maven Scope" 
		#Question What is Maven Scope?
* Rich versions
* Contraints

### Configuring JVM Projects
- Java plugin - when we're working on an application e.g. when working on a server
- Java library plugin - additional functionality supposed to be used for libraries of Java e.g. client and interface libraries

### Gradle Metadata
- Descriptor vs metadata
	- Build.gradle = descriptor metadata files
	- Metadata file is separate gradle.
	- In maven, descriptor and metadata files are the same - pom file
	- Gradle is compatible with pom metadata files of maven