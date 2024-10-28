# Jenkins Pipeline Setup

This README describes the configuration settings for a Jenkins pipeline to ensure continuous integration (CI) for a project hosted on GitLab or GitHub. This pipeline is designed to validate build stability and monitor changes in the source repository.This pipeline is configured to automatically trigger builds based on changes in a GitLab or GitHub repository. It provides options to handle concurrency, manage credentials, and specify build triggers. Additionally, the pipeline setup allows for speed/durability optimization and stash preservation between builds.

## Prerequisites
   Jenkins:Ensure that Jenkins is installed and accessible.                             
**GitLab/GitHub Access:** API tokens for GitLab and GitHub are required for connection and triggering builds.
**GitLab and GitHub Webhooks:** Set up webhooks in the respective repositories to notify Jenkins of any changes.

### Pipeline Configuration
### General Settings
1. Discard Old Builds: Enable to automatically discard older builds and free up storage.
2. Concurrency Management:
    Do not allow concurrent builds: Ensures only one build is active at a time.
    Do not allow the pipeline to resume if the controller restarts: Stops builds from resuming post-restart.


#### GitHub and GitLab Connections
GitHub Project: Connect to a specific GitHub repository.

GitLab Connection: Use credentials and repository name to link your GitLab repository to Jenkins.

Use Alternative Credential: Specify alternative GitLab credentials if needed.


#### Pipeline Options
Pipeline Speed/Durability Override: Adjust the speed and durability settings as needed.
Preserve Stashes from Completed Builds: Enabling this option retains stashes across builds.

#### Build Triggers
The following triggers can be used to automate builds:

Build after other projects are built: Useful for chaining projects.
Build periodically: Schedule builds at specific intervals.
Build when a change is pushed to GitLab/GitHub:
GitLab Webhook URL: http://localhost:8080/project/Hello%20world
Gitee Webhook URL (if using Gitee): http://localhost:8080/gitee-project/Hello%20world
GitHub Branches: Define branches to monitor for changes.
GitHub Pull Requests: Optional, trigger builds on GitHub pull requests.
GitHub hook trigger for GITScm polling: Poll GitHub for SCM changes.
Poll SCM: Periodically poll the SCM for changes to trigger builds.
Quiet Period: Introduce a delay before builds trigger after changes.



## Pipeline Script

![image](https://github.com/user-attachments/assets/0dbdcc22-d166-42ae-96fb-593adfc18350)

### OUTPUT
![image](https://github.com/user-attachments/assets/679e5acb-f95c-4476-af32-de13edd7cdbe)

