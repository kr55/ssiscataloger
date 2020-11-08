---
layout: page
title: Download
permalink: /download/
---

Download and follow the instructions from  [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=KunalRathi.ssiscatalogmigrator). 

**If you have SQL Server Data Tools for Visual Studio 2017 (SSDT) installed and want to use this tool from there:**

1.Download the tool from **Extensions and Updates** under the **Tools** menu item as shown in the image below..
<img src="../media/VSMarketPlaceDownload.png" width="700"> 
2.Restart SSDT 2017 and you should see the tool under the **Tools** menu item.
A good part of this option is that you automatically get an update installed in SSDT whenever a newer version of the wizard is available in the marketplace. Isn’t that great!

**If you have SQL Server Management Studio 2018 (SSMS 2018) installed and want to use this tool from there:**
As the VSIX 2017 installer does not support installation into a VS Shell edition, and generally because SSMS extensions are unsupported, You will have to manually install the extension.
1. Download the latest vsix plugin from this page.
2. Unzip the downloaded file SSIS.Catalog.Migration.Extension.vsix to a folder named 'SSIS Catalog Migrator' using [7zip](https://www.7-zip.org/download.html).
3. Copy this folder ('SSIS Catalog Migrator') to C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\Extensions location. You would need administrative permissions to do this.
4. Restart SSMS 2018 and you should see the tool under the Tools menu item.

**If you don't wish to use this with either of the above tools, you can use it directly.**
1. Download the latest vsix plugin from this page.
2. Unzip the downloaded file SSIS.Catalog.Migration.Extension.vsix to a folder named 'SSIS Catalog Migrator' using 7zip.
3. Place this folder at a preferred location.
4. Double click the file 'SSIS.Catalog.Migration.exe'. You can also create a shortcut for this file and use it.


