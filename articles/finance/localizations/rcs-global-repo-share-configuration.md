---
title: 與外部組織共用 RCS/全 Global 存放庫的 ER 組態
description: 本主題解釋如何直接與外部組織共用 Microsoft Regulatory Configuration Services (RCS)/ Global 存放庫的 Electric 報表 (ER) 組態。
author: JaneA07
ms.date: 05/04/2020
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
ms.openlocfilehash: ee7feef83ffa458e7cbd238d37a0f343d1a202f48002da67823df024bb609d02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450174"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a>與外部組織共用 Regulatory Configuration Services (RCS) Global 存放庫的 Electric 報表 (ER) 組態。

[!include [banner](../includes/banner.md)]

您可以使用 Microsoft Regulatory Configuration Services (RCS) 共用 Electronic 報表 (ER) 組態，接著將它們發佈到外部組織。

下列程序解釋 RCS 使用者如何與外部組織共用已在 RCS 執行個體配置的 ER 組態版本。 在您完成這些程序之前，您必須先完成先決行件如下：

- 存取 RCS 執行個體。
- 建立有效組態提供者。 更多資訊，請參閱[建立組態提供者並標示為有效](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)。
- 建立和上傳新 ER 組態版本。 更多資訊，請參閱[建立和上傳新 Electronic 報表 (ER) 組態版本](rcs-global-repo-upload.md)。

您也必須確定為貴公司佈署 RCS 環境。

1. 在財務和營運應用程式中，前往 **組織管理**\>**工作區**\>**電子報表**。
2. 如果貴公司未佈署任何 RCS 環境，請選取 **Regulatory Services - 外部組態**，接著按照說明部署一個。

如果貴公司已經佈署 RCS 環境，請使用頁面的 URL 選取登入選項存取。

## <a name="verify-the-configuration-that-you-want-to-share"></a>驗證您希望共用的組態

按照下列步驟驗證您希望共用的組態是否已上傳到 Global 存放庫。

1. 在 **Electronic 報表** 工作區為您的組態提供者選取 **存放庫**。

    ![組態提供者。](media/1_RCS_Repo_for_config_provider.JPG)

2. 選取 **Global 存放庫**\>**打開**。
3. 搜尋您希望共用的組態。 您可以使用篩選欄位縮小搜尋範圍。 如果在 Global 存放庫中找不到組態，請按照[建立和上傳新 Electronic 報表 (ER) 組態版本的步驟](rcs-global-repo-upload.md)。

## <a name="share-er-configurations-with-external-organizations"></a>與外部組織共用 ER 組態

待組態已在您的組態提供者下建立後，您可以使用 **Global 組態存放庫** 頁上的 **共用對象** FastTab 直接與外部組織共用。

1. 在 **Electronic 報表** 工作區為您的組態提供者選取 **存放庫**。
2. 選取 **Global 存放庫**\>**打開**。 
3. 選取您希望共用的組態。
4. 在 **共用對象** FastTab 上選取 **組織**。

    ![與 FastTab 共用。](media/1_RCS_Repo_for_Share_with_org.JPG)

5. 在對話方塊中，輸入外部組織的網域名稱，接著選取 **確定**。

    ![與外部組織共用組態版本對話方塊。](media/1_RCS_Repo_for_Share_with_form.JPG)

組態是與外部組織共用，並開放 Global 存放庫中的組織使用。 它可以從那裡匯入組織的 RCS 執行個體或其財務和營運應用程式執行個體。

6. 若要取消共用之前已和外部組織共用的組態，請選取此組態並點選 **取消共用**，接著選取 **確定**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]