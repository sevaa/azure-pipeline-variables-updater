This is a fork of [Variable Updater](https://github.com/lanalua/azure-pipeline-variables-updater) by Bruno Grillo.

This extension provides a custom build/release task called "Shared Variable Updater" to create or update a
variable in a Azure DevOps project level variable group (library).

**Important: the build/release job needs to have the writing rights
on the variable group to be modified.** The only role with writing rights is the Administrator.
As of Azure DevOps 2019, the jobs run under an artificial identity called 
`Project Collection Build Service ({CollectionName})`. So please grant that one the
Administrator role in the variable group's Security window, or add it to a group with
Administrator rights.

The task identifies variable groups by the internal, numeric ID. You can retrieve it
from the browser query string on the group editing screen; the ID would be in the `variableGroupId`
parammeter.

Variable names are treated as case insensitive, in line with the rest of Azure DevOps.

If the variable is not present in the group, it will be created with the specified value.
Secret variable creation is not supported.
