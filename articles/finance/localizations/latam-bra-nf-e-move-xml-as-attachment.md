---
title: 移動 NF-e XML 檔案附件
description: 本主題說明如何將 NF-e XML 檔案移出 Microsoft Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 資料庫並使它們改為附件開放使用。
author: gionoder
ms.date: 11/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: c7b82d486cecf6b20f1283fa609c360b3003efca
ms.sourcegitcommit: ebf6546835e4d6a80aea1dfae81e119e294387f0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2021
ms.locfileid: "8451191"
---
# <a name="move-nf-e-xml-files-as-attachments"></a>移動 NF-e XML 檔案附件

[!include [banner](../includes/banner.md)] 


核發電子財務文件 (NF-e) 時，會建立 XML 檔案並儲存在 Microsoft Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management 資料庫。 您可以在巴西在地化過程中使用 **NF-e XML 附件移動** 功能釋放這些 XML 檔案佔用資料庫的空間。

特定日期範圍和財務設立方面，此功能將 NF-e XML 檔案從您的 Finance 或 Supply Chain Management 資料庫移動到您訂閱 Azure 的 Blob 儲存裝置。 這類移動會使文件只以附件形成開放使用。 XML 檔案成功移動到 Blob 儲存裝置後，原始檔案將從 Finance 或 Supply Chain Management 資料庫刪除。 因此會釋出這些檔案使用的資料庫空間。

按照這些步驟啟用 **NF-e XML 移動附件** 功能。

1. 在 Finance 或 Supply Chain Management 中，打開 **功能管理** 工作區。
2. 在 **全部** 索引標籤上搜尋和選取 **NF-e XML 移動附件** 功能。
3. 選取 **立即啟用**。

按照這些步驟將 NF-e XML 檔案以附件形式移動。

1. 前往 **應收帳款**\>**財政文件**\>**電子財政文件**\>**將 NF-e XML 以附件形式移動**。
2. 在 **開始日期** 和 **截止日期** 欄位，選取開始和結束日期。
3. 在 **財政機構識別碼** 欄位，輸入一值。
4. 選取 **確定**。

> [!IMPORTANT]
> 此段流程不可逆。 待您移動 NF-e XML 檔案後，使用者只能藉由選取 **財政文件** 頁面最上方的 **附件** 檢視。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
