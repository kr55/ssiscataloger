---
layout: page
title: Frequently Asked Questions
permalink: /faq/
---
### What all source and target SQL Servers are supported for migration of SSISDB.

SSIS Catalog Migration Wizard supports migration of SSISDB between SQL Server 2012, 2014, 2016, 2017, 2019, 2022, ADF SSIS IR, and Azure SQL MI. It is recommended to only migrate SSIS catalog from lower to higher versions of the SQL Server as features in SSIS may not be backward SQL server version compatible. 

### Does this tool migrates SSIS environment references?
SSIS Catalog Migration Wizard migrates environment variable and project/package parameter server-side values from source to target SSISDB. You can also update their values during the migration using a proactive recommendation process.

### How many seats are available in one license?
All SSIS Catalog Migration Wizard license editions offer multi-seat access and grant access to all the users on the server or computer where it is installed.

### How many licenses do I need to buy for my SSISDB migration?
You can migrate SSISDB between any SQL Servers from the server where the tool is installed. So, if your source and target SSISDB can be connected from a single server, you would need only a single license.

### We are an educational institute or non-profit organization. Can we get any offer or discount on the license?
We offer exclusive discounts to educational institutes and non-profit organizations. To check the offer, write an email to support@azureops.org from your official email address. The offer will be tagged to the official email address and can only be availed when using the email as the billing address.

### I am planning to purchase multiple licenses at the same time. Can I get a discount?
We offer discounts to our customers planning to acquire more than two licenses simultaneously. To check the latest offer, write an email to support@azureops.org
with your requirements. The offer code will be delivered to you based on your purchase plan.

### Is there a limited feature free trial available?
SSIS Catalog Migration Wizard has a limited feature trial version. the LFT version can migrate the first three SSIS projects (.ispac files) from source to target SSISDB without environment variable configurations. If you want to try this before purchasing the full version, email support@azureops.org or chat with our support from the product page.

### Does SSIS Catalog Migration Requires an internet connection to work?
SSIS Catalog Migration Wizard is an offline tool; hence, it does not require the internet to work. The Installer of the tool interacts with our license server only once.

### My source and target SSISDB are in different network/domain, and they do not have a direct connection. Will SSIS Catalog Migration Wizard work in this case?
SSIS Catalog Migration Wizard offers .scmw file (an export format for SSISDB items). You can achieve SSISDB migrations across different domains. Export the source SSISDB in .scmw file using SSIS Catalog Migration Wizard. Copy this file to the target server or computer where you have access to the target SQL Server (SSISDB). Import the scmw file to target SSISDB using SSIS Catalog Migration Wizard. Please note that you need to install SSIS Catalog Migration Wizard in source and target network machines.

### What has been included in the software package?
You will receive an email with a download link to the product and an activation key. Once you download the zip file after the purchase, you will get an installer to install and activate the software, installation guide, and product documentation file. 

### I am facing issues with the migration; how can I get help?
AzureOps support team offers dedicated support to SSIS Catalog Migration Wizard users. You can contact a support agent from the product page live chat or email support@azureops.org with the problem statement.

### What payment options are available?
We currently only accept payment via PayPal. If you do not have a PayPal account, PayPal generally offers to use a credit card without creating an account. However, this differs based on your country of origin. Check out PayPal [privacy policy](https://azureops.org/privacy-policy/). Reach out to our support in case of any payment issues.
 
### Does this tool comes with a refund policy?
SSIS Catalog Migration Wizard migrates SSIS Catalog from one server to another in just a few clicks. If it does not work for you and you wish to get the refund of your purchase, you can claim it within three days of the purchase. Check out our [refund policy](https://azureops.org/refund_returns/) for more details.

