---
title: 更正普通發票
description: 本文介紹如何更正已過帳的普通發票，並將其作為更正後的發票重新開立該發票。
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf4503e3d4b200219d6b444b69c866871d21787d
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451155"
---
# <a name="correct-a-free-text-invoice"></a>更正普通發票

[!include [banner](../includes/banner.md)]

本文介紹如何更正已過帳的普通發票，並將其作為更正後的發票重新開立該發票。

要更正已過帳的普通發票，請打開已過帳的普通發票。 在 **發票** 頁面上，選擇 **取消**，接著選擇 **更正發票**。 選擇原因代碼，新增註釋，然後選擇新更正發票的日期。 您可以修改更正後的發票，然後過帳。 

當您過帳更正的發票時，將為等於原始發票金額的貸方金額建立取消發票。 因此，原始發票和取消發票的組合餘額為 0 (零)。 取消發票根據原始發票結算。 

過帳更正後的發票後，您將擁有三張發票：

-   **原始發票** – 包含您正在更正的資訊的發票。
-   **取消發票** – 為取消最近更正的發票而建立的系統產生的貸方發票。
-   **更正發票** – 包含更正發票資訊的發票。

您可以透過兩種方式識別取消和更正發票：

-   **所有普通發票** 頁面包括 **更正** 欄，可在其中查看哪些發票是正在取消發票和已更正發票。
-   普通發票的抬頭顯示狀態為 **取消發票'\[發票編號\]'** 或 **更正發票'\[發票編號\]'**。

> [!NOTE]
> 此功能只有在選取了 **普通發票更正** 組態金鑰時才可供使用。 有關如何啟用組態金鑰的更多資訊，請參閱[維護模式](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)主題中的啟用 (或停用) 組態金鑰區段。 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
