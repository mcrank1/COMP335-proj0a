[![Java sbt CI](https://github.com/lucformalmethodscourse/hello-java-sbt/actions/workflows/java-sbt.yml/badge.svg)](https://github.com/lucformalmethodscourse/hello-java-sbt/actions/workflows/java-sbt.yml)

This build will always fail because it has 2 examples of failing tests:
one because of a defect in the SUT (system under test), and one because of an error in the test itself.

# Learning objectives

* Simple hello world example
* Experience with Git source code management
* Building with SBT
* Automated unit testing with JUnit
* Continuous integration with GitHub Actions

# System requirements

* Java 17 SDK or later (Java 17 LTS release recommended)
* [SBT](https://www.scala-sbt.org/1.x/docs/Setup.html)

# Running the application

Without command-line arguments:

    $ sbt run

With specific command-line arguments:

    $ sbt "run arg1 arg2 arg3"
	
# Running the tests

    $ sbt test
	
# Generating the test coverage reports

    $ sbt jacoco
	
You will then see the coverage report on the console. 
In addition, you can view a formatted HTML version of report in a web browser.

In Gitpod, navigate to and open

    target/scala-2.13/jacoco/report/html/index.html
    
then press the "show preview" button in the top right corner.

On macOS:

    $ open target/scala-2.13/jacoco/report/html/index.html

On Linux:

    $ xdg-open target/scala-2.13/jacoco/report/html/index.html

On Windows: please let me know if you know how to do this from the WSL
command line. Otherwise you can open the index file in your web browser.

*Note that the report will show 0% coverage as long as there are failing tests.*

# Running the application outside SBT

This allows passing command-line arguments directly:

On Linux or macOS:

    $ sbt stage
    $ ./target/universal/stage/bin/hello-java arg1 arg2 arg3

On Windows:

    > sbt stage
    > .\target\universal\stage\bin\hello-java arg1 arg2 arg3
