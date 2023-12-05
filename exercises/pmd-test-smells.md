# Detecting test smells with PMD

In folder [`pmd-documentation`](../pmd-documentation) you will find the documentation of a selection of PMD rules designed to catch test smells.
Identify which of the test smells discussed in classes are implemented by these rules.

Use one of the rules to detect a test smell in one of the following projects:

- [Apache Commons Collections](https://github.com/apache/commons-collections)
- [Apache Commons CLI](https://github.com/apache/commons-cli)
- [Apache Commons Math](https://github.com/apache/commons-math)
- [Apache Commons Lang](https://github.com/apache/commons-lang)

Discuss the test smell you found with the help of PMD and propose here an improvement.
Include the improved test code in this file.

## Answer

 - **JUnitTestsShouldIncludeAssert**: Defines that there should be an assertion in test cases.
 - **UnnecessaryBooleanAssertion**: Defines that an assertion on a literal boolean has no real purpose.
 - **JUnitTestContainsTooManyAsserts**: Checks whether a test contains only one assertion to avoid Piggybacking.
 - **JUnitUseExpected**: Checks for weird exception checking where the test is considered successful when failing 
in a try...catch block. Using `@Test(expected = Exception.class)` is clearer and safer. JUnit5 defines an even better
way to catch such exceptions using `assertThrows`.
 - **JUnit4TestShouldUseTestAnnotation**: As of JUnit4, test methods need to be annotated with `@Test` to be run, whereas
in Junit3, methods had to be named `test....()`. This check exists to not forget methods during the transition from JUnit3
to JUnit4.