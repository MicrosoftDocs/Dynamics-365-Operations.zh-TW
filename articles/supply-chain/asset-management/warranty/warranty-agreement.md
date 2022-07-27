---
title: 擔保合約
description: 本主題說明「資產管理」中的擔保合約。
author: johanhoffmann
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8269b9f2084ddd0f69039044c29978ce7940270d5b569456f7a0bfca0a6f1f0b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446838"
---
# <a name="warranty-agreements"></a>擔保合約

[!include [banner](../../includes/banner.md)]

 


在資產管理中，您可以設定能連接到資產或資產類型的擔保條款。 擔保條款是針對特定期限建立的。 可以設定擔保以提供完整涵蓋或部分涵蓋，您可以設定與工時、費用和品項相關的條款。

第一步是為您的設備建立任何廠商擔保合約。 然後，將擔保合約附加到資產或資產類型。 廠商擔保合約僅供參考。 如果為資產設定了廠商擔保，則可以查看資產的擔保涵蓋期間。

## <a name="create-a-warranty-agreement"></a>建立擔保合約

擔保合約可以包括多個合約行，以涵蓋工作時間、費用和品項的擔保。

1. 選取 **資產管理** \> **設定** \> **資產** \> **擔保**。
2. 選取 **新增** 以建立產品。
3. 在 **擔保** 欄位中，輸入擔保識別碼。 
4. 在 **名稱** 欄位中，輸入描述。

    在 **詳細資料** FastTab 的 **資產** 欄位顯示使用擔保合約的使用中資產的數量。

5. 在 **擔保行** FastTab 中，請按照以下步驟新增應包含在擔保合約中的行：

    1. 選擇 **新增行** 將新條件新增到擔保。 一個序號型的行編號會自動輸入到 **行** 欄位。
    2. 在 **期間** 欄位中，選擇擔保期間的類型。
    3. 在 **間隔** 欄位中輸入數字。 此欄位定義擔保的有效期間數。
    4. 在 **百分比** 欄位中，輸入擔保行的涵蓋百分比。 該百分比表示您公司涵蓋的量。

![擔保頁面。](media/01-warranty.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]