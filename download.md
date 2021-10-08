---
layout: page
title: How to Install
permalink: /download/
---

{% include youtubePlayer.html id="Dylw06FigY" %}


**If you have SQL Server Data Tools for Visual Studio 2017 (SSDT 2017) installed:**

1. Download the extension from **Extensions and Updates** under the **Tools** menu item as shown in the image below..
<img src="../media/VSMarketPlaceDownload.png" width="700"> 

2. Restart SSDT 2017 and you should see the tool under the **Tools** menu item.

A good part of this option is that you automatically get an update installed in SSDT whenever a newer version of the wizard is available in the marketplace. Isn’t that great?

**If you have SQL Server Management Studio 2018 (SSMS 2018) installed:**

As the VSIX 2017 installer does not support installation into a VS Shell edition, and generally because SSMS extensions are unsupported, You will have to manually install the extension.
1. Download the latest vsix plugin from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=AzureOps.ssiscatalogerpro). 
2. Unzip the downloaded file SSIS.Cataloger.Extension.vsix to a folder named 'SSIS Cataloger' using [7zip](https://www.7-zip.org/download.html).
3. Copy this folder ('SSIS Cataloger') to *C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\Extensions* location. You would need administrative permissions to do this.
4. Restart SSMS 2018 and you should see the tool under the Tools menu item.
<img src="../media/SSMSoption.jpg" width="700"> 

**If you don't wish to use this with either of the above tools, you can use it directly.**

1. Download the latest vsix plugin from Visual Studio Marketplace.
2. Unzip the downloaded file SSIS.Cataloger.Extension.vsix to a folder named 'SSIS Cataloger' using 7zip.
3. Place this folder at a preferred location.
4. Double click the file 'SSIS.Cataloger.exe'. You can also create a shortcut for this file and use it.


