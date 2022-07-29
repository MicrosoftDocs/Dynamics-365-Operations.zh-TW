---
title: 設定與處理經常性發票
description: 本文說明如何設定與處理經常性發票。 如果您必須定期為客戶開立相同金額的發票，則可以使用經常性發票。
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 53b667b8a5aef0a788abd6a9d5d4a3b4d8d890e2a18bb5f74e58bb198fab5fa8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450471"
---
# <a name="set-up-and-process-recurring-invoices"></a>設定與處理經常性發票

[!include [banner](../includes/banner.md)]

本文說明如何設定與處理經常性發票。 如果您必須定期為客戶開立相同金額的發票，則可以使用經常性發票。

## <a name="create-a-recurring-free-text-invoice-template"></a>建立經常性普通發票範本

若要定期為客戶開立相同服務的發票，您必須定義一個可重複用於建立發票的普通發票範本。 此範本包含以下資訊: 

-   標頭資訊，例如稅務群組、付款條件和付款方式
-   明細行資訊，例如服務描述、收入帳戶、單價和發票金額。
-   運輸或處理費用
-   會計分配連同財務維度資訊，例如成本中心和事業單位

事實上，您正在建立一個完整的發票，並將其儲存為範本。 您可以使用 **經常性發票** 頁面設定範本。

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a>將普通發票範本指派給客戶，並輸入週期性詳細資料
建立範本後，您必須將範本指派給您要開立發票的客戶。 此外，您必須指定發票的使用時間和頻率。 您可以在 **客戶** 頁面的 **發票** 索引標籤上指派範本。 將範本新增到清單，並更新以下資訊: 

-   定期計費的開始日期及選擇性結束日期
-   定期計費的頻率 (例如，每天或每月一次)
-   計費金額上限 (如果此資訊為必填)

一個客戶可以擁有多個頻率不同的範本。

## <a name="generate-the-recurring-invoices"></a>產生經常性發票
在 **經常性發票** 頁面上，會有一個工作處理經常性發票範本。 您指定發票日期及產生發票的範本。 系統將產生發票，並為所處理的每組發票指派一個週期識別碼。

## <a name="post-recurring-free-text-invoices"></a>過帳經常性普通發票

產生經常性發票後，發票週期識別碼會出在 **經常性發票** 頁面的過帳工作中。 您可以按一下連結來檢視週期識別碼的所有發票。 在檢閱週期識別碼的發票期間，您可以刪除個別的發票。 系統將為該範本重設客戶的週期性設定，以便日後可以重新產生該範本。 您可以過帳週期識別碼的一個、多個或所有的發票。 如果已啟用工作流程，您必須先按一下 **提交**，再過帳發票。

## <a name="print-recurring-free-text-invoices"></a>列印經常性普通發票

過帳經常性發票後，您可以從普通發票清單頁面列印發票。 您可以列印所選的發票，也可以選取要列印的發票範圍。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]