---
title: 匯入 ER 設定的版本更新
description: 本主題說明如何從設定服務的全局存放庫匯入電子報表 (ER) 設定的版本更新。
author: NickSelin
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 712bccbd48775cadc069ef5e8a04f9aae3c9f223137bcd394ff1815a720393b5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460496"
---
# <a name="import-updated-versions-of-er-configurations"></a>匯入 ER 設定的版本更新

[!include [banner](../includes/banner.md)]

電子報告 (ER) [存放庫](general-electronic-reporting.md#Repository)用於分享 [ER 設定](general-electronic-reporting.md#Configuration)。 您可以將 ER 設定從不同的存放庫[匯入](download-electronic-reporting-configuration-lcs.md)您的 Microsoft Dynamics 365 Finance 實體。 當您匯入 ER 設定時，[設定提供者](general-electronic-reporting.md#Provider)可以發布新[版本](general-electronic-reporting.md#component-versioning)存放庫，以便可以分享它們。

本主題說明如何從設定服務的全局存放庫匯入 ER 設定的版本更新。 如需相關資訊，請參閱[Microsoft Dynamics 365 for Finance and Operations - Regulatory Services，設定服務](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration)。

## <a name="review-the-available-updated-versions"></a>查看可用的版本更新

1. 使用以下角色之一登入 Finance：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **匯入設定版本更新**。

    ![本地化設定頁面。](./media/er-download-updated-versions-global-repo1.png)

4. 在 **匯入電子報告設定版本更新** 對話方塊的 **執行模式** 欄位中，選取 **僅顯示可用更新**。 然後選取 **確定**。 

    ![執行模式欄位設定為僅顯示可用更新。](./media/er-download-updated-versions-global-repo2.png)

5. 查看您收到的訊息。 這些訊息提供有關現行 Finance 實體中的 ER 設定以及它們與全局存放庫內容的比較情況的以下資訊：

    - ER 設定總數
    - 全局存放庫中不存在的 ER 設定
    - 現行 Finance 實體中已提供最新版本的 ER 設定 (若要查看這些 ER 設定的完整清單，請選取 **訊息詳情** 連結。)

        ![「以下設定的最新版本已匯入」訊息和訊息詳情](./media/er-download-updated-versions-global-repo3.png)

    - 最新版本的 ER 設定在全局存放庫中可用並且可以匯入到現行的 Finance 實體中 (若要查看這些 ER 設定的完整清單，請選取 **訊息詳情** 連結。)

        ![「可用更新」訊息和訊息詳情](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a>匯入可用的更新版本

1. 使用以下角色之一登入 Finance：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **匯入設定版本更新**。
4. 在 **匯入電子報表設定版本更新** 對話方塊的 **執行模式** 欄位中，選取 **匯入最新更新** 以將最新版本的 ER 設定從全局存放庫匯入到現行 Finance 實體。
5. 若要為匯入安排批次處理作業，請在 **背景執行** FastTab 上，將 **批次處理** 選項設定為 **是**。 如果要定期重複匯入，請設定所需的重複週期。

    ![執行模式欄位設定為匯入最新更新。](./media/er-download-updated-versions-global-repo5.png)

6. 選取 **確定**。
7. 若要了解已匯入哪些設定版本，請執行以下步驟之一：

    - 如果您以互動方式執行匯入而不是使用批次處理作業，請查看您收到的訊息。

        ![在互動式匯入執行期間收到的訊息。](./media/er-download-updated-versions-global-repo6.png)

    - 如果您以批次處理模式執行匯入，請執行以下步驟：

        1. 進入 **常用**\>**查詢**\>**批次作業**\>**我的批次處理作業**。
        2. 查詢並選取 **匯入電子報表設定版本更新** 作業，然後在操作窗格的 **批次處理作業** 索引標籤上，選取 **批次處理作業歷史記錄** 以查看作業歷史記錄。
        3. 在 **批次處理作業歷史** 頁面，選取 **記錄**。 然後，在您收到的訊息中，選取 **訊息詳情** 連結以查看作業記錄。

        ![作業記錄。](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> 我們不建議您安排重複性批次處理作業將更新版本的 ER 設定直接從全局存放庫匯入生產環境，因為匯入的版本將立即可供使用。 相反，使用此方法將 ER 設定版本部署到沙箱環境。 然後可以在將它們部署到生產環境之前在沙箱環境中對其進行評估。

## <a name="additional-resources"></a>其他資源

- [電子報表 (ER) 概觀](general-electronic-reporting.md)
- [從設定服務的全域存放庫下載 ER 設定](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]