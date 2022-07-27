---
title: Dynamics 365 Supply Chain Management 10.0.6 (2019 年 11 月) 的新增功能或變更
description: 本主題說明 Dynamics 365 Supply Chain Management 10.0.6 中的新增功能或變更。
author: kamaybac
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 87bcda25b89135e052a5a883b816ea0bb430479a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448152"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a>Dynamics 365 Supply Chain Management 10.0.6 (2019 年 11 月) 的新增功能或變更

[!include [banner](../includes/banner.md)]

本主題說明 Microsoft Dynamics 365 Supply Chain Management 10.0.6 中的新增功能或變更。 此版本的組建編號為 10.0.234。 雖然正式發行日期為 11 月，新增功能在 10 月的提前版本中就已提供。 有關版本 10.0.6 的詳細資訊，請參閱[其他資源](whats-new-scm-10-0-6.md#additional-resources)。

## <a name="product-configuration-models-v2-data-entity"></a>產品設定模型 V2 資料實體

已發佈「產品設定模型」資料實體的第二個版本 (稱為「產品設定模型 V2」)。 預設範本「418 - 產品設定模型」也需要使用匯入/匯出框架範本中的新「產品設定模型 V2」資料實體。 該範本不會自動更新，因此您必須手動從預設範本載入。 V2 實體將一行作為附件中的一個單獨檔案匯出，而不是以內嵌方式匯出，從而解決 V1 實體的大小限制問題。 
 
若要採用此更新，需要執行什麼操作？
-    由於 V1 實體已被取代，您應該從 V1 遷移到 V2。 如果您使用的是「418 - 產品設定模型」範本，可以點擊「載入預設範本」按鈕，重新載入範本「418 - 產品設定模型」
-    如果您需要保持與現有系統的相容性，您現在可以繼續使用現有範本和 (已取代) V1 實體，直到您將整合移至新範本。 

## <a name="feature-management-enhancements"></a>功能管理增強功能
功能管理現在可讓您預設啟用所有新功能，要求執行功能確認和啟用尚未啟用的所有功能。 


## <a name="purchase-agreement-responsible-party"></a>採購合約責任方
您現在可以在採購合約分類表單和產生的採購合約中定義主要和次要責任方。  這讓使用者可以存取合約的監督者。

## <a name="rfq-link-on-the-purchase-order-line"></a>訂購單行中的 RFQ 連結
您可以將訂購單行中的參考連結新增回其相應的來源 RFQ 行，從而輕鬆地為使用者提供詢價文件支援。

## <a name="additional-resources"></a>其他資源

### <a name="bug-fixes"></a>錯誤修正
有關 10.0.6 中每個更新包含的錯誤修正資訊，請登入 Lifecycle Services (LCS)，並查看[知識庫文章](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7)。

### <a name="platform-update-30"></a>平台更新 30
Microsoft Dynamics 365 Supply Chain Management 10.0.6 包括平台更新 30。 若要深入了解有關平台更新 30，請參閱[平台更新 30 中的新增功能或變更](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md)。

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Dynamics 365：2019 年發行第 2 波計劃
想了解商務應用程式或平台中即將推出和最近發布的功能嗎？

查看 [Dynamics 365：2019 年發行第 2 波計劃](/dynamics365-release-plan/2019wave2/)。 我們已經在文件中擷取了所有詳細資料，從頭到尾，從上到下，方便您進行規劃。

### <a name="removed-and-deprecated-supply-chain-management-features"></a>已移除和已取代的 Supply Chain Management 功能

[Dynamics 365 Supply Chain Management 中已移除或已取代的功能](removed-deprecated-features-scm-updates.md)主題說明了 Supply Chain Management 已經或計劃移除或取代的功能。

- *已移除* 功能不再於產品中提供該功能。
- *已取代* 功能未進行開發，可能會在未來的更新中移除。

在從產品中刪除任何功能之前，將在移除前 12 個月在 [Dynamics 365 Supply Chain Management 中已移除或已取代的功能](removed-deprecated-features-scm-updates.md)主題中公佈取代通知。

對於僅影響編譯時間但與沙盒和生產環境二進位相容的重大變更，取代時間將少於 12 個月。 這些通常是需要對編譯器進行的功能更新。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]