# Continuous Integration/Deployment (CI/CD) tools

## Jenkins
- Free
- Open source build server
- Setup may take longer than other tools, as Jenkins is installed on a build server.
- large open source ecosystem, easy to extend
- Supports MSBuild files, git version etc
- Have to setup and configure it yourself
- Jenkins is a self-contained, open source automation server which can be used to automate all sorts of tasks related to building, testing, and delivering or deploying software.

## Travis CI 
- Differs from Jenkins as it is open source build service
- Easy setup, all you need to do is add a travis.yml file in root
- Integrates with Github.
- https://stackoverflow.com/questions/32422264/jenkins-vs-travis-ci-which-one-would-you-use-for-a-open-source-project

## TeamCity
- CI build Server
- Has free tier, where 20 build resources?
- Easy setup and good user interface

## Bamboo
- CI Build Server
- Costs money - (depending on the number of build agents)
- Integration with Bitbucket, JIRA, hipchat etc. 
- https://stackify.com/jenkins-teamcity-bamboo/

## Azure pipelines
  - Need a DevOps account and organisation (formly VSTS)
  - Build, test, and deploy Node.js, Python,  Java, PHP, Ruby, Go, C/C++, C#, Android, and iOS apps
  - Deploy to cloud providers like Azure, AWS, and GCP.
  - Integrates with the following:
    - Azure Repos Git
    - GitHub
    - Subversion
    - Bitbucket Cloud
    - and External Git.
    - https://docs.microsoft.com/en-us/azure/devops/pipelines/repos/pipeline-options-for-git?view=azure-devops
- **Access restrictions**
  - Be aware of the following restrictions for public projects in Azure Pipelines:
    - Build secrets
      - secrets associated with build pipeline are not made available to pull request builds of forks
    - Cross-project access
      - All builds in Azure DevOps public project run with an access token restricted to the project.
    - Azure artifacts packages:
      - If builds need access to packages from Azure Artifacts, you need to explicitly grant permission.
    - https://docs.microsoft.com/en-us/azure/devops/pipelines/repos/github?view=azure-devops
- **Tasks**
  - A task is simply a packaged script or procedure
  - Tasks run inside jobs
  - When yoiu queue a build or deployment, all the tasks are run in sequence, one after the other, on an agent.
  - You can build custom tasks. See this for example: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/tasks?view=azure-devops&tabs=yaml
- **Release Pipelines**
  - Continously deliver software which is fully automated
  - With release pipelines you can automate multiple stages all the way to production with approvals and on-demand deployments.
  - https://docs.microsoft.com/en-us/azure/devops/pipelines/release/what-is-release-management?view=azure-devops
- **Container jobs**
  - Containers offer a lightweight abstraction over the host operating system.-
  - You can select exact versions of operating systems, tools, and dependencies that your build requires.
  - When you specify a container in your pipeline, the agent will first fetch and start the container.
- **Jobs**
  - Every build or deployment has atleast one job.
  - A job is a series of tasks that run sequentially on the same target.
  - https://docs.microsoft.com/en-us/azure/devops/pipelines/process/phases?view=azure-devops&tabs=yaml
  - Parrallel jobs
    - https://docs.microsoft.com/en-us/azure/devops/pipelines/licensing/concurrent-jobs?view=azure-devops
- **Pricing**
  - Cloud-hosted pipelines for Linux, macOS, and Windows
  - 10 free parallel jobs and unlimited minutes for open source projects.