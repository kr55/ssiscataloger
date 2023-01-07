---
layout: page
title: FAQ
permalink: /faq/
---

## Does SSIS Catalog Migration Requires an internet connection to work?
SSIS Catalog Migration Wizard is an offline tool; hence, it does not require the internet to work. The Installer of the tool interacts with our license server only once.

### How many seats can access the tool from a particular server.
All SSIS Catalog Migration Wizard licenses offer multi-seat access and grant access to all the users on the server or computer where it is installed.

### How many licenses do I need to buy for my SSISDB migration?
You can migrate SSISDB between any SQL servers from where the tool is installed. So, if your source and target SSISDB can be connected from a single server, you would need only a single license.

### My source and target SSISDB are in different network/domain, and they do not have a direct connection. Will SSIS Catalog Migration Wizard work in this case?
SSIS Catalog Migration Wizard offers .scmw file (an export format for SSISDB items). You can achive SSISDB migrations across different domains. Export the source SSISDB in .scmw file using SSIS Catalog Migration Wizard. Copy this file to the target server or computer where you have access to the target SQL Server (SSISDB). Import the scmw file to target SSISDB using SSIS Catalog Migration Wizard. Please note here that you need to install SSIS Catalog Migration Wizard in soruce and target network machines in this case.

### We are an educational institute or non-profit organization. Can we get any offer or discount on the license?
We offer exclusive discounts to educational institutes and non-profit organizations. To check the offer, write an email to support@azureops.org from your official email address. The offer will be tagged to the official email address and can only be availed when using the email as the billing address.

