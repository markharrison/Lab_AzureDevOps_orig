# Azure DevOps - Hands-on Lab Script

Mark Harrison : 26 March 2020

![](Images/devops.png)

- [Part 1 - Create Project / Application](azuredevops-1.md) ... this document
- [Part 2 - Development](azuredevops-2.md)
- [Part 3 - Test Plans](azuredevops-3.md)

## Overview

Azure DevOps provide rich and powerful tools everyone in the team can use to drive quality and collaboration throughout the development process. The easy-to-use, browser-based test management solution provides all the capabilities required for planned manual testing, user acceptance testing, exploratory testing, and gathering feedback from stakeholders.

## Create Project / Application sample

Use Azure DevOps Projects <https://portal.azure.com/#blade/HubsExtension/BrowseResource/resourceType/microsoft.visualstudio%2Faccount%2Fproject>

- Create a .NET project ... suggest use Windows AppService F1 free tier
  - Choose `.NET` | [Next]
  - Choose `ASP.NET Core` | [Next]
  - Choose `Windows Wep App` | [Next]
  - Enter details - webapp name must be unique, use local regions
  - Use the [Additional Settings] - select F1 free tier
  - [Done]

![](Images/TPCreate1.png)

When the project has provisioned, the following has happenend:

- a sample application is stored in a Azure DevOps repo
- infrastructure as code ARM template is stored in the same Azure DevOps repo (different top level folder)
- build and release pipelines are generated, and invoked
- an Azure DevOps Project dashboard is generated.

![](Images/TPCreate2.png)

Note on the Azure DevOps Project dashboard links to the AzureDevs homepage, repos, pipelines and boards.

![](Images/TPCreate3.png)

## Pipelines - Automated Testing

Also note on the Azure DevOps Project dashboard that the pipelines did some automated testing.

In the Build pipeline there was one unit test executed and this passed successfully.

![](Images/TPBuild1.png)

![](Images/TPBuild2.png)

![](Images/TPBuild3.png)

![](Images/TPBuild4.png)

Also in the Release pipeline, there was one functional test executed and this passed successfully.

![](Images/TPRelease1.png)

![](Images/TPRelease2.png)

![](Images/TPRelease3.png)

## Amend Pipelines

Make the following change to the Release pipeline ... this will be useful later.

- Select [Edit]

![](Images/TPEditRelease1.png)

- Select [Options]

![](Images/TPEditRelease2.png)

- Enable the Integrations :

  - Report deployment status to the repository host
  - Report deployment status to Work
  - Report deployment status to Boards
  - Enable the deployment status badge

- [Save]

![](Images/TPEditRelease3.png)

## Create WorkItems

Next we will create a User Story with two Tasks and two Test Cases.

- Go to WorkItems
- Create Story

![](Images/TPCreateStory1.png)

![](Images/TPCreateStory2.png)

- Go to Boards

![](Images/TPCreateStory3.png)

- Create two tasks:

![](Images/TPCreateTask1.png)

![](Images/TPCreateTask2.png)

- Create two test cases:

![](Images/TPCreateTestCase1.png)

![](Images/TPCreateTestCase2.png)

- Move story to Active

![](Images/TPStoryActive.png)

- Goto Backlogs
- Move story to Sprint1

![](Images/TPStorySprint1.png)

![](Images/TPStorySprint2.png)

## Summary

In this section we create our DevOps project and set up some work items.

In the next section we shall take on the persona of a developer, and make some code changes that relate to the work items.

---

[Home](README.md) | [Next](azuredevops-2.md)
