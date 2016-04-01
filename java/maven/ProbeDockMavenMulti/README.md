## Project structure

```
ProbeDockMavenMulti
|-- ProbeDockMultiModule1
|-- ProbeDockMultiModule2
|-- ProbeDockMultiModule3
|-- ProbeDockMultiModule4
  |-- ProbeDockMultiModule4-Sub1
  |-- ProbeDockMultiModule4-Sub2
```

## How to test it?

1. Clone this repo
2. Be sure to have an accoun on Probe Dock
3. Make sure to create a project in your Probe Dock organization
4. Update the project id in `/src/test/resources/probedock.yml`
5. Run `mvn clean install` in the project root directory.

At this stage, you should be able to see one report in Probe Dock with 5 tests from Module 1 - 3 and Module 4 Sub 1 and 2.

To run the tests in a submodule, you need to make sure to have run at least once the tests from the root project directory. 
As we use some maven filtering, we expect to find the filtered `probedock.yml` with `${project.version}` replaced by the maven 
version in `Project Root/target/test-classes/probedock.yml`. Once you ensured to have run the tests from the root project, you can
run the tests on each submodules independently by running `mvn clean install` in the submodule of your choice.

# More details?

For more information about the Maven configuration, take a look to these files:

- [Root pom.xml](pom.xml)
- [Module 4 pom.xml](ProbeDockMultiModule4/pom.xml)
