---
title: 建立服務合約
description: 本主題說明如何使用服務管理及專案管理和會計模組中的功能來建立服務合約。
author: kamaybac
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9a5d580b0bb146bf5d445823b37f607e507f7eb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448185"
---
# <a name="create-service-agreements"></a>建立服務合約

[!include [banner](../includes/banner.md)]

本主題說明如何使用服務管理及專案管理和會計模組中的功能來建立服務合約。

## <a name="create-a-service-agreement-from-service-management"></a>從服務管理建立服務合約

1. 前往 **服務管理**。
2. 選擇頁面標題的 **服務合約** 來建立新的服務合約明細。 
3. 選擇 **新增**。 輸入描述、在 **專案識別碼** 欄位選擇專案參考，然後填寫該服務合約的其餘欄位和明細。 選擇 **儲存**。
4. 在 **關係** 索引標籤上，選擇 **服務物件** 或 **服務工作**，為該服務合約建立服務物件關係或服務工作關係。 您建立的服務物件和工作關係可附加至服務合約的明細。
5. 在頁面下半部複製服務範本、另一個服務合約的明細，即可建立服務合約明細，亦可手動建立服務合約明細。

> [!NOTE]
> 若您將明細從另一份服務合約複製到此服務合約，您可選擇是否要同時複製服務物件和服務工作關係。 若您複製這些關係，則這些關係會新增至此服務合約現有的任何關係。 若您從服務範本複製服務合約明細，則服務物件和服務工作關係也會自動複製，成為新的服務合約明細的服務物件關係和服務工作關係。

## <a name="create-service-agreement-lines-manually"></a>手動建立服務合約明細

1. 在 **服務合約** 頁面，於明細網格新增服務合約明細。 
2. 輸入服務合約明細相應的資訊。 
3. 選擇 **儲存** 來儲存明細，然後關閉頁面。

## <a name="create-a-service-agreement-from-project"></a>從專案建立服務合約

1. 選擇 **專案管理和會計**。
2. 選擇 **所有專案**。
3. 從清單中選擇專案。
4. 在 **動作窗格** 上，選擇 **管理**。 在 **新增** 動作群組中，選擇 **服務** 再選擇 **服務合約**。
5. 遵循此主題之前在 **建立服務合約** 一節說明的步驟，輸入專案參考。


## <a name="related-topics"></a>相關主題

[制定和建立服務合約概觀](service-agreements.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]