---
title: 根據生產需求變更寄售庫存所有權
description: 此過程顯示當生產有庫存需求時，如何將寄售庫存的所有者從供應商更改為您的法律實體。
author: yufeihuang
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e735a9003f2859ed173f399525297506ec458e8d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447861"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a>根據生產需求變更寄售庫存所有權

[!include [banner](../../includes/banner.md)]

此過程顯示當生產有庫存需求時，如何將寄售庫存的所有者從供應商更改為您的法律實體。 這種所有權變更是以建立和過帳庫存所有權變更日記帳來完成的。 可以手動建立所有權變更日記帳明細，也可以根據現有的生產需求建立，如本記錄內容所示。 通常，由車間主管執行此工作。 您可在 USMF 示範資料公司或自己的資料中執行此程序。 如果您使用自己的資料，請確保您具有以下先決條件：庫存所有權更改已設定庫存日記帳名稱、供應商擁有的現有品項的實際記錄以及物料的一個或多個生產訂單明細。 本道程序是針對在 Dynamics 365 for Operations 版本 1611 新增的功能。

> [!NOTE]
> 沒有預設支援出站寄售流程，也不支援自動所有權日記帳處理。

## <a name="create-an-inventory-ownership-journal"></a>建立庫存所有權日記帳
1. 前往庫存管理 > 日記帳輸入 > 品項 > 庫存所有權變更。
2. 按一下「新增」。
    * 庫存所有權更改日記帳用於將寄售庫存的擁有者從供應商更改為當前法律實體。 透過發佈供應商擁有的現有庫存，然後在當前法律實體中接收該庫存來完成所有權更改。  
3. 在名稱欄位中，輸入或選擇一個值。
    * 您選取庫存日記帳名稱，只能是日記帳類型為所有權變更。  
4. 按一下確定。
5. 按一下「功能」。
6. 按一下從生產訂單建立日記帳明細。
    * 您可以查詢所有有原物料消耗需求的生產線，來啟動所有權變更流程。  
7. 在要包括的庫存出貨狀態欄位中，選取一個選項。
    * 此選項允許您按庫存交易記錄的出貨狀態進行篩選。 例如，您可以為具有已揀選和已保留實際狀態的庫存建立日記帳明細。  
8. 展開記錄以包含區段。
    * 本區段允許您套用其他篩選。 例如，您可以選取特定的原物料日期。  
9. 按一下確定。

## <a name="post-the-inventory-ownership-change-journal"></a>過帳庫存所有權變更日記帳
1. 按一下過帳。
    * 過帳日記帳時，供應商擁有的庫存使用「所有權變更」參考來發佈。 然後，使用以訂購單產品接收更新的庫存交易來接收現有庫存。 請注意，僅建立與已過帳日記帳相關的交易。 未建立預期的庫存交易記錄。  
2. 按一下確定。
3. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]