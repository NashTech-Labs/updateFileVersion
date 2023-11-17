This repository provides a common Azure DevOps pipeline template (`updateFileVersionJSON.yml`) that simplifies the process of updating the version in a JSON file. By using this template, you can easily update your file version of JSON of your Azure pipelines.


### Parameters used
| Name  | type | Default | Values | Optional/Required | Comments |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| Path | string | | | Required | |
| VersionNumber | string | | | Required | |
| useBuildNumberDirectly | string | | | Required | |
| FilenamePattern | string | | | Required | |
| OutputVersion | string | | | Required | |
 

### Usage

To use this template, follow these steps:

1. Include the `updateFileVersionJSON.yml` file in your Azure DevOps repository.

2. In your Azure DevOps pipeline YAML file, add the following code to reference the template:

```yaml
resources:
  repositories:
    - repository: updateFileVersionJSON
      type: github
      name: GitHub
      ref: <respective branch name>
      endpoint: 'GitHUbServiceConnection'
steps:
- template: frameWork/common/pipeline/updateFileVersionJSON.yml@updateFileVersionJSON
  parameters:
      Path: ${{ parameters.filePath }}
      VersionNumber: ${{ parameters.VersionNumber }}
      useBuildNumberDirectly: ${{ parameters.useBuildNumberDirectly }}
      FilenamePattern: ${{ parameters.filenamePattern }}
      OutputVersion: ${{ parameters.outputVersion }}
```
