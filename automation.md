---
layout: page
title: Automation
permalink: /automation/
---

With the SSIS Catalog Migration Wizard (SCMW) command-line utility, you can automate routine migrations in a few clicks. The migration script can be integrated with any scheduler or CI-CD tool.

Watch this quick video to learn more.
{% include youtubePlayer.html id="uQ0oc8mEuUs" %}

For example, the command-line script will look like the below in the current case.

    SSIS.Cataloger.Pro.exe /st:0 /ssn:SQLServerInstance /tt:1 /tsn:azuresql.database.windows.net /items:”[{"FolderName":"Azure test","Projects":[],"Environments":["env1"]},{"FolderName":"AzureDevOpsDeployment","Projects":["testUC"],"Environments":[]},{"FolderName":"Sales","Projects":["sales-stg2"],"Environments":[]}]” /fm:”{"Azure Test":"Azure Prod"}” /fm:”{"Pqr":"Abc"}” /oev:true

More information about the command-line utility parameters and usage examples is available [here](https://azureops.org/articles/ssis-catalog-migration-wizard-pro/#Automation). 
