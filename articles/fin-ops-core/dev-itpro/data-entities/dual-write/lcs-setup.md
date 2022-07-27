---
title: Lifecycle Services 的雙重寫入設定
description: 本主題說明如何從 Microsoft Dynamics Lifecycle Services (LCS) 設定雙重寫入連線。
author: laneswenka
ms.date: 08/03/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 825d6a4b3462077d0f4b3f4275792ea0fe5152df
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460233"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Lifecycle Services 的雙重寫入設定

[!include [banner](../../includes/banner.md)]



本主題說明如何從 Microsoft Dynamics Lifecycle Services (LCS) 啟用雙重寫入。

## <a name="prerequisites"></a>先決條件

您必須按照以下主題中的說明完成 Power Platform 整合：

+ [Power Platform 整合 - 在環境部署期間啟用](../../power-platform/enable-power-platform-integration.md#enable-during-deploy)
+ [Power Platform 整合 - 在環境部署後啟用](../../power-platform/enable-power-platform-integration.md#enable-after-deploy)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>為新的 Dataverse 環境設定雙重寫入

按照以下步驟從 LCS **環境詳情** 頁面設定雙重寫入：

1. 在 **環境詳情** 頁，展開 **Power Platform 整合** 區塊。

2. 選取 **雙重寫入應用程式** 按鈕。

    ![Power Platform 整合。](media/powerplat_integration_step2.png)

3. 查看條款和條件，然後選取 **設定**。

4. 選取 **確定**，繼續。

5. 您可以透過定期重新整理環境詳情頁面來監控進度。 設定通常需要 30 分鐘或更短的時間。  

6. 設定完成後，將有一條訊息通知您該過程是成功還是失敗。 如果設定失敗，則會顯示相關的錯誤訊息。 在進行下一步之前，您必須修復所有錯誤。

7. 選取 **連結到 Power Platform 環境** 以在 Dataverse 和目前環境的資料庫之間建立連結。 這通常需要不到 5 分鐘。

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="連結到 Power Platform 環境。":::

8. 連結完成後，會顯示一個超連結。 使用該連結登入到財務和營運環境中的雙重寫入管理區域。 從那裡，您可以設定實體對應。

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>為現有 Dataverse 環境設定雙重寫入

若要為現有 Dataverse 環境設定雙重寫入，您必須建立 Microsoft [支援票證](../../lifecycle-services/lcs-support.md)。 門票必須包括：

+ 您的財務和營運環境 ID。
+ 來自 Lifecycle Services 的環境名稱。
+ 來自 Power Platform 管理中心的 Dataverse 組織 ID 或 Power Platform 環境 ID。 在您的票證中，請求 ID 是用於 Power Platform 整合的實體。

> [!NOTE]
> 您無法使用 LCS 取消連結環境。 若要取消連結環境，請打開財務和營運環境中的 **資料整合** 工作區，然後選取 **取消連結**。

## <a name="linking-mismatch"></a>連結不相符

您的 LCS 環境可能連結到一個 Dataverse 實體，而您的雙重寫入環境可能連結到另一個 Dataverse 實體。 這種連結不相符可能會導致意外行為，最終可能會將資料發送到錯誤的環境。 推薦用於雙重寫入的環境是作為 Power Platform 整合的一部分建立的環境，從長遠來看，這將是在環境之間建立連結的唯一方法。

如果您的環境存在連結不相符，LCS 會在您的環境詳情頁面上顯示類似於「Microsoft 偵測到您的環境透過雙重寫入連結到與 Power Platform 整合中指定目的地不同的目的地，不建議這樣做」的警告：

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Power Platform 整合連結不相符。":::

如果您遇到此錯誤，有兩個選項，根據您的需要：

+ [取消連結和重新連結雙重寫入環境 (重設或更改連結)](relink-environments.md#scenario-reset-or-change-linking)，如您的 LCS 環境詳情頁面上指定的那樣。 這是理想的選取，因為您可以在沒有 Microsoft 支援的情況下執行它。  
+ 如果您想保持雙重寫入連結，您可以向 Microsoft 支援尋求幫助，以更改 Power Platform 整合以使用您現有的 Dataverse 環境，如上一節所述。  

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
