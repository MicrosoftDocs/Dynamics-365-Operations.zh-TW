---
title: 在 RCS 建立 ER 組態並上傳到 Global 存放庫
description: 本主題解釋如何在 Microsoft Regulatory Configuration Services (RCS) 建立 Electric 報表 (ER) 組態並上傳到 Global 存放庫。
author: JaneA07
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: eb04362d6d7261af56d2940b085fbc8d43c9d662
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "8451341"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>在 Regulatory Configuration Services (RCS) 建立 ER 組態並上傳到 Global 存放庫

[!include [banner](../includes/banner.md)]

您可以使用 Microsoft Regulatory Configuration Services (RCS) 設計 Electronic 報表 (ER) 組態和發佈，藉此可在貴組織使用。

下列程序解釋系統管理員中的使用者或 Electronic Reporting Developer 角色，如何建立已經在 RCS 執行個體配置的 ER 組態衍生版本，接著上傳衍生組態到 Global 存放庫。 

在您完成這些程序之前，您必須先完成先決行件如下：

- 對貴組織的 RCS 環境有存取權。
- 建立有效組態提供者並讓它有效。 更多資訊，請參閱[建立組態提供者並標示為有效](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)。

您必須確定貴公司已佈署 RCS 環境。 如果貴組織尚未佈署 RCS 執行個體，您可以使用下列步驟進行：

1. 在財務和營運應用程式中，前往 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **相關連結/外部連結** 中，選取 **Regulatory services - 組態**，接著按照說明 **註冊** 佈署一個。

如果貴組織已經佈署 RCS 環境，請使用頁面的 URL 存取並選取 **登入** 選項。

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>在 RCS 建立組態的衍生版本

> [!NOTE]
> 如果這是您第一次使用 RCS，您將無法從中衍生任何可用的組態。 您將需要從 Global 存放庫匯入組態。 關於詳細資訊，請參閱[從設定服務的全域存放庫下載 ER 設定](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)。

1. **登入** RCS 並選取 **Electronic 報表** 工作區。
2. 驗證貴組織的有效組態提供者已設定為有效 (請參閱先決行件)。 
3. 請選取 **Reporting 組態**。
4. 請選取希望從中衍生新版本的組態。 您可以使用樹狀圖上方的篩選欄位縮小您的搜尋範圍。
5. 請選取 **建立組態**\>**從 Name 衍生**。
6. 輸入名稱和說明，接著選取 **建立組態**，建立狀態為 '草稿' 的新衍生版本。
7. 如果有需要，選取新衍生的組態並對配置格式進行額外更改。 
8. 更改完成後，您需要設定組態的 **更改狀態** 為 **已完成**，才能發佈到存放庫。 選取 **確定**。

![RCS 的新組態版本。](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> 更改組態狀態時，您可能會收到與連接的應用程式有關的驗證錯誤訊息。 若要關閉驗證，請在 **組態** 索引標籤上的動作窗格，選取 **使用者參數**，接著設定 **跳過組態的狀態更改時的驗證並且重訂基底** 選項為 **是** 

## <a name="upload-a-configuration-to-the-global-repository"></a>上傳組態到 Global 存放庫

若要與貴組織共用新組態或衍生組態，您可以按照下列步驟上傳到 Global 存放庫：

1. 選取完整的組態版本，接著選取 **上傳到存放庫**。
2. 選取 **Global (Microsoft)** 選項和 **上傳**。

    ![上傳到存放庫選項。](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. 在確認訊息方塊中，選取 **是**。 
4. 按照需求更新版本說明，接著選取 **確定**。 您也可以選擇性上傳版本到連接的應用程式或 GIT 存放庫。  

組態的狀態更新為 **共用**，並且上傳到 Global 存放庫。 您上傳的組態草稿版本也會建立並且用在後續需要更改的時候。

組態上傳到 Global 存放庫後，您可以透過下列方式在那裡使用：

- 匯入您的 Dynamics 365 執行個體。 更多資訊，請參閱 [(ER) 從 RCS 匯入組態](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md)。
- 與第三方或外部組織共用，請參閱 [RCS 與外部組織共用 Electronic 報表 (ER) 組態](rcs-global-repo-share-configuration.md)

    ![Global 存放庫衍生的 Intrastat Contoso 組態版本。](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>從 Global 存放庫刪除組態
完成下列步驟刪除貴組織已經建立的組態。

1. 在 **Electronic 報表** 工作區驗證您的組態提供者是否為 **有效**。 更多資訊，請參閱[建立組態提供者並標示為有效](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)。
2. 在您的有效組態提供者上方，選取 **存放庫**。
3. 選取存放庫類型 **Global**，並選取 **打開**。
4. 在 **篩選** FastTab 上方使用 **篩選** 功能尋找希望刪除的組態。
5. 在 **版本** FastTab 上方，選取希望刪除的組態版本，之後選取 **刪除**：

    ![從全域存放庫刪除組態。](media/RCS_Delete_from_GlobalRepo.JPG)

6. 在確認訊息方塊中，選取 **是**。

    ![刪除組態版本確認訊息。](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
組態版本已刪除，並顯示確認訊息。 

> [!NOTE]
> 組態只能由建立它們的組態提供者刪除。 如果組態已和另一間組織共用，將需要先取消共用組態才能刪除。
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
