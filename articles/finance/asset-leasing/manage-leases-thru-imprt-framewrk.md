---
title: 透過租賃匯入框架管理租賃
description: 本主題解釋如何使用租賃匯入框架同時調整多筆租賃。
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeaseImportHeader
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 534584a7da494b427d48b1bc97bf6554d25f4a79d9d62f59ec5f2afb65e67431
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450618"
---
# <a name="manage-leases-through-the-lease-import-framework"></a>透過租賃匯入框架管理租賃

[!include [banner](../includes/banner.md)]

本主題解釋如何使用租賃匯入框架一步式調整多筆租賃。 藉由本功能，您可以節省時間，也可以藉由減少人為錯誤的機會確保更精確的調整。 此外，本功能可以連接 Microsoft Dynamics 365 Finance 和外部資料實體有效率地上傳資料。

下列資料實體可用來整合資產租賃和外部系統：

- 租賃暫存
- 付款契約暫存
- 待履行契約暫存

您可以使用匯入流程調整租賃、更新非財務資訊或新增租賃。 您可以在匯入前檢視和編輯租賃資料。

系統可透過租賃匯入套件執行下列三道流程。

| 流程類型  | 描述 |
|---------------|-------------|
| 新增記錄    | 具有此流程類型的遷移租賃會在系統建立租賃。 付款期桯必須人工確認，而初步認可的日記帳分錄必須在遷移後人工過帳。 |
| 更新記錄 | 具有此流程類型的遷移租賃更新系統中已有租賃的欄位值。 唯有在 **更新欄位選取** 頁面選取的欄位才會更新。 我們建議您在 **更新欄位選取** 頁面選取非財務欄位，因為此流程類型不會調整租賃。 |
| 調整記錄 | 有此流程類型的遷移租賃調整租賃。 此項調整造成修改租賃的財務租賃。 租賃處理後，系統會使用租賃匯入套件的新資料建立新付款期程。 本系統不會確認付款期程或過帳調整日記帳分錄。 |

透過 **資料管理** 工作區上傳資訊後，請打開 **匯入抬頭** 頁 (**資產租賃\>租賃匯入框架\>匯入抬頭**)。 本頁面列出稍早列過的三個資料實體的所有匯入項。

若要在執行處理之前檢視租賃暫存資料，請選取 **暫存資料**。

比較功能讓您比較正在匯入對應記錄和系統已有的記錄。 若要比較個別租賃記錄，請選取租賃，然後選取 **比較**。 您應該在遷移租賃記錄前，完成此步驟產生 **差額** 報表。 比較功能暫存資料值和系統目前租賃值。

> [!NOTE]
> 比較功能不適用有 **新增記錄** 流程類型的租賃，因為該租賃無從比較。
>
> 若要同時比較多筆租賃，請前往 **資產租賃\>租賃匯入框架\>定期**，並選取 **比較**。

以各實體而言，您可以檢視系統目前內容和暫存表內容之間的差異。 以暫存表中的各實體而言，選取 **查看差異**。 出現的對話方塊顯示目前值和建議的暫存值。

您也可以藉由在 **新值** 欄位更改，然後選取 **更新暫存** 的方式更新暫存值。

您可以驗證租賃以確保記錄可帶入系統，不會出錯。 租賃記錄遷移之前，系統會執行多次驗證以確保記錄將成功匯入。 若要驗證單筆租賃，請選取 **驗證**。

> [!NOTE]
> 若要同時驗證多筆租賃，請前往 **資產租賃\>租賃匯入框架\>定期**，並選取 **驗證**。

若要處理單個筆租賃，請選取 **匯入抬頭** 頁上的 **遷移租賃記錄**。 遷移租賃時，系統將執行 **處理類型** 欄位指明的動作。

> [!NOTE]
> 若要同時遷移多筆租賃，請前往 **資產租賃\>租賃匯入框架\>定期**，並選取 **遷移**。

比較租賃後，您可以執行報表檢視匯入識別碼包括的各筆租賃差異。 若針對一筆租賃跑報表，請選取暫存資料中租賃，然後選取 **比較和檢視報表\>差異報表**。

> [!NOTE]
> 若要同時比較多筆租賃，請前往 **資產租賃\>租賃匯入框架\>定期** 並選取 **比較**。 

## <a name="set-up-update-fields"></a>設定更新欄位

如果您使用 Lease 匯入框架更新租賃，而且流程類型為 **更新記錄**，您可以選取預計更新的特定欄位。

1. 請前往 **資產租賃\>租賃匯入框架\>設定\>更新欄位選取**。
2. 在出現的頁面上選取預計更新的欄位，然後選取綠色箭頭將它們移往 **選取欄位** 清單。 只有 **選取欄位** 清單裡的欄位才能使用租約匯入套件更新。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
