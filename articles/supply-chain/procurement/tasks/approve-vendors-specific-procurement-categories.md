---
title: 核准特定採購類別的供應商
description: 本主題解釋在 Dynamics 365 Supply Chain Management 如何核准特定採購類別供應商。
author: Henrikan
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a885ba924137c56583db9f81b34db9a20f33bc4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448209"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>核准特定採購類別的供應商

[!include [banner](../../includes/banner.md)]

本主題解釋在 Dynamics 365 Supply Chain Management 如何核准特定採購類別供應商。 建立採購申請時，依據採購原則設定的方式，可能申請選取已核准或偏好的供應商。 此流程展示如何在特定採購類別指定核准或偏好的供應商。 此工作通常由採購專業人員執行。 您可以在 USMF 示範公司資料中使用此程序。

1. 在瀏覽窗格中，移至 **模組 > 採購及開源 > 供應商 > 所有供應商**。
2. 選取供應商，以設定為類別的核准或偏好供應商。
3. 在 [動作窗格] 上，選取 **一般**。
4. 選取 **類別**。
5. 選取 **新增類別**。
6. 在 **類別** 欄位，選取 **辦公室和辦公桌配件 (辦公室和辦公桌配件)**。
7. 在 **供應商類別狀態** 欄位，選取 **偏好**。 可以為一個類別指定多個偏好供應商。  
8. 選取 **儲存**。
9. 在瀏覽窗格，前往 **模組 > 採購及開源 > 採購類別**。
10. 在樹狀圖中，選取 **公司採購類別\辦公室和辦公桌配件**。
11. 展開 **供應商** 區段。 檢查選取的供應商是否在辦公室和辦公桌配件類別顯示為偏好供應商。 如果您將此流程作為工作指南執行，您可能必須選取 **解除鎖定** 按鈕，才可以向下滾動到供應商列表。  也可以在此頁面上新增偏好和核准供應商。  
12. 在樹狀圖中，展開 **辦公室和辦公桌配件** 並選取 **剪刀**。
13. 在 **從父類別繼承供應商：** 欄位，選取 **不**。
14. 在 **從父類別繼承供應商：** 欄位，選取 **是**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]