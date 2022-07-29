---
title: 設定原因代碼
description: Dynamics 365 Human Resources 使用原因代碼來解釋員工福利變動的原因。
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a30a59a648d54eda771845b8bee52df43987d3d1
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452433"
---
# <a name="set-up-reason-codes"></a>設定原因代碼


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources 使用原因代碼來解釋員工福利變動的原因。

> [!NOTE]
> 自 2021 年一月起，原因代碼已經遷移到 **人事管理** 工作區而不是 **福利管理** 工作區。 更多資訊，請參閱[手動遷移原因代碼到人事管理](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management)。

## <a name="create-reason-codes"></a>建立原因代碼

1. 請在 **人事管理** 工作區 (或者如果您的原因代碼尚未遷移，則 **福利管理** 工作區) 中選取 **連結**，然後選取 **原因代碼**。

2. 選取 **新增**。

3. 請指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **原因代碼** | 用來辨別員工會變更福利計劃註冊原因的唯一名稱。 |
   | **描述** | 原因代碼說明。 |

4. 請在 **適用方案** 下方設定 **福利管理** 為 **是**。 (如果您的原因代碼尚未遷移到 **人事管理** 工作區，則不適用。)

5. 選取 **儲存**。

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>手動遷移原因代碼到人事管理

2021 年一月，原因代碼已經遷移到 **人事管理** 工作區而不是 **福利管理** 工作區。 大多數原因碼資料將在您的環境自動遷移。 某些原因代碼資料可能不會遷移。 例如，原因代碼現在最多有 15 個字元，因此超過 15 個字元的原因代碼將不自動遷移。

您將在 **福利管理** 工作區的 **連結** 頁面上看到橫幅列，知會您有關遷移一事以及有無任何原因代碼並未遷移。

1. 請選取 **原因代碼** 了解有關遷移狀態的細節。

   [![原因代碼。](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. 請選取未能遷移的原因代碼。

   [![原因代碼遷移狀態。](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. 請選取 **遷移原因代碼**。

   [![遷移原因代碼。](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. 您在 **福利原因代碼遷移** 窗格中兩個選項用於測繪人事管理原因代碼：

   - 若要在人事管理中使用既有的原因代碼，請從 **使用既有原因代碼** 下拉選單任選一個。
     > [!NOTE]
     > 如果另一個福利管理原因代碼尚未遷移到既有的原因代碼，您只能在人事管理中使用既有的原因代碼。
   - 若要在人事管理中建立新原因代碼，請在 **新原因代碼** 中輸入一個新代碼，然後在 **新說明** 中輸入說明。

   [![測繪到人事管理原因代碼。](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

待原因代碼遷移到人事管理後，用來在福利管理中使用它們的選項會自動設定為 **是**。

[![在福利管理中使用原因代碼。](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
