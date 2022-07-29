---
title: RCS/全域存放庫中的 RCS 增強篩選
description: 本主題介紹 RCS Global 存放庫的增強篩選功能，這些功能已得到改進，包括額外的篩選器。
author: JaneA07
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2def3b653ac7c90318feb696c0dd197217ac29f64f0f08d26a7069918c67922b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450846"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>用於在 RCS/Global 存放庫中查找配置的 RCS 增強篩選選項

[!include [banner](../includes/banner.md)]

本主題描述了 Regulatory Configuration Services (RCS) 全局存放庫的增強篩選功能，這些功能已得到改進，包括使用以下條件進行篩選的能力： 
- **國家/地區**- 基於 ISO 國家代碼  
- **標籤** 類型：
  - 功能區域
  - 特色區域
  - 產業 
  - 商業文件 

為了更容易發現特定或相關配置，您可以單獨或作為一組應用篩選器。 例如，要查找與供應商發票相關的單一類型的「可配置業務文件」，您可以應用 **業務單據類型** 篩選以搜尋該類型的文件。 

[![全局存放庫的篩選器部分。](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

您可以通過選擇文件類型來進一步細化搜尋，例如「供應商發票」並點擊 **應用篩選器**. 以下示例顯示了篩選時的結果 **業務單據類型** 新增了文件類型。 

[![為業務文件類型應用篩選器和匯入。](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

篩選後的結果可以匯入用戶 RCS 存放庫或Dynamics 365 Finance環境，單獨或作為一組。 為此，請選擇配置組，然後點擊 **進口**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]