---
title: How to Create Reports with XBRL | Microsoft Docs
description: XBRL, which stands for eXtensible Business Reporting Language, is an XML-based language for tagging financial data, and enabling businesses to efficiently and accurately process and share their data.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 10/01/2020
ms.author: edupont

---
# Create Reports with XBRL
XBRL, which stands for eXtensible Business Reporting Language, is an XML-based language for tagging financial data, and enabling businesses to efficiently and accurately process and share their data. The XBRL initiative enables global financial reporting by numerous ERP software companies and international accounting organizations. The goal of the initiative is to provide a standard for the uniform reporting of financial information for banks, investors, and government authorities. Such business reporting can include:  

 • Financial statements  
 • Financial information  
 • Non-financial information  
 • Regulatory filings, such as annual and quarterly financial statements  

> [!NOTE]
> You can import G/L-related schemas and create XBRL instance documents by mapping G/L data from the chart of accounts to elements in taxonomies that were designed for financial reports, such as balance sheets, income statements, and so on.
> 
> The XBRL capabilities in Business Central support taxonomies for Specification 2.1, however, taxonomies might contain unsupported elements such as Formula linkbases, iXBRL, or have other structural differences. We recommend that you validate the XBRL capability before you use it for reporting.
> 
> Full support for taxonomies may require third party XBRL tagging and tools. The XBRL International organization has a list of tools and services that you can use for XBRL reporting. Depending on the XBRL reporting requirements for a given taxonomy, you might want to explore those resources. For more information, see [Getting Started for Business](https://go.microsoft.com/fwlink/?linkid=2153466) and [Tools and Services](https://go.microsoft.com/fwlink/?linkid=2153356).

## eXtensible Business Reporting Language
XBRL (e**X**tensible **B**usiness **R**eporting **L**anguage) is an XML-based language for financial reporting. XBRL provides a standard for uniform reporting for all users of the financial information supply chain; such as public and private companies, the accounting profession, regulators, analysts, the investment community, capital markets and lenders, as well as key third parties such as software developers and data aggregators.  

Taxonomies are maintained by www.xbrl.org. You can download taxonomies or read more detailed information on the XBRL website.  

Someone who wants financial information from you, provides you with a taxonomy (an XML document) containing one or more schemas, each with one or more lines to fill out. The lines correspond to the individual financial facts required by the sender. You import this taxonomy and then fill out the schema(s) by entering which account or accounts correspond to each line and what kind of time frame to use, for example, net change or balance at date. In some cases you can enter a constant instead, for example, a number of employees. You are now ready to send the instance document (an XML document) to the requester. The idea is that this might be a recurring event, so unless changes have been made to the taxonomy, you just export new instance documents for new periods on request.  

## XBRL is comprised of the following components  
The XBRL **Specification** explains what XBRL is, and how to build XBRL instance documents and XBRL taxonomies. The XBRL Specification explains XBRL in technical terms and is intended for a technical audience.  

The XBRL **Schema** are the core low-level components of XBRL. The schema is the physical XSD file that expresses how instance documents and taxonomies are to be built.  

The XBRL **Linkbases** are the physical XML files that contain various information about the elements defined in the XBRL Schema, such as labels in one or more languages, how they relate to each other, how to sum up elements, and so on.  

An XBRL **Taxonomy** is a "vocabulary" or "dictionary" created by a group, compliant with the XBRL Specification, in order to exchange business information.  

An XBRL **Instance document** is a business report, such as a financial statement prepared to the XBRL specification. The meaning of the values in the instance document is explained by the taxonomy. An instance document is somewhat useless unless you know the taxonomy for which it is prepared.  

## Layered Taxonomies  
A taxonomy can consist of a base taxonomy, for example, us-gaap or IAS, and then have one or more extensions. To reflect this, a taxonomy refers to one or more schemas, each of which are separate taxonomies. When the additional taxonomies are loaded into the database, the new elements are simply added to the end of the existing elements.  

## Linkbases  
 In XBRL Spec. 2, the taxonomy is described in several XML-files. The primary XML file is the taxonomy schema file itself (.xsd file) which only contains an unordered list of elements or facts to be reported. In addition to this, there are usually associated some linkbase files (.xml). The linkbase files contain data which is complementary to the raw taxonomy (.xsd file). There are six types of linkbases files of which four have relevance for Product Name XBRL. These are:  

-   Label linkbase: This linkbase contains labels or names for the elements. The file may contain labels in different languages which are identified with an XML property called 'lang'. The XML language identifier usually contains a two-letter abbreviation, and although it should be easy to guess what the abbreviation means, there is no connection to the Windows language code or to the language codes defined in the demo data. Therefore, when the user looks up the languages for a specific taxonomy, he will see all the labels for the first element in the taxonomy, meaning that he can then see an example of each language. A taxonomy can have several label linkbases attached to it as long as these linkbases contain different languages.  

-   Presentation linkbase: This linkbase contains information about the structure of the elements, or more precisely; how the issuer of the taxonomy suggests that application presents the taxonomy to the user. The linkbase contains a series of links that each connect two elements as parent and child. When applying all these links, the elements can be shown in a hierarchical way. Note that the presentation linkbase deals with just that: the presentation of elements to the user.  

-   Calculation linkbase: This linkbase contains information about which elements roll up to which. The structure is quite similar to the presentation linkbase, except that each link or ‘arc’, as they are called, has a weight property. The weight can be either 1 or –1 indicating whether the element should be added to or subtracted from its parent. Note that the rollups are not necessarily in keeping with the visual presentation.  

-   Reference linkbase: This linkbase is an xml file that contains supplementary information about the data that is required by the taxonomy issuer.

## To set up XBRL lines  
After you import or update the taxonomy, the lines of the schemas must be supplied with all the information that is required. This information will include basic company information, the actual financial statements, notes to the financial statements, supplemental schedules, and other information that is required to satisfy the particular financial reporting requirements.  

You set up the XBRL Lines by mapping the data in the taxonomy to the data in your general ledger.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **XBRL Taxonomies**, and then choose the related link.  
2.  On the **XBRL Taxonomies** page, select a taxonomy from the list.  
3.  Choose the **Lines** action.  
4.  Select a line and fill in the fields.   
5.  To read detailed information about what to fill in, choose the **Information** action.  
6.  To set up the mapping of the general ledger accounts in the chart of accounts to the XBRL lines, choose the **G/L Map Lines** action.  
7.  To add notes to the financial statement, choose the **Notes** action.  

   > [!TIP]
   > To exclude lines from the export, choose **NOT APPLICABLE** as the source type.

   > [!NOTE]  
   > You can only export data that corresponds to the selection in the **Source Type** field. This includes descriptions and notes.  

   > [!NOTE]  
   > Taxonomies might contain elements that [!INCLUDE[prod_short](includes/prod_short.md)] does not support. If an element is not supported, the **Source Type** field will display **Not Applicable** and the **Description** field will show an error message, such as **Unexpected type: "specific type not recognized"**. If you must export the element, choose a matching source type. Typically, this is a constant or a description. This will allow you to enter and export data, however, such elements might have validation rules that cannot be checked before exporting.

 ## To import an XBRL taxonomy  
The first step in working with the XBRL functionality is to import the taxonomy into your company database. A taxonomy consists of one or more schemas and some linkbases. After you have completed the import of both schemas and linkbases and have applied the linkbases to the schema, you can set up the lines and map the general ledger accounts in the chart of accounts to the appropriate taxonomy lines.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **XBRL Taxonomies**, and then choose the related link.  
2.  On the **XBRL Taxonomies** page, create a new line and enter the name and description of the taxonomy.  
3.  Choose the **Schemas** action, and then insert the description of the schema.  
4.  To import the schema, on the **XBRL Schemas** page, choose the **Import** action, and the select a folder and an XSD file. Choose the **Open** button.  
5.  To import the linkbase, on the **XBRL Schemas** page, choose the **Linkbases** action, and then select a folder and an XML file. Choose the **Open** button..  
6.  You can now choose to apply the linkbase to the schema. Repeat until you have imported all linkbases.  
7. Choose the **Apply to Taxonomy** action to apply the linkbase to the schema.  

> [!IMPORTANT]  
>  Instead of individually applying the linkbases after the import, you can wait until you have imported all linkbases and then apply them at the same time. To do this, choose the **NO** button when you are prompted to apply the newly imported linkbase to the schema. Then select the lines with the linkbases that you want to apply.  

## To update an XBRL taxonomy  
When a taxonomy changes you need to update the current taxonomy accordingly. The reason for the update can be an altered schema, an altered linkbase, or a new linkbase. After updating the taxonomy, you only need to map the lines for the changed or new lines.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **XBRL Taxonomies**, and then choose the related link.  
2.  On the **XBRL Taxonomies** page, choose the **Schemas** action.  
3.  To update a schema, select the schema you want to update, and then choose the **Import** action.  
4.  To update or add a new linkbase, choose the **Linkbases** action.  
5.  Select the relevant linkbase or press Ctrl+N for a new line, select the type of linkbase, and then insert a description.  
6.  To import the linkbase, choose the **Import** action.  
7.  Choose the **Yes** button to apply the linkbase to the schema.  

## See Related Training at [Microsoft Learn](/learn/modules/xbrl-reports-dynamics-365-business-central/index)

## See Also
[Finance](finance.md)    
[Business Intelligence](bi.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]