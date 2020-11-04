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

## Sources & Targets

It supports the following source and target types. 
SSIS for SQL Server - SSIS catalog enabled in SQL Server. 

SSIS for Azure Data Factory - This is used when you want to run SSIS packages in Azure using Azure data factory pipelines. 

File System - SSIS Catalog exported to the file system. This can be used as a staged migration when you don't have acess to source and target SQL server connection at the same time.

We'll see a quick demo on how to migrate SSIS Catalog from on-premise SQL Server to SSIS in Azure Data Factory.

### Choose Source 
Choose SSIS in SQL Server from Source Type drop-down.

<img src="media/Choosesource.png" :height="50%" width="50%">

![this screen](/media/Choosesource.png)

![Image](https://github.com/kr55/ssiscataloger/blob/master/media/Choose%20Target.png)



Provide SQL Server instance name. 
To perform operations on SSIS catalog, we have to use windows authentication. And user should have ssis_admin role.  

### Choose Target
Choose SSIS in Azure Data Factory from the Target Type drop-down. 

<img src="https://github.com/kr55/ssiscataloger/blob/master/media/Choose%20Target.png" :height="50%" width="50%">

Provide Azure SQL Server hostname, admin SQL server authentication user name, and password.
Note: This utihttps://github.com/kr55/ssiscataloger/blob/master/media/Choose%20Target.pnglity only supports SQL authentication for Azure SSIS at the moment. 

### Select SSISDB Catalog Folders to Migrate

![](https://github.com/kr55/ssiscataloger/blob/master/media/Choose%20Target.png)

Choose the catalog folders from the listview you want to migrate. 

Migrate Projects : Select the checkbox if you want to migrate SSIS projects (.ispac) files from the selected list of folders.
Migrate Environments, project and package parameter configurations : Select the checkbox if you want to migrate catalog Environments. This will also apply environment references to SSIS projects and parameter mapping. If there are server side default values set for some project or package parameters, those will also be migrated to target server.

### Replace Parameter and Environment Values

If you wish to replace environemnt variable, project or package parameter values with new values, configure the replacement rules in this screen.

![](https://github.com/kr55/SSISCatalogMigrator/blob/master/media/Replace%20Values.png)

As showen in the image above, all the connection string values will be updated from Data Source-Server1 to Data Source-Server2 & User ID=user1 to User ID=user2.

This is an optional step. If you dont want to replace anything, you can skip this step by clicking Next.

 
### Complete the Wizard

Review the deployment summary. And if everything looks ok, click Finish.

![](https://github.com/kr55/SSISCatalogMigrator/blob/master/media/migration%20summary.png)


### Monitor the migration

Monitor the migration.

![](https://github.com/kr55/SSISCatalogMigrator/blob/master/media/Migration%20finish.png)

If there is any warning or error during the migration, it will be shown against the respective folder in the status column of the grid.
Note: Sensitive environment variables, project or package parameter values are encrypted in SSISDB with master key. Hence, such values cannot be copied in this migration. However, such variable/parameter names will be listed in status column tooltip and the status value will be shown as a warning.
You can also save migration reports in CSV format by clicking on Save Report.







## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/kr55/ssis-catalog-migrator/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/kr55/ssis-catalog-migrator/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
