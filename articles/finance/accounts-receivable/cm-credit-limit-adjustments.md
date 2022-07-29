---
title: 信用額度調整
description: 本主題說明如何設定和新增信用額度調整。
author: JodiChristiansen
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: c171ab99a434e529c48f39be9147ac411fb08b9b
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451167"
---
# <a name="credit-limit-adjustments"></a>信用額度調整 

[!include [banner](../includes/banner.md)]

信用額度調整可讓信用經理透過過帳流程更新單一客戶、一組客戶或所有客戶的信用額度和到期日期。 您可以新增信用額度調整分錄來更新客戶和客戶信用群組，也可以使用它們來計算自動信用額度。 然後可以查看分錄，透過工作流程傳送以供核准，並過帳到客戶帳戶。

## <a name="set-up-credit-limit-adjustments"></a>設定信用額度調整

您可以在 **信用額度調整** 頁面 (**信用管理 \> 信用額度調整 \> 信用額度調整**) 上信用額度調整日記帳中建立分錄。

1. 選取 **新增**。 這將建立具有信用額度調整編號的新分錄群組。
2. 選擇信用額度調整類型：

    - 選擇 **信用額度** 以變更客戶的信用額度。
    - 選擇 **臨時信用額度** 以建立臨時信用額度，而不是變更客戶目前的信用額度。 臨時信用額度會在所定義的時間內覆寫客戶信用額度。 該期間結束後，將再次使用客戶的信用額度。
3. 輸入描述。 

如果已選取 **已過帳** 核取方塊，則已套用信用額度。 **核准狀態** 欄位表示日記帳的工作流程狀態。 工作流程是選擇性的。

### <a name="add-credit-limit-adjustments"></a>新增信用額度調整

要手動新增信用額度調整，請選擇 **行**，然後執行以下步驟。

1. 要為客戶新增信用額度調整，請使用 **客戶調整** 功能表。 要為客戶信用群組新增信用額度，請選擇 **客戶信用群組調整**。
2. 輸入客戶帳戶作為應使用新信用額度進行更新的發票客戶帳戶。 如果在步驟 1 中選擇 **客戶信用群組調整**，輸入客戶信用群組。 您不能在同一日記帳行中同時輸入客戶帳戶和客戶信用群組識別碼。

    此時會顯示目前的信用額度，並自動顯示名稱。

3. 輸入過帳信用額度分錄時應替換目前信用額度的新信用額度。
4. 輸入日期以定義客戶信用額度的新到期日期。 建立信用額度調整時，您必須輸入信用額度到期日期。

**核准狀態** 欄位表示日記帳行的工作流程狀態。

如果您想自動產生信用額度調整，可以使用動作窗格上的 **產生** 功能表。
 
### <a name="add-temporary-credit-limit-adjustments"></a>新增臨時信用額度調整

要手動新增臨時信用額度調整，請針對日記行執行以下步驟。

1. 要為客戶新增信用額度調整，請使用 **客戶調整** 功能表。 要為客戶信用群組新增信用額度，請選擇 **客戶信用群組調整**。
2. 輸入客戶帳戶作為應使用新信用額度進行更新的發票客戶帳戶。 如果在步驟 1 中選擇 **客戶信用群組調整**，輸入客戶信用群組。 您不能在同一日記帳行中同時輸入客戶帳戶和客戶信用群組識別碼。

    如果已存在有效的或未來的臨時信用額度，則會為每個臨時信用額度顯示目前臨時信用額度和日期範圍。 名稱將自動出現。

3. 輸入應替換目前信用額度的新信用額度。
4. 在 **新開始日期** 和 **新結束日期** 欄位中，定義進階信用額度的有效期限。 建立信用額度調整日記帳時，必須輸入信用額度到期日期。

**核准狀態** 欄位表示日記帳行的工作流程狀態。

## <a name="generate-credit-limit-adjustments"></a>產生信用額度調整

您還可以自動調整信用額度。 在動作窗格上，選擇 **產生**，然後選擇以下選項之一：

- 從現有客戶
- 從現有客戶信用群組
- 自動信用額度

### <a name="from-existing-customer"></a>從現有客戶

您可以從現有客戶建立日記帳行。 當您選擇 **產生 \> 從現有客戶**，將出現一個對話方塊，您可以在其中提供選擇客戶和計算新限制的標準。

1. 輸入調整值以在信用額度中增加或減少金額。 輸入負值以降低目前信用額度或輸入正值以增加額度。
2. 在 **值類型** 欄位，選擇您在步驟 1 中輸入的值應如何用於計算新的信用額度：

    - 選擇 **固定值** 以按金額變更信用額度。
    - 選擇 **百分比** 以按百分比變更信用額度。

3. 輸入用於四捨五入計算出的信用額度的值。 例如，輸入 **10.00** 會將信用額度四捨五入到最接近的 10.00 貨幣單位。
4. 設定 **進位形式** 欄位來指定餘數是進位還是捨去。
5. 選取用於調整日期的方法。

    - 如果選擇 **絕對**，您可以輸入定義信用額度日期範圍的日期。
    - 如果選擇 **相對**，您可以輸入範圍的位移日期。 信用額度的目前日期範圍將透過位移進行調整。

6. 使用 **要包括的記錄** FastTab 篩選包含的客戶清單。 如果不包括篩選條件，則會為所有客戶產生信用額度分錄。
7. 選擇 **確定** 以建立信用額度調整分錄。

### <a name="from-existing-customer-credit-group"></a>從現有客戶信用群組

您可以從現有客戶信用群組建立日記帳行。 當您選擇 **產生 \> 從現有客戶信用群組**，將出現一個對話方塊，您可以在其中提供選擇客戶信用群組和計算新限制的標準。 這些標準與用於從現有客戶建立日記帳行的標準相同。 請參閱上一節中的步驟。

### <a name="automatic-credit-limits"></a>自動信用額度

您可以建立自動信用額度來定義和更新客戶信用額度。 自動信用額度是為風險群組建立的，其是根據評分群組中使用的特定值建立。 您可以使用這些自動信用額度來產生信用額度分錄。 如果已將客戶分配到特定風險群組，並且客戶的信用資訊符合自動信用額度的標準，則會建立信用額度調整分錄。

#### <a name="create-automatic-credit-limits"></a>建立自動信用額度

您可以使用信用額度調整來建立自動信用額度。 選擇 **產生\>自動信用額度** 時，將出現一個對話方塊，您可以在其中設定新信用額度的到期日期，新信用額度將根據分配給客戶的風險群組來建立。 完成後，選擇 **確定** 以建立信用額度調整行。

### <a name="post-adjustments"></a>過帳調整

建立信用額度調整行後，您可以使用動作窗格上的 **過帳** 按鈕過帳分錄並更新客戶信用額度。 但是，如果您已設定工作流程，則必須在動作窗格上選擇 **工作流程 \> 提交** 以提交日記帳進行核准。

### <a name="credit-limit-adjustments-workflows"></a>信用額度調整工作流程

**信用額度調整** 工作流程可用於透過工作流程核准流程傳送信用額度調整。 您可以在 **信用管理工作流程** 頁面 (**信用管理 \> 設定 \> 信用管理工作流程**) 上建立兩個工作流程：

- **信用額度調整** – 此工作流程可用於核准標題等級的分錄。
- **信用額度調整行** – 此工作流程可用於核准調整分錄，以便根據工作流程中的標準，不同人員核准這些分錄。

> [!NOTE]
> 建立 **信用額度調整** 工作流程後，您可以對其進行設定，以便在行核准後自動過帳調整。 只需在工作流程中包括 **自動過帳日記帳** 工作即可。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]