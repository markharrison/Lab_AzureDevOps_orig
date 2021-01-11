# Azure DevOps - Hands-on Lab Script

Mark Harrison : 26 March 2020 ... updated 11 January 2021

![](Images/devops.png)

- [Part 1 - Create Project / Application](azuredevops-1.md)
- [Part 2 - Development](azuredevops-2.md)
- [Part 3 - Test Plans](azuredevops-3.md) ... this document
- [Part 4 - Accessibility Testing](azuredevops-4.md)

## TestPlans

### Manual Testing

Manual testing has evolved with the software development process into a more agile-based approach. Azure DevOps integrate manual testing into your agile processes; the team can begin manual testing right from their Kanban boards in the Work hub. In Azure DevOps, you need just Basic access to use these features.

![](Images/TPKanban.png)

Teams that need more advanced capabilities can use the Test hub for all their test management needs. This enables organizing tests into test plans and test suites by designated testers and test leads.

![](Images/TPTesthub.png)

### Terminology

**Test plans** - group test suites and individual test cases together. Test plans include static test suites, requirement-based suites, and query-based suites.

**Test suites** - group test cases into separate testing scenarios within a single test plan. Grouping test cases makes it easier to see which scenarios are complete.

**Test cases** - validate individual parts of your code or app deployment. You can ensure your code works correctly, has no errors, and meets business and customer requirements. You can add individual test cases to a test plan without creating a test suite, if you wish. More than one test suite or test plan can refer to a test case. You can effectively reuse test cases without needing to copy or clone them for each suite or plan.

After you create your test plan, you assign test configurations and assign testers to cover the required test matrix. These testers run the tests and gauge the quality of the product. Testers continue testing until the product meets exit criteria. For the next development cycle and release, you can create a new test plan and reuse the same test cases. You repeat this development-test-release cycle by importing the same test cases into each new test plan.

Because test plans refer to test cases, updates to a test case automatically reflect in all the test plans and test suites that use it.

There are three types of Test Suites that can be created in our test plan

- **Static suite** - these are just containers for a number of test cases
- **Requirement based suite** - identifies relevant test cases related to one or more requirements (user stories)
- **Query based suite** - identifies advanced queries to pull relevant test cases related to work items identified by the query

### Edit Test Case

In part 1 of this lab, we created two test cases linked to the story - but we never filled any information about the test case.

- Open up one of the test cases

![](Images/FPEditTestCase1.png)

- enter a set of steps and what to be expected
- if values need to be entered use @xxxxx e.g. @name , @password
  - then specify the values in parameter values ... each set will need a separate test interation

![](Images/FPEditTestCase2.png)

If a set of steps are going to be commong across a number of test cases, they can be selected and made a reusable "shared steps". For example, an initial logon sequence most likely would be the same for all test cases.

![](Images/FPEditTestCase3.png)

- [Save and Close] the test case

### Manage Test Plans and Test Suites

To manage test plans and test suites, the user must have Test Manager license.
Basic users can execute test cases.

[License requirements](https://docs.microsoft.com/en-us/azure/devops/test/manual-test-permissions?view=azure-devops)

- Go to the Test Plans hub - and select [+New Test Plan]

![](Images/TPTestPlan1.png)

- The test plan will be a container for our test cases for Sprint1

![](Images/TPTestPlan2.png)

- In the test plan, create a [New Suite] - and specify [Requirements based suite]

  ![](Images/TPTestPlan3.png)

- In the query, add a new clause to specify interaction 1
- Run query

![](Images/TPTestPlan4.png)

- This identifies our user story
- Select [Create Suite]

![](Images/TPTestPlan5.png)

This then shows our test cases, to test our user story.

![](Images/TPTestPlan6.png)

### Configuration

Configuration enables us to define the environment required to run a test. By default it shows Windows 10.

![](Images/TPConfig1.png)

We could for example set up separate test config for Windows10+Edge, Windows10+FireFox, etc

![](Images/TPConfig2.png)

![](Images/TPConfig3.png)

Go back to the test plan and assign the configurations to our test cases

![](Images/TPAssignConfig1.png)

![](Images/TPAssignConfig2.png)

Note that additional test cases are created, to create a matrix - each test case for each configuration

![](Images/TPAssignConfig3.png)

### Testers

Next assign the Testers for each test case

![](Images/TPAssignTester1.png)

![](Images/TPAssignTester2.png)

![](Images/TPAssignTester3.png)

Email received:

![](Images/TPAssignTester4.png)

### Test & Feedback Browser Extension

The following Chrome / Edge (Chromium) / Firefox browser extension is required to execute the test cases.

<https://marketplace.visualstudio.com/items?itemName=ms.vss-exploratorytesting-web>

![](Images/TPExtension.png)

![](Images/TPExtension2.png)

When enabled - appears as a button in the top right menu of browser.
Use the CogWheel button to config and make sure it is connected to the Azure DevOps Project

![](Images/TPExtension3.png)

### Execute Test

As the tester

- select the test case and [Run for web application]

![](Images/TPExecute1.png)

The Test Runner is then displayed. It displays each step that the tester must perform and what expected result to check for.

![](Images/TPExecute2.png)

Because we set up two sets of test data - the test runner has 2 interactions.

For each step, the tester must click the tick or cross to indicate iof the expected result did happen.

![](Images/TPExecute3.png)

Once the test is complete - select [Save and close]

The outcome of the test is then displayed in the list of test cases.

![](Images/TPExecute4.png)

### Test History and Monitoring

Select [View Execution History] on the completed test case

![](Images/TPHistory1.png)

![](Images/TPHistory2.png)

Select [View Test Result] on the completed test case

![](Images/TPResult1.png)

![](Images/TPResult2.png)

Select [Chart] and [New Test Result Chart]

![](Images/TPChart1.png)

Experiment with options - for example, create a Pie chart of Outcomes.

![](Images/TPChart2.png)

![](Images/TPChart3.png)

![](Images/TPChart4.png)

![](Images/TPDashboard1.png)

Select [Progress report] in the Test hub menu. We can see the one test successfully executed.

![](Images/TPProgress.png)

Select the [ Runs] in the Test hub menu. Again - we can see the one test execute.

![](Images/TPRuns.png)

### Raise a bug

Do another test execution - but this time, lets raise a bug.

![](Images/TPBug1.png)

- Add a comment
- Click the camera icon to add a screenshot
- Select the area of interest
- Select the Tick to save the image

![](Images/TPBug2.png)

The image is incorporated in to the test execution record.

![](Images/TPBug3.png)

- Select the button to fail the test

![](Images/TPBug4.png)

- Click [Create Bug] icon

![](Images/TPBug5.png)

A Bug WorkItem dialog is displayed for the bug to be created. Note that the whole test excution information is included, including the screenshot and the system information.

- Enter a Bug title and [Save & Close]

![](Images/TPBug6.png)

- [Save & Close] the test runner

The failure is reflected in the Dashboard and Progress Report

![](Images/TPBug7.png)

![](Images/TPBug8.png)

Check the Kanban board - we see the bug (associated with the Story) and the test failures

![](Images/TPBug9.png)

The Bug appears in the list of Work Items

![](Images/TPBug10.png)

---

[Home](README.md) | [Prev](azuredevops-2.md) | [Next](azuredevops-4.md)
