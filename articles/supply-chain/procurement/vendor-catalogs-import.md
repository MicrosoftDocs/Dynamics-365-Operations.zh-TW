---
title: 匯入廠商目錄
description: 本主題說明匯入廠商目錄資料的流程。
author: Henrikan
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, CatVendorCatalogDetails, CatVendorCatalogReleaseApprovedProducts, CatVendorCMRDetails, CatVendorCatalogProductPerCompanyStatus, CatVendorMaintenanceEventLog, CatVendorCatalogReviewTool, CatVendorCatalogFileUpload, CatVendorCatalogMaintenanceRequest, CatVendorCatalogFileInLegalEntity, CatVendorCatalogSchema, CatVendorCatalogFilePreviewPane, CatVendorCatalogImportParameter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: henrikan
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: fb7e9735ac29fae50a4a3874b713a9a75799605c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448302"
---
# <a name="import-vendor-catalogs"></a>匯入廠商目錄

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a>廠商目錄匯入

在 Dynamics 365 Supply Chain Management 中，採購專業人員可以建立和維護目錄，供公司員工在訂購供內部使用的品項和服務時使用。 若要建立採購目錄，您可以透過匯入產品目錄資料或將產品目錄資料手動新增到基準產品，來新增要向員工提供的品項和服務。 

您可以上傳廠商從 Microsoft Dynamics 365 用戶端提交的目錄資料。

廠商以目錄維護請求 (CMR) 檔案的形式提交給您的產品資料必須採用 XML 檔案格式。 CMR 檔案應包含廠商提供給您公司的產品詳細資料。

## <a name="import-vendor-catalog-data"></a>匯入廠商目錄資料

若要匯入廠商目錄資料，您必須完成以下工作：

1. 在定義了資料對應規則的資料管理工作區中設定專案。 選擇 **資料管理** 然後選擇 **設定資料專案的角色**。

2. 設定採購類別階層，並將廠商指派到採購類別。 如果您使用商品代碼，則將商品代碼新增到採購類別中。 有關設定採購類別階層的資訊，請參閱[設定採購類別階層](../procurement/tasks/set-up-procurement-category-hierarchy.md)。

3. 設定目錄匯入的廠商。 選擇廠商，然後選擇 **採購** > **設定** > **設定目錄匯入的廠商**。

4. 設定目錄匯入的工作流程。 建立 CMR 檔案範本並與您的廠商共用。

5. 選擇 **採購和資源開發** \> **通用** \> **目錄** \> **廠商目錄** 以建立廠商目錄。 在此目錄中對您從廠商處接收的目錄維護要求 (CMR) 檔案進行分組。 

6. 上傳 CMR 檔案。

7. 檢閱、核准或拒絕廠商目錄中的產品。 產品會自動對應到採購類別。 

已核准的產品將新增到基準產品並發佈給選定的法律實體。 只有核准的產品才能新增到採購目錄中。

## <a name="generate-a-catalog-import-file-template"></a>產生目錄匯入檔案範本

目錄匯入檔案範本是一個 XSD 檔案，用於為廠商的產品建立 CMR 檔案。 您可以使用 CMR 檔案建立新目錄、替換現有目錄或修改現有目錄。

1. 選擇 **採購和資源開發** \> **目錄** \> **廠商目錄** 並按兩下要使用的目錄。

2. 下載目前目錄匯入範本 (XSD 檔案)。 在 **更新目錄** 頁面的 **動作窗格** 上，在 **目錄** 索引標籤的 **相關資訊** 群組中，點選 **產生目錄範本**，然後選擇 **採購類別**。

    - 可使用 **採購類別** 選項產生目錄範本，其中包括廠商授權提供產品的採購類別。

3. 在 **另存新檔** 對話方塊中，選擇要儲存目錄檔案範本的位置並儲存檔案。

有關更多資訊和範例，請參閱此部落格文章：[Dynamics AX 中的廠商目錄](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]