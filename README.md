# DevOps Showcase Repository

Welcome to the DevOps Showcase Repository! This repository serves as an educational resource to showcase your abilities in DevOps and cloud technologies. It demonstrates the setup of a sample C# application and its deployment using Azure DevOps and various cloud services.

## Repository Structure

The repository is organized into several template files that represent different stages of the deployment pipeline. Each template file contains code and instructions specific to that stage. Here's a brief overview of the template files:

- [clean_source_dir.yml](templates/clean_source_dir.yml): Cleans the source directory and clones the source code repository.
- [main.yml](main.yml): Builds, tests, publishes, and deploys the application.
- [detect_source_branch.yml](templates/detect_source_branch.yml): Detects the source branch of the code repository.
- [build_releaseapp_from_pr.yml](templates/build_releaseapp_from_pr.yml): Builds and tests the application from a pull request.
- [detect_change.yml](templates/detect_change.yml): Detects changes in the code repository.
- [run_app.yml](templates/run_app.yml): Runs the application.
- [merge_build_step.yml](templates/merge_build_step.yml): Merges the build branch into the main branch.
- [set_variables.yml](templates/set_variables.yml): Sets the required variables for the pipeline.
- [compile_app.yml](templates/compile_app.yml): Compiles the C# application.
- [save_app_to_blob.yml](templates/save_app_to_blob.yml): Uploads the application to Azure Blob Storage.
- [package_Apprunner_to_reg.yml](templates/package_Apprunner_to_reg.yml): Builds and pushes the Docker image to Azure Container Registry.
- [dummy.yml](templates/dummy.yml): Placeholder template for running the app on a target database.

## Getting Started

To utilize the DevOps Showcase Repository effectively, follow these steps:

1. **Set Variables**: Open the `set_variables.yml` file and set the necessary variables such as `sourceDirectory`, `buildConfiguration`, `storageAccountName`, `containerName`, and `registryName`. Customize the values to align with your Azure resources and requirements.

2. **Configure Azure DevOps Pipeline**: Create a new pipeline in Azure DevOps and configure it to use this repository. The pipeline should reference the appropriate template files for each stage. Here's an example pipeline configuration:

   ```yaml
   trigger: none
   
   stages:
   - stage: UATIntegrationBuild
     jobs:
     - job: IntegrationRun
       steps:
         - template: templates/clean_source_dir.yml
         - template: main.yml
         # Additional template steps for this stage
   
   # Add more stages as needed
## Customize Pipeline Stages
Customize the pipeline stages in the `main.yml` file to match your deployment requirements. Each stage represents a specific step in the build and deployment process. You can add, remove, or modify stages as needed, incorporating additional Azure services or DevOps tasks.

## Azure Blob Storage Setup
Ensure you have an Azure Storage account and Blob Storage container created. Update the `save_app_to_blob.yml` file with the correct storage account name and container name.

## Azure Container Registry Setup
Make sure you have an Azure Container Registry provisioned. Update the `package_Apprunner_to_reg.yml` file with the appropriate registry name.

## Run the Pipeline
Trigger the pipeline manually in Azure DevOps to initiate the build, test, and deployment process. Monitor the pipeline's execution and review the logs for any errors or warnings.

## Additional Resources
Here are some additional resources to help you with Azure DevOps and the cloud services used in this repository:

- [Azure DevOps Documentation](https://docs.microsoft.com/azure/devops/): Official documentation for Azure DevOps.
- [Azure Blob Storage Documentation](https://docs.microsoft.com/azure/storage/blobs/): Official documentation for Azure Blob Storage.
- [Azure Container Registry Documentation](https://docs.microsoft.com/azure/container-registry/): Official documentation for Azure Container Registry.
- [Microsoft Learn](https://learn.microsoft.com/): Comprehensive learning platform for Azure and DevOps topics.
- [GitHub Docs](https://docs.github.com/): Official documentation for managing repositories and workflows.

Enjoy showcasing your DevOps and cloud skills with this repository!
