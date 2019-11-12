---
layout: post
title: "Pull Requests taking over Azure"
categories: "Azure DevOps, Azure"
author: "Venura Athukorala"
meta: "Azure, Azure DevOps, Microsoft, GitHub Actions"
---

If you’ve not been in Microsoft’s eco-system in the recent few years, it’s something that’s hard for many to digest the amount of changes made to Microsoft’s offerings. Considerable efforts have been made to make the cloud tool set more developer friendly. With the acquisitions such as GitHub and number of open source initiatives Microsoft is trying to change how they are viewed by most of the developers. 

One of the key tooling in the mix is Azure DevOps. While there are other cloud agnostic solutions in play, Azure DevOps has been the front runner for anything azure in the recent years, mainly due to the tight native and 3rd party integrations as well as the extended set of features such as the Boards, Artifacts, Test Plans and Repositories which enables end-to-end software development. 

Operations by pull-request has been in discussion for a while now. Words such as GitOps came to use mainly related to Infrastructure running Kubernetes where the infrastructure orchestration and the CI/CD was based and controlled around a git repository(s).  Azure DevOps made GitOps a reality for any deployment with the enhancements they made to their YAML based pipeline experience. 

Being a developer at heart, with a DevOps background, these changes made me jump straight into the band wagon of expressing everything as code. Azure DevOps initially had the CI (Continuous Integration) and CD (Continuous Deployment) addressed as two separate sections which was called Build and Deploy in the previous sprints/versions of Azure DevOps. With the introduction of the pipelines initiative everything became a set of pipelines. While the feature set required to enable end-to-end CD did take a lot longer than expected, it’s now at a stage which allows the creation of production ready “Everything as Code” projects. 

My recent meetup [presentation](https://github.com/venura9/azure-devops-yaml) covered an end-to-end solution which was completely version controlled including the application source code, infrastructure as well as the actual deployment pipelines themselves, which Microsoft refers as configuration as code in certain documentations. Post the meetup the azure DevOps team added the final missing features as a part of [Sprint 158](https://docs.microsoft.com/en-us/azure/devops/release-notes/2019/sprint-158-update#enhancements-to-approvals-in-yaml-pipelines) to enable [Approvals](https://docs.microsoft.com/en-us/azure/devops/release-notes/2019/sprint-158-update#enhancements-to-approvals-in-yaml-pipelines) and [Retries](https://docs.microsoft.com/en-us/azure/devops/release-notes/2019/sprint-158-update#retry-failed-stages) for Multi-Stage,the concept which enables end-to-end pipelines, making pipelines ready for production use. 

The next two iterations added the finetuning around these features making the feature more robust with features such as [Approval policies for YAML pipelines](https://docs.microsoft.com/en-us/azure/devops/release-notes/2019/sprint-160-update#approval-policies-for-yaml-pipelines)
 
This is great, looks cool, what does it bring into my organisation?

*Principle of least privilege*

For most of the users they would require no or read-only access to azure and azure devops, once setup all the changes are in version control and it’s yet another Pull-Requests. 

*Better DevOps and DevSecOps*

DevOps will soon go beyond from being a buzz word and you can reap higher benefits by going DevOps as a single tool acting as the all-in-one package. 

Different areas of the source code can have different policies allowing different combinations of individuals and teams review the changes depending on the area of the source code. Including how the deployments and infrastructure changes are orchestrated and approved. With the use of correct tech-stack the secrets will be actually be secrets allowing the development teams to focus on what they do.


###What’s GitHub Actions, Isn’t that Similar?

Yes, Microsoft own GitHub. They’ve done a good job with the move not adding the Microsft name to everything not many projects found different homes as predicted before. Why not spread the goodness beyond Azure DevOps and Azure, now you have GitHub actions providing similar features for many-a-clouds including AWS and GCP.
