Annotation processing in IDEA: bug report
=========================================

IntelliJ IDEA seems to be unable to build annotation processors if you have the module containing them enable annotation proessors, while Gradle is fine with it.

Build successfully in IntelliJ:
-------------------------------

```bash
$ ./gradlew build
:compileJava
:processResources
:classes
:jar
:assemble
:compileTestJava UP-TO-DATE
:processTestResources UP-TO-DATE
:testClasses UP-TO-DATE
:test UP-TO-DATE
:check UP-TO-DATE
:build

BUILD SUCCESSFUL

Total time: 0.761 secs
```

Build unsuccessfully in IDEA:
-----------------------------

```bash
$ ./gradlew idea
```

Open IDEA, build to see this error: `Error:java: Bad service configuration file, or exception thrown while constructing Processor object: javax.annotation.processing.Processor: Provider com.aughr.annotest.MyProcessor not found`
