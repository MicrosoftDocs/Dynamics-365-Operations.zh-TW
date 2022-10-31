---
title: 帳戶結構啟用效能增強
description: 本文章說明帳戶結構啟用程序的新效能增強。
author: RyanCCarlson2
ms.date: 10/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-10-08
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 42f8fcebba6465261489f74a9bb1dd46c2d5fa16
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2022
ms.locfileid: "9713991"
---
# <a name="account-structure-activation-performance-enhancement"></a>帳戶結構啟用效能增強

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

此效能增強讓您透過同時執行多個交易更新來更快啟用帳戶結構。 此外，結構本身在經過驗證之後會標記為使用中，並且在現有未過帳交易更新至新結構的同時，交易處理可以繼續進行。 由於交易更新可能需要花一些時間，您可以選取 **帳戶結構** 頁面的格線上方的 **檢視啟用狀態** 來追蹤啟用狀態。 您也可以選取執行窗格上的 **檢視**，然後選取下拉式功能表中的 **啟用狀態** 來檢視您的啟用狀態。

[![帳戶結構頁面。](./media/AccountStructure1.png)](./media/AccountStructure1.png)

選取 **檢視啟用狀態** 之後，將出現一個對話方塊，其中會顯示視同啟用程序的一部分而執行的個別任務。 您可以檢視每項任務的狀態，並在任務完成後檢視其完成日期和時間。

[![帳戶結構啟用時間表。](./media/AccountStructureTimeline.png)](./media/AccountStructureTimeline.png)

## <a name="account-structure-activation-tips"></a>帳戶結構啟用提示

當您針對草稿帳戶結構選取 **啟用** 時所出現的帳戶結構啟用對話方塊中，會有一個名為 **更新未過帳交易** 的索引標籤區段。 本區段包括一個名為 **強制更新** 的選項。 您可以選取此選項，將所有未過帳交易更新至目前的結構。 但是，只有在發生錯誤或 Microsoft 支援服務指示您使用此選項時，您才應使用此選項。

以下是一些可能影響啟用程序效能的因素：

- 大量的未過帳日記帳記錄
- 大量的開放來源文件記錄，例如普通發票、廠商發票以及使用來源文件架構且具有未完成會計分配的相關文件
- TaxUncommitted 中的資料量
- 未結預算資料的金額
- 啟用任務仍在執行時匯入的日記帳資料

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
