---
ms.openlocfilehash: 22911afd3a3da0ce3bcaeb7e42ab0096c868be547d559f14a91e09d6e6e12c08
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452859"
---
在環境之間複製資料庫時，您必須在複製的資料庫完全運作之前執行環境重新佈建工具，以確保所有 Commerce 元件都是最新的。

> [!IMPORTANT]
> 由於所有環境都包含 Commerce 功能，因此無論您是否使用 Commerce 元件，都建議您執行此程序。 

在繼續之前，您必須確保符合下列必要條件：
1. 如果您要升級到 2017 年 7 月版本 (也稱為 7.2) 的 7.2.11792.56024，請先在目的地環境中套用下列應用程式 X++ Hotfix，再於該環境中執行資料升級。 這些將防止資料升級過程中發生的各種錯誤：

    - KB 4036156 - 零售次要版本升級 -「未設定變體編號序列」。 此修正套件還包含 KB 4035399 和 KB 4035751。 請注意，您必須至少擁有平台更新 9 才能使用此套件。 如果您不確定，請安裝最新的二進位檔案。
    
2. 如果您要從 Microsoft Dynamics AX 2012 升級，請先在目的地環境中安裝下列應用程式 X++ 修正，再執行資料升級：
    - KB 4033183 - Dynamics AX 2012 R2 或 Dynamics AX 2012 R3 Pre-CU8 版本非零售升級失敗，dbo.RETAILTILLLAYOUTZONE 找不到物件。
    - KB 4040692 - 從 Dynamics AX 2012 R3 升級到 Microsoft Dynamics 365 for Operations 7.2 失敗，SalesLineIdx 上出現 RetailSalesLine 重複索引。
    - KB 4035490 - GeneralJournalAccountEntry MainAccount 欄位升級指令碼發生效能問題。


請遵循下列步驟來執行環境重新佈建工具。

1. 在共用資產庫中，選取 **軟體可部署的套件**。
2. 下載環境重新佈建工具。
3. 在您專案的資產庫中，選取 **軟體可部署的套件**。
4. 選取 **新增** 以建立新的套件。
5. 輸入套件的名稱和描述。 您可以使用 **環境重新佈建工具** 做為套件名稱。
6. 上傳您稍早所下載的套件。
7. 在您目標環境的 **環境詳細資料** 頁面上，選取 **維護** > **套用更新**。
8. 選取您稍早所上傳的環境重新佈建工具，然後選取 **套用** 以套用套件。
9. 監視套件部署的進度。 

如需如何套用可部署套件的詳細資訊，請參閱[套用可部署的套件](../deployment/create-apply-deployable-package.md)。 如需如何手動套用可部署套件的詳細資訊，請參閱[安裝可部署的套件](../deployment/install-deployable-package.md)。
