---
title: Set Up and Report Intrastat
description: Learn how to set up Intrastat reporting features, and how to report trade with companies in other EU countries/regions.

documentationcenter: ''
author: bholtorf

ms.prod: "dynamics-nav-2018"
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union 
ms.date: 08/15/2017
ms.author: bholtorf

---
# How To: Set Up and Report Intrastat
All companies in the European Union must report their trade with other EU countries/regions. You must report the movement of goods to the statistics authorities in your country/region every month, and the report must be delivered to the tax authorities. This is referred to as Intrastat Reporting. You use the **Intrastat Journal** page to complete periodic Intrastat reports.  
  
## Required and Optional Setups
Before you can use the Intrastat journal to report Intrastat information, there are several things you must set up:  
  
* **Intrastat journal templates**: You must set up the Intrastat journal templates and batches you will use. Because Intrastat is reported monthly, you must create 12 Intrastat journal batches based on the same template.  
* **Commodity codes**: Customs and tax authorities have established numerical codes that classify items and services. You specify these codes on items.
* **Transaction nature codes**: Countries and regions have different codes for types of Intrastat transactions, such as ordinary purchase and sale, exchange of returned goods, and exchange of non-returned goods. Set up all of the codes that apply to your country/region. You use these codes on sales and purchase documents, and when you process returns.  
* **Transport methods**: There are seven, one-digit codes for Intrastat transport methods. **1** for sea, **2** for rail, **3** for road, **4** for air, **5** for post, **7** for fixed installations, and **9** for own propulsion (for eample, transporting a car by driving it). Dynamics NAV does not require these codes, however, we recommend that the descriptions provide a similar meaning.  

Optionally, you can also set up:

* **Transaction specifications**: Use these to supplement the descriptions from the transaction types.  
* **Areas**: Use these to supplement information about countries and regions.  
* **Entry/exit points**: Use these to specify the locations where you ship or receive items to or from other countries/regions. Heathrow Airport is an example of an entry or exit point. You enter entry or exit points on sales and purchase documents on the **Foreign Trade** FastTab. This information will also be copied from the item entries when you create the Intrastat journal.  

### To set up Intrastat templates and batches
The Intrastat batch jobs include only item entries, and not general ledger entries. If you have general ledger entries that qualify for Intrastat reporting, you must enter them manually. For example, if you purchase a computer from another EU country or region, the computer is not placed in inventory, but is posted to a general ledger account. You must manually enter this type of entry in the Intrastat journal.  
  
You can export the entries to a file that you can send to your Intrastat authorities. You can also print a report, manually enter the information on the forms from your authorities, and then submit the information.

> [!Note]
> We recommended that you set up an Intrastat journal batch for each month.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journal Templates**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Create a template for each Intrastat form you use.  
3. To create batches, choose the **Navigate** tab, and then choose **Batches**.  
4. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Create a template for each Intrastat form you use..  

> [!Note]
> In the **Statistics Period** field, enter the statistics period as a four-digit number, where the first two digits represent the year and the next two digits represent the month. For example, enter 1706 for June, 2017.

### To set up commodity codes
All items that you buy or sell must have a commodity code.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Commodity Codes**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. To assign a commodity code to an item, go to the **Item Card** page, expand the **Costs & Posting** FastTab, and then enter the code in the **Commodity Code** field.   

### To set up transaction nature codes
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transaction Nature Codes**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

> [!Tip]
> If you frequently use a particular transaction nature code, you can make it the default. To do this, go to the **Intrastat Setup** page, and choose the code. 

### To set up transport methods
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transport Methods**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To Report Intrastat
After you fill in the Intrastat journal, you can print the **Checklist** report to make sure that that all information in the journal is correct. Afterward, you can print an Intrastat report as a form, or create a file to submit to the tax authority in your country/region.  

### To fill in Intrastat journals  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journal** and then choose the related link.  
2. On the **Intrastat Journal** page, in the **Batch Name** field, choose the relevant journal batch, and then Choose the **OK** button.  
3. Choose the **Suggest Lines** action. The **Starting Date** and **Ending Date** fields will already contain the dates specified for the statistics period on the journal batch.  
4. In the **Cost Regulation %** field, you can enter a percentage to cover transport and insurance. If you enter a percentage, the content of the **Statistical Value** field in the journal is proportionally higher.  
5. Choose **OK** to start the batch job.  
  
The batch job retrieves all the item entries in the statistics period and inserts them as lines in the Intrastat journal. You can edit the lines if needed.  
  
> [!IMPORTANT]  
>  The batch job retrieves only the entries that contain a country/region code for which an Intrastat code has been entered on the **Countries/Regions** page. Therefore, you must enter Intrastat codes for the country/region codes for which you will run the batch job.  

### How to: Report Intrastat on a form or a file
To get the information that is required on the Intrastat form from the statistical authorities, you must print the **Intrastat – Form** report. Before you can do this, you must prepare the Intrastat journal and fill it in. If you have both sales and purchase transactions, you must complete a separate form for each type, so that you must print the report two times.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journals**, and then choose the related link.  
2. On the **Intrastat Journal** page, choose the relevant journal batch in the **Batch Name** field.  
3. If you have not already done this, fill in the journal manually or choose **Suggest Lines**.  
4. Choose the **Prints Intrastat Journal** action.  
5. On the **Intrastat Jnl. Line** FastTab, add a **Type** filter and then specify whether this is a **Receipt** or a **Shipment**.  
6. Choose **Send to** to print the report.  

### How to: Report Intrastat in a file
You can submit the Intrastat report as a file. Before creating the file, you can print a checklist that contains the same information that will be in the file.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journal**, and then choose the related link.  
2. In the **Intrastat Journal** window, select the relevant journal batch in the **Batch Name** field.  
3. If you have not already done this, fill in the journal manually or by choosing **Suggest Lines**.  
4. Choose the **Create File** action.  
5. In the batch job window, Choose the **OK** button.  
6. Choose **Save**.  
7. Browse to the location where you want to save the file, enter the file name, and then choose **Save**. 

## How to: Reorganize Intrastat Journals
Because you must submit an Intrastat report every month, and you create a new journal batch for each report, you will eventually have many journal batches. The journal lines are not deleted automatically. You may want to reorganize the journal batch names periodically. You do this by deleting the journal batches that you no longer need. The journal lines in these batches are also deleted.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intrastat Journals**, and then choose the related link.  
2. To view the options, choose the **Batch Name** field.  
3. Choose the journal batches to deleted, and then choose **Delete**.  

## See Also
[Dynamics 365 Business Central](/dynamics365/business-central/)  
[Financial Management](finance.md) 