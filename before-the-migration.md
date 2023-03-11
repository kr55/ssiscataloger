---
layout: page
title: Before the Migration
permalink: /before-the-migration/
---
Before you begin to use SSIS Catalog Migration Wizard for your first ever 
migration, you need to ensure that:
1. SSISDB in the target SQL Server Integration Services Catalog already 
exists. If it does not exist, you can create a new under the Integration 
Service Catalog on target SQL server. 
Note: Restoring an existing SSISDB on the target SQL Server may result 
in unexpected errors during or after the migrations.
2. You can inspect your SSIS Catalog to ensure consistency in the source 
SSISDB. The inspection result will provide details about possible 
errors or warnings. It is advisable to fix them before you run the 
migration. Follow this tutorial to know more.
3. Make sure that the user running the wizard has the ssis_admin role on both 
source and target SSISDB.