# Introduction

From SQL Server 2012, Microsoft has introduced a new deployment model in SSIS called the project deployment model. This new model has great benefits in terms of managing SSIS project deployments, executions, and configurations. With every new version of SQL Server, SSIS Catalog is also getting upgraded with new features. In this article, I will describe how we can migrate our existing SSIS Integration Services Catalog from one SQL server to another.  

SSIS Integration services catalog consists of the following artifacts:
SSIS Builds (.ispac files): Contains several SSIS packages with project and package parameters.
Environments (Typically used to store configurations of your SSIS projects). These variables are used to configure the SSIS project and package parameters of SSIS projects.

**The need for this activity might arise when:**
* you are migrating your SQL server to a new server. 
* upgrading the SQL server to a new server on a separate machine.
* setting up a new SSIS environment from the existing setup, etc.

This quick utility will help you migrate your existing SSIS catalog in a few clicks. 

# How to install

Download and follow the instructions from  [visualstudio marketplace](https://marketplace.visualstudio.com/items?itemName=KunalRathi.ssiscatalogmigrator) 

# About the wizard

This quick wizard once installed, can be launched from SQL Server Management Studio (SSMS) 2018 or SQL Server Data Tools (SSDT) 2017 for Visual Studio 2017. Alternatively, you can use it as a standalone tool if you don't wish you add it as a plugin. 

<img src="media/Welcome.png" width="500">

## Sources & Targets

It supports the following source and target types. 

**SSIS for SQL Server** - SSIS catalog enabled in SQL Server. 

**SSIS for Azure Data Factory** - This is used when you want to run SSIS packages in Azure using Azure data factory pipelines. 

**File System** - SSIS Catalog exported to the file system. This can be used as a staged migration when you don't have acess to source and target SQL server connection at the same time.

We'll see a quick demo on how to migrate SSIS Catalog from on-premise SQL Server to SSIS in Azure Data Factory.

### Choose Source 
Choose SSIS in SQL Server from Source Type drop-down.

<img src="media/ChooseSource.png" width="500">

Provide SQL Server instance name. 
To perform operations on SSIS catalog, we have to use windows authentication. And user should have ssis_admin role.  

### Choose Target
Choose SSIS in Azure Data Factory from the Target Type drop-down. 

<img src="media/ChooseTarget.png" width="500">

Provide Azure SQL Server hostname, admin SQL server authentication user name, and password.
Note: This utihttps://github.com/kr55/ssiscataloger/blob/master/media/Choose%20Target.pnglity only supports SQL authentication for Azure SSIS at the moment. 

### Select SSISDB Catalog Folders to Migrate

<img src="media/ChooseCatalogFolders.png" width="500">

Choose the catalog folders from the listview you want to migrate. 

Select Catalog options:

**Migrate Projects** - Select the checkbox if you want to migrate SSIS projects (.ispac) files from the selected list of folders.

**Migrate Environments, Project and Package parameter configurations** - Select the checkbox if you want to migrate catalog Environments. This will also apply environment references to SSIS projects and parameter mapping. If there are server side default values set for some project or package parameters, those will also be migrated to target server.

### Replace Parameter and Environment Values

If you wish to replace environemnt variable, project or package parameter values with new values, configure the replacement rules in this screen.

<img src="media/ReplaceValues.png" width="500">

As showen in the image above, all the connection string values will be updated from Data Source-Server1 to Data Source-Server2 & User ID=user1 to User ID=user2.

This is an optional step. If you dont want to replace anything, you can skip this step by clicking Next.

 
### Complete the Wizard

Review the deployment summary. And if everything looks ok, click Finish.

<img src="media/MigrationSummary.png" width="500">

### Monitor the migration

Monitor the migration.

<img src="media/MigrationFinish.png" width="500">

If there is any warning or error during the migration, it will be shown against the respective folder in the status column of the grid.
Note: Sensitive environment variables, project or package parameter values are encrypted in SSISDB with master key. Hence, such values cannot be copied in this migration. However, such variable/parameter names will be listed in status column tooltip and the status value will be shown as a warning.
You can also save migration reports in CSV format by clicking on Save Report.


