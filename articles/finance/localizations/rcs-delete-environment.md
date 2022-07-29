---
title: Regulatory Configuration Service (RCS) - 刪除 RCS 環境
description: 本主題說明 Regulatory Configuration Service (RCS) 系統管理員如何刪除 RCS 環境和相資料。
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: f9073a14143423676f23f9bf8dc9c17dbae18a6c3ad0d2f6d1e33919fd9162bf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450624"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>Regulatory Configuration Service (RCS) - 刪除 RCS 環境

[!include [banner](../includes/banner.md)]

本主題說明 Regulatory Configuration Service (RCS) 系統管理員如何刪除 RCS 環境和相資料。

完成本主題的程序之前，必須先符合先決行件如下：

- 你必須具備指派您 RCS 環境的 **系統管理員** 角色。
- **系統管理員** 角色必須具備指派的 **RCSDeleteEnvironmentDuty** 角色。

## <a name="delete-an-rcs-environment"></a>刪除 RCS 環境

1. 打開 RCS 並且選取 **電子報表** 工作區圖格。
2. 在 **相關連結** 專區，選取 **刪除 RCS 環境**。

    ![在 Related 連結專區刪除 RCS 環境連結。](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. 在出現的對話方塊中，審視有關環境刪除範圍的訊息。

    ![刪除 RCS 環境對話方塊的訊息。](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > 無法撤消對 RCS 環境的刪除。
    >
    > 操作刪除已選取的 RCS 環境和任何相關資料，包括儲存在 Global 存放庫的功能和組態。 與其他組織共用的功能和組態如果沒有相依性，將被取消共用和刪除。 有相依性的功能和組態將被標記為已中斷。

4. 在提供的欄位中，輸入 RCS 環境的全域唯一識別碼 (GUID) 以便確認希望刪除。 環境的 GUID 納入刪除訊息。
5. 選取 **刪除環境**。
    
您的 RCS 環境和任何相關資料現在皆已刪除。

> [!IMPORTANT]
> 刪除 RCS 環境後，無法復原資料。 新 RCS 環境可以在任何開放使用的 RCS 區域建立。
