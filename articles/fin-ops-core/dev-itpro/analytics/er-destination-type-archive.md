---
title: 封存 ER 目的地類型
description: 本主題提供有關如何為電子報表 (ER) 格式的每個 FOLDER 或 FILE 組件設定封存目的地的信息。
author: NickSelin
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: e2566fc5115df8b47277fc6b6d7f4698cea0a00bea83bcb17e9d7a9e9b765b65
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460410"
---
# <a name="archive-er-destination-type"></a>封存 ER 目的地類型

[!include [banner](../includes/banner.md)]

您可以為設定為產生輸出文件的電子報表 (ER) 格式的每個 **資料夾** 或 **檔案** 組件設定封存目標。 根據該目的地設定，產生的文件作為 ER 作業清單記錄的附件儲存。 若要檢視該結果，進入 **組織管理**\>**電子報表**\>**電子報表作業**。

您可以使用此選項將產生的文件發送到 Microsoft SharePoint 資料夾或 Microsoft Azure 儲存體。 將 **已啟用** 設定為 **是** 以將輸出發送到由所選文件類型定義的目的地。 只有群組設定為 **檔案** 的文件類型可供選取。 您在 **組織管理**\>**文件管理**\>**文件類型** 中定義文件[類型](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types)。 ER 目的地的設定與文件管理系統的設定相同。

[![檔案類型頁面。](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

位置確定檔案的儲存位置。 啟用 **封存** 目標後，可以將結果儲存在作業封存中。 您可以在 **組織管理**\>**電子報表**\>**電子報表封存作業** 檢視結果。

> [!NOTE]
> 透過導覽至 **組織管理**\>**工作區**\>**電子報表**\>**電子報表參數** 來選取作業封存的文件類型。 如需相關資訊，請參閱[設定電子報表 (ER) 架構](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup)。

## <a name="sharepoint"></a>SharePoint

您可以將檔案儲存在指定的 SharePoint 資料夾中。 若要定義預設 SharePoint 伺服器，請進入 **組織管理**\>**文件管理**\>**文件管理參數**。 在 **SharePoint** 索引標籤上，設定 SharePoint 資料夾。 然後，您可以選取它作為將儲存 ER 輸出的資料夾。 該 **SharePoint** 必須在此文件類型中選取位置。

[![選取 SharePoint 資料夾。](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Azure 儲存體

當文件類型位置設定為 **Azure 儲存體** 時，您可以將檔案儲存到 Azure 儲存體。

> [!NOTE] 
> ER 架構將檔案永久儲存在 Azure Blob 儲存體中，這與對必須處理的文件應用 7 天保留策略的資料管理架構不同。 如需相關資訊，請參閱[取得訊息狀態的 API](../data-entities/recurring-integrations.md#api-for-getting-message-status)和[狀態檢查 API](../data-entities/data-management-api.md#status-check-api)。 只要有必要，與 ER 相關的檔案將作為應用程式表記錄的附件儲存在 Azure Blob 儲存體中。 將從 Azure Blob 儲存體中刪除單個檔案以及該檔案附加到的應用程式表記錄。

## <a name="additional-resources"></a>其他資源

- [電子報表 (ER) 概觀](general-electronic-reporting.md)
- [電子報表 (ER) 目的地](electronic-reporting-destinations.md)
- [設定檔案管理](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]