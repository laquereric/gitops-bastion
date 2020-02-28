GitOpsBastion

GitOpsBastion builds one or mor GitOpsBastionServers that are deployed into hybrid compute environments.

Once deployed, GitOpsBastionServer(s) respond to Git Pull Request events and perform whatever actions are 
required to bring the state of a particular deployment in line with the latest content of the source repository.

  Repository + GitOpsBastion => Deployed System (or Cluster)
    Running on End user owned host(s)
    Holds software licenses
    Holds licensed software
    Granted minimum needed permissions in host environments

GitOpsBastion Features
  fully open-source 
  works with licensed software
  works inside and outside of secure environments
  works in local environments (Macs, Windows, Linux) and in hybrid-cloud environments. 

GitOpsBastion Workflow

1) GitOpsBastion is deployed to a host that is accessible from the repository.
  Configuration is either at time on deployment or later
  Configuration:
    Software licenses
    Licensed software
    Utilities need to operate withing larger environments
      Kubernetes Management (Rancher/Rio)
      MarkLogic Cluster Management

2) One (or more) Repositories are configured (with Webhooks) to send pull request events to the GitOpsBastionServer

3) Pull Requests on the repositories create Events in the GitOpsBastion

4) GitOpsBastion responds to those events

FAQs

What is a host environment?
  A host environment provides the resources needed to run an application.
  A Windows laptop
  A Mac laptop
  A Linux Server running on AWS
  A Linux Server running on Microsoft Azure
  A Linux Server running on the Google Cloud
  A Linux Server running on Digital Ocean 
  
What is GitOps?
  Initial: Repository(Git) + tools and services => Deployed Cluster
  Changes: Developer -> pull request to Repository (Git) branch -> Changed system state
  See https://thenewstack.io/the-tools-you-need-to-run-gitops-based-automated-deployments/
  See https://www.weave.works/blog/what-is-gitops-really

Why is GitOpsBastion needed?
  The GitOps ecossytem fails to meet the needs of:
    Software licences
    Strict security requirents

Implmentation
  https://developer.github.com/webhooks/

Repository Structure
  Docker standard directory structure
    PROJECT_HOME
      Dockerfile
  NOTE: The Dockerfile has dependancies on GitOpsBastion
