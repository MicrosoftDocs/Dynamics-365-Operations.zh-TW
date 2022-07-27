---
title: 在財務和營運應用程式和 Dataverse 中驗證雙重寫入設定
description: 本主題說明如何確定是否在財務和營運應用程式和 Dataverse 中配置了雙重寫入。
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 3fa16a450032464e445ae166f0699fe0dc388071
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460197"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>在財務和營運應用程式和 Dataverse 中驗證雙重寫入設定

[!include [banner](../../includes/banner.md)]





本主題提供有關財務和營運應用程式與 Dataverse 之間的雙重寫入整合的疑難排解信息。 具體來說，它解釋了如何確定是否在財務和營運應用程式和 Dataverse 中配置了雙重寫入。

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>驗證在財務和營運應用程式中設定了雙重寫入

若要確定您在嘗試儲存行以供更新時看到的錯誤是否來自雙重寫入，請先驗證是否設定了雙重寫入。

+ 如果您在財務和營運應用程式中具有管理員權限，請進入 **工作區\>資料管理**，然後選取 **雙重寫入** 圖格。 如果顯示了連結環境的詳情和正在運行的表對應清單，則說明設定了雙重寫入。

    ![在您擁有管理員權限時驗證財務和營運應用程式連接。](media/verify_fin_ops_1.png)

+ 如果您沒有管理員權限，您將收到錯誤訊息 *無法將資料寫入實體\<entity name\>*。 在下圖中的範例中，您無法在財務和營運應用程式中建立客戶資料列，因為設定了雙重寫入，但 Dataverse 中不存在客戶組和付款條款參考資料。

    ![在您沒有管理員權限時驗證財務和營運應用程式連接。](media/verify_fin_ops_2.png)

如需如何在財務和營運應用程式中建立資料時解決問題的相關信息，請參閱[疑難排解即時同步問題](dual-write-troubleshooting-live-sync.md)。

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>驗證是否在 Dataverse 中設定了雙重寫入

建立資料時，如果在 Dataverse 中的頁面上看到 **公司** 資料欄，則說明設定了雙重寫入。

![驗證 Dataverse 連線。](media/verify_cds.png)

如需如何在 Dataverse 中建立資料時解決問題的相關信息，請參閱[疑難排解即時同步問題](dual-write-troubleshooting-live-sync.md)。

針對如果您在 Dataverse 中建立資料時遇到任何錯誤，該如何查看錯誤詳情，請參閱[在 Dataverse 中啟用並查看外掛程式跟踪記錄以查看錯誤詳情](dual-write-troubleshooting.md#enable-view-trace)。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]