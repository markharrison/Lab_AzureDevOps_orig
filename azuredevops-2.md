# Azure DevOps - Hands-on Lab Script

Mark Harrison : 26 March 2020

![](Images/devops.png)

- [Part 1 - Create Project / Application](azuredevops-1.md)
- [Part 2 - Development](azuredevops-2.md) ... this document
- [Part 3 - Test Plans](azuredevops-3.md)

## Development

In this section we will make a code change to address the task work items - this section is optional for those only interested in testing.

### Allocate Developers

- Assign the Tasks to the Developer

![](Images/TPTaskAssign.png)

- In the User Story, create a branch for the development tasks related to this story

![](Images/TPStoryCreateBranch.png)

![](Images/TPStoryCreateBranch2.png)

### Visual Studio set up

Using Visual Studio

- Connect to the Azure DevOps Project

![](Images/TPVisualStudioConnect.png)

- Clone project Repo to desktop

![](Images/TPVisualStudioClone.png)

- Switch view to open application project

![](Images/TPVisualStudioClone2.png)

- Get branch related to Story

![](Images/TPVisualStudioCheckout.png)

- Make sure editing this branch locally - it will be in bold font

![](Images/TPVisualStudioCheckout2.png)

### Developer Coding

- Make a change to the home page welcome message - this is in the /Pages/Index.cshtml file

![](Images/TPVisualStudioCode1.png)

- Make a change to the stylesheet - for example, change the background color ... this file is located in /wwwroot/css/site.css

![](Images/TPVisualStudioCode2.png)

- Check locally the code works - will need to set the default startup project to be the web application

![](Images/TPRunWebApp.png)

- Copy the .GitIgnore file from the Application folder to the level above .. to stop some of the Visual Studio configuration being uploaded into the Repo

![](Images/TPGitIgnore.png)

### Upload changes to Repo

- In Team Explorer, select the Changes view
- Make sure branch is correct ... not the master
- Enter Commit message
- Enter Workitem Ids for the Story and Tasks
- Commit all changes

![](Images/TPCommit1.png)

![](Images/TPCommit2.png)

- Sync

![](Images/TPCommit3.png)

- Push

![](Images/TPCommit4.png)

Repo in Azure DevOps has code changes

![](Images/TPCommit5.png)

### Pipelines Build & Deploy

The build pipeline default configuration is to only start when changes to the master are detected.

- Select [Queue] a Build

![](Images/TPQueueBuild1.png)

- Specify the branch for the Story that has been worked on

![](Images/TPQueueBuild2.png)

![](Images/TPQueueBuild3.png)

![](Images/TPQueueBuild4.png)

Once the Build pipeline has completed, the Release pipeline is started.

![](Images/TPQueueRelease1.png)

![](Images/TPDeployed1.png)

Check the updated App has been deployed to the Dev environment

![](Images/TPDeployed2.png)

### Do Manual Testing

At this stage - we should do our manual testing ... see the [Next](testplans-3.md) part of the lab.

This remaining section of this part of the lab assumes that testing has been completed and no issues are outstanding.

### Merge Code changes to Master

Create a Pull Request to merge the code into the master branch

![](Images/TPPullRequest1.png)

![](Images/TPPullRequest2.png)

- The Pull Request is now approved.

![](Images/TPPullRequest3.png)

![](Images/TPPullRequest4.png)

![](Images/TPPullRequest5.png)

The Story branch has now been merged with the master branch - and the Story branch is then deleted.

The master branch being updated will kick off the Build and Release pipelines.

If we check in the User Story work item, we can see it has been updated with Deployment information showing was deployed to Development

![](Images/TPStoryDeployment.png)

## Summary

In this section we made some development changes - and commited the work back to the Repos, and the application was deployed.

In the next section we shall take on the persona of a tester, and validate that the development did what was required and meets the Test Cases.

---

[Home](README.md) | [Prev](azuredevops-1.md) | [Next](azuredevops-3.md)
