---
title: 資產重要性類型
description: 本主題說明資產管理中的資產重要性類型。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9edf55c22375a66fda04ae7ff76d7a0a191140e5ffb3a377b9ac1a7ba604a8d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447276"
---
# <a name="asset-criticality-types"></a>資產重要性類型

[!include [banner](../../includes/banner.md)]

 

本主題說明資產管理中的資產重要性類型。 資產重要性與資產相關，並轉移到工單。 無法在工單上變更重要性。 資產關鍵性用於計算工單排程期間的工單重要性。 換句話說，它用於計算資產維護作業對貴公司生產排程和生產力的影響程度。 如需與工單排程評等分數相關的設定詳細資訊，請參閱[資產管理參數](../setup-for-objects/enterprise-asset-management-parameters.md)。

若要設定重要性，您須先建立應在資產設定中使用的重要性類型。 接著，您要設定資產重要性。

## <a name="set-up-criticality-types"></a>設定重要性類型

1. 選取 **資產管理** \> **設定** \> **資產** \> **重要性模型**。
2. 選取 **新增** 建立記錄。
3. 在 **重要性** 欄位，輸入一個表示重要性的數字。
4. 在 **名稱** 欄位中，輸入重要性類型的名稱。
5. 在 **係數** 欄位中，輸入一個係數。 此係數用於計算工單排程期間，以決定應使用的重要性記錄。 (一律使用具有最高係數的記錄。) 如果建立具有相同重要性值的重要性明細，如下圖所示，則此設定是相關的。

    ![重要性類型頁面。](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a>設定資產重要性

1. 選取 **資產管理** \> **設定** \> **資產重要性**。
2. 選取 **新增** 建立記錄。
3. 根據資產重要性所需的詳細資料層級，在 **功能位置**、**資產類型**、**製造商**、**模型**、**資產**、**作業類型類別**、**作業類型**、**作業類型變體** 和 **作業需求** 欄位中進行相關選擇。

    > [!NOTE]
    > 若有選取資產重要性，資產管理會檢查所有資產重要性記錄以檢查可能的符合項目。 一律先檢查最具體的組合。 換句話說，資產管理會先檢查 **作業需求**。 如果未找到符合項目，則會檢查 **作業類型變體**。 如果未找到符合項目，則會檢查 **作業類型** 等等。 正如您在頁面配置上所見，此行為意味著為了找到最具體的組合，資產管理會從右到左檢查每條記錄以找出符合項目。 如果未找到符合項目，則會使用沒有選擇的「預設」記錄。

4. 在 **重要性** 欄位中，選取您在上一個程序中建立的重要性值之一。

### <a name="notes-about-criticality-setup"></a>關於重要性設定的說明

- 如果您在工單中使用資產重要性後，變更此設定中的重要性，系統不會相應地更新工單的重要性。
- 每次在工單中新增或刪除工單明細時，都會重新計算工單的重要性。
- 如果工單包含多個工單作業，則會根據 **重要性類型** 頁面的 **係數** 欄位，一律在工單上使用最高重要性。
- 通常，資產重要性會在一段時間內發生變化。 購買新設備、翻新等可能會影響重要性。 考慮定期重新評估您的資產重要性 (例如，每年一次或每隔一年)，以確保重要性定義符合您目前的生產設定。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]