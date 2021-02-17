## Languages and Frameworks

This project using the following Libraries and Frameworks:

* [Maven](https://maven.apache.org/) as the Dependency Management tool
* [Java 11](https://openjdk.java.net/projects/jdk/11/) as the programming language
* [TestNG](https://testng.org/doc/) as the UnitTest framework to support the test creation
* [Seleium WebDriver](https://www.selenium.dev/) as the web browser automation framework using the Java binding
* [AssertJ](https://joel-costigliola.github.io/assertj/) as the fluent assertion library
* [Allure Report](https://docs.qameta.io/allure/) as the testing report strategy
* [WebDriverManager](https://github.com/bonigarcia/webdrivermanager) for the Selenium WebDriver Binaries Management
* [Page Objects pattern](#page-objects-pattern)
* [TestListener](#testlistener) - iTestListener is used for implementing the TestListener. The TestListener is a class that implements ITestListener. 
  The following method is in use to help logging errors and attach additional information on the test report:
             **onTestStart**: add the browser information into the test report
             **onTestFailure**: log the exceptions and add a screenshot on the test report
             **onTestSkipped**: add the skipped test on the log
* [Logging](#logging) - All the log is done by the Log4J plugin.
* [Parallel execution](#parallel-execution) - using TestNG 
* [Data Provider](#data-provider) - with Apache POI Plugin and Excel Utility
* [BaseTest] - This testing pattern was implemented on the BaseTest class to automatically run the pre (setup) and post (teardown) condition

###The framework consists of below higlighted features and can be improved further:

 Encapsulation layers like test data, logic of tests, actions on web pages -- Done
 Reading test data from excel sheet (in this framework) -- Done
 Generating random values for test data, Implementing Data Provider and using Excel Utility for Data -- Done
 Browser/WebDriver Factory -- Done
 Ability to run tests for different browsers/OS by configuring -- Done
 Ability to run tests for different environments by configuring/by command-line -- Done
 Run Tests in Parallel Mode -- Done
 Logging -- Done
 Taking screenshot on failed tests -- Done
 Generation Allure Reports --Done

## How to Run

Default Parameters are defined in pom.xml. These can be overridden by passing the parameters through the command linnen as given below -

`<is_parallel>false</is_parallel>
<browserName>chrome</browserName>
<environment>prod</environment>
<platform>MAC</platform>
<appUrl>http://automationpractice.com/index.php</appUrl>`

`mvn clean test -DbrowserName=chrome -Dplatform=WIN -DappUrl=http://automationpractice.com/index.php ---> Above parameters can be changed to different values. If not passed , default values will be picked.
`
To generate Allure Report - `mvn allure:report`

Report will be generated at  target/allure-report/index.html
Sample report is available at allure-report/index.html

Logs will be generated at target/log4j-application.log




