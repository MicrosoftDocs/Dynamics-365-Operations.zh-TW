---
title: 重新分類固定資產
description: 本主題解釋重新分類資產的流程。 為了要重新分類固定資產，您必須移轉到新固定資產群組或在相同群組指派新固定資產編號。
author: moaamer
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5fadebe685810d6833d1cb0581ed9a4869cc124
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451257"
---
# <a name="reclassify-fixed-assets"></a>重新分類固定資產

[!include [banner](../../includes/banner.md)]

為了要重新分類固定資產，您必須移轉到新固定資產群組或在相同群組指派新固定資產編號。 

重新分類固定資產時：

- 既有固定資產的所有帳冊皆按照新固定資產建立。 針對原始固定資產設定的任何資訊皆將複製到新固定資產。 原始固定資產的帳冊狀態為已關閉。 

- 新固定資產的新帳冊包含在 **取得日期** 欄位重新分類的日期。 **折舊執行日期** 欄位的日期是從原始資產資訊複製而來。 如果折舊已經開始，**上次執行折舊日期** 欄位會顯示重新分類的日期。 

- 原始固定資產的既有固定資產交易會取消，並為新固定資產重新產生。

- 有轉移交易的資產重新分類時，系統將在 **動作中心** 顯示訊息，指出重新分類期間尚未完成的轉移交易。 完成轉移交易並將既有的重新分類交易移到適當的財務維度是必要之舉。 

   重新分類期間，系統執行下列動作將資產餘額從原始資產重新分類到新資產。 
   
   - 重新分類流程將資料從原始固定資產帳冊複製到新固定資產帳冊。

   - 重新分類交易使用原始過帳的取得資訊，包括納入取得交易的財務維度資訊。  
   
   - 同時，重新分類流程逆轉原始資產取得和資產移轉交易。 

下列示意圖和程序提供重新分類流程範例。 

[![顯示重新分類流程示意圖。](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)

按照下列步驟重新分類固定資產：

1. 前往 **固定資產 > 定期任務 > 重新分類。**
2. 在 **固定資產群組** 欄位，選取要重新分類的群組。
3. 在 **固定資產編號** 欄位，選取要重新分類的固定資產。
4. 在 **新固定資產群組** 欄位，選取要移轉固定資產的群組。
    * 如果新固定資產群組按編號順序附上，則 **新固定資產編號** 欄位會以新固定資產群組編號順序的編號更新。 否則，**新固定資產編號** 欄位會以在 **固定資產參數** 頁設定編號順序時的編號更新。 如果編號順序未在 **固定資產參數** 頁設定，請在 **新固定資產編號** 欄位輸入編號。  
5. 在 **重新分類日期** 欄位，輸入日期。
6. 在 **憑單系列** 欄位，輸入或選取一值。
7. 選取 **確定**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
