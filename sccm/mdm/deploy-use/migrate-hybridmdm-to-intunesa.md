---
title: Migrate hybrid MDM users and devices to Intune standalone
titleSuffix: "Configuration Manager"
description: "Learn how to migrate hybrid MDM users and devices to Intune on Azure."
keywords:
author: dougeby
manager: angrobe
ms.date: 09/12/2017
ms.topic: article
ms.prod: configmgr-hybrid
ms.service:
ms.technology:
ms.assetid: 1dd696ce-3e46-4dfa-a76d-592fe0f0320e
---

# Migrate hybrid MDM users and devices to Intune standalone

*Applies to: System Center Configuration Manager (Current Branch)*    

When you have decided that you are ready to start migrating from hybrid MDM (Intune integrated with Configuration Manager) to a cloud-only experience using Intune on Azure, this is the article is for you. If you are still unsure, see [Choose between Microsoft Intune standalone and hybrid mobile device management with System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management). 

You can start migrating to Intune standalone using a phased approach that allows you to test a small subset of users and devices while most of your users and devices are still managed with hybrid MDM. Then, after you verify Intune functionality, you can start migrating more users to Intune.    

The following topics provide the steps to migrate your users to Intune standalone using a phased approach.    
  
1.	[Import Configuration Manager data to Microsoft Intune](migrate-import-data.md)   
    The Intune Data Importer tool collects data about the objects you select from your Configuration Manager hierarchy, provides details about the objects you can select for import and information about why some object cannot be imported, and lets you import selected objects into your Microsoft Intune tenant. While this step is optional, it can save you much time by automating the process to recreate objects from Configuration Manager to Intune. 
2.	[Prepare Intune for user migration](migrate-prepare-intune.md)    
    Validate imported objects from Configuration Manager, create new objects, create AAD groups and make object assignments to these groups, install NDES and Exchange connectors, etc. When you complete the steps and start the migration to Intune standalone, it should be transparent to your users.  
3.	[Change the MDM authority for specific users (mixed MDM authority)](migrate-mixed-authority.md)    
    Configure a mixed MDM authority in the same tenant by selecting some users to be managed in Intune and while all other devices continue to be managed with hybrid MDM (Intune integrated with Configuration Manager). You can test that Intune functionality is working as expected on the devices for a small subset of users before you start migrating additional users. 
4.	[Change your MDM authority to Intune standalone](change-mdm-authority.md)     
    Change your tenant-level MDM authority from Configuration Manager to Intune. All remaining users and devices are migrated to Intune standalone. You will change your tenant-level MDM authority after you have thoroughly tested Intune functionality in the previous step and have likely migrated most or all of your users already.