
Migrate the SSIS catalog to the new server quickly using SSIS Catalog Migration Wizard. 

Do you want to:
* migrate SSIS to Azure Data Factory SSIS Integration runtime.
* migrate SSISDB from one server to another
* migrate SSIS catalog from SQL Server 2012 to SQL Server 2022 (or any version of SQL Server).
* migrate SSIS catalog environment variables from DEV to UAT etc.
* automate routine SSIS catalog migrations.

Then you are at the right place!

{% include youtubePlayer.html id="t2h6xNVFQkc" %}

# Background

From SQL Server 2012 onwards, Microsoft introduced a new deployment model in SSIS called the project deployment model. This new model has many benefits in managing SSIS project deployments, executions, and configurations. With every new version of SQL Server, the SSIS Catalog is also getting upgraded with new features. In this article, I will describe how we can migrate the SSIS Catalog from one SQL Server instance to another using the SSIS Catalog Migration Wizard.

The SSIS Integration Services Catalog consists of the following artifacts:

* SSIS Builds (.ispac files) - Contains several SSIS packages with project and package parameters.
* Environments - Stores configurations of SSIS projects. These variables are used to configure the SSIS project and package parameters of SSIS projects.

This quick utility will help you migrate the SSIS catalog in just a few clicks.
# SSIS Catalog Migration Wizard

Once installed, you can launch the SSIS Catalog Migration Wizard from SQL Server Management Studio (SSMS 18, 19), Visual Studio 2017, Visual Studio 2019 or Visual Studio 2022. Alternatively, you can use it as a standalone tool. The welcome screen for the wizard is shown below:

<img src="media/Main.png" width="500">

[<img src="media/Download.PNG" width="150">](https://azureops.org/product/ssis-catalog-migration-wizard-pro/)

The wizard supports the following source and target types.

* SSIS for SQL Server - SSIS catalog enabled in SQL Server. 

* SSIS for Azure Data Factory - This is used when running SSIS packages in Azure using Azure data factory pipelines.

* SCMW export - This is a unique export format for SSIS Catalog items.

# Demo - Let's Migrate On-premise SSIS to Azure SSIS! 

We will now see how SSIS Catalog Migration Wizard migrates on-premises SSIS Catalog in SQL Server to SSIS in Azure Data Factory in just a few clicks. I also have a video demo available to watch.

To start, launch the wizard from your preferred location.

**Choose Source** 

Choose the SQL Server radio button and then provide the SQL Server instance name. To perform operations on the SSIS catalog, we have to use Windows Authentication, and the user running this should have the ssis_admin role.

<img src="media/ChooseSource.PNG" width="500">


**Choose Target**

Choose the Azure data factory radio button for the target. Provide the Azure SQL Server hostname, admin SQL server authentication user name, and password.

<img src="media/ChooseTarget.PNG" width="500">

Note: This utility only supports SQL authentication for the Azure SQL Server connection.

**Select SSISDB Catalog Items to Migrate**

Choose the catalog items from the treeview.

<img src="media/ChooseItems.gif" width="500">

***Compare source & target***
Compare source and target and choose to migrate only what has changed.
For example, in the above image:
* Green items are present in the source and not present in the target,
* Red items mean source and target items are not the same.
* Unmodified items are displayed in the original color, and these objects are identical in the source and target

***Migration Type***
Migration types are ‘copy’ and ‘move’. Select the’ move’ radio button to delete the source catalog after the migration. The default type is ‘copy’.

***Migrate explicit permissions***
Catalog folders, projects, and environments have explicit permissions. To migrate these permissions to the target, check the ‘Migrate explicit permissions' checkbox screen.

**Customize folder mapping**

Easily map source and target its permissions' checkbox folder names. The wizard populates all selected folder names in the Source and Target folder columns. If you wish to customize the folders, edit the value in the ‘Target Folder’ column.

<img src="media/CustomizeFolders.png" width="500">

For instance, as shown in the above image, the wizard will copy the content of the source catalog folder Pqr to the target catalog folder Abc. This step is optional.

**Would you like to replace your environment variable values while you are on your way?**

Configure the key-value pairs you want to replace in the environment variable and parameter values. Suggest button will list suggestions for replacing values based on the selected Replace Scope. Click on the Ref column to view the affected environment variables and parameters in the image below.

<img src="media/ReplaceVariables.gif" width="500">

Perhaps, this is useful when setting up a parallel environment for your ETL workload, and some configuration is different in the target environment. This configuration is optional.

***Overwrite environment variable values***
The ‘Overwrite environment variable values’ setting recreates environment variables and parameter default values in the target. Note here that you may lose target data in this case.

***Export sensitive data***
This setting applies to exporting SSIS Catalog to the SCMW file.SCMW export file is not encrypted—whenThe ‘Export sensitive data’ setting exports sensitive information in the export file as free text.

**Complete the Wizard**

<img src="media/Review.png" width="500">

***Automation (Command-line utility)***
With the command-line utility, we can automate routine migrations in a few clicks. The migration script can run using any scheduler like SQL Server Agent job. Here, the Script button at this step will generate a command-line script based on the choices made in previous actions.

For example, the command-line script will look like the below in the current case.

    SSIS.Cataloger.Pro.exe /st:0 /ssn:SQLServerInstance /tt:1 /tsn:azuresql.database.windows.net /items:”[{"FolderName":"Azure test","Projects":[],"Environments":["env1"]},{"FolderName":"AzureDevOpsDeployment","Projects":["testUC"],"Environments":[]},{"FolderName":"Sales","Projects":["sales-stg2"],"Environments":[]}]” /fm:”{"Azure Test":"Azure Prod"}” /fm:”{"Pqr":"Abc"}” /oev:true

More information about the command-line utility parameters and usage examples is available [here](https://azureops.org/articles/ssis-catalog-migration-wizard-pro/#Automation).Review the deployment summary. And if everything looks ok, click Finish.


**Monitor the migration**

<img src="media/Finish.png" width="500">

Any warning or error during the migration gets shown next to the respective folder in the Result column tooltip of the grid. The success items are all noted as "Passed" in the above image.

