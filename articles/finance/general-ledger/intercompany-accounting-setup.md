---
title: 公司間會計設定。
description: 本主題解釋如何設定公司間會計，如此您便能將公司間日記帳用於分類帳配置和財務日記帳，例如日常日記帳、廠商發票日記帳和付款日記帳。
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: roschlom
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09c8933b08710ec82dbb449f2ba7f7c29cc24ff3a4c9b73178aa916ea0fab83a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450153"
---
# <a name="intercompany-accounting-setup"></a>公司間會計設定。

[!include [banner](../includes/banner.md)]

本主題解釋如何設定公司間會計，如此您便能將公司間日記帳用於分類帳配置和財務日記帳，例如日常日記帳、廠商發票日記帳和付款日記帳。

公司間日記帳可在各類可能情況中建立，例如日常日記帳、廠商發票日記帳、分類帳配置和集中付款。 若要啟用這些可能情況，您必須設定公司間會計。

## <a name="define-main-accounts"></a>定義主科目
首先，您必須建立公司間主科目用於應付和應收會計分錄。 為每間公司使用唯一的主帳戶是很好的構想，可簡化公司間會計分錄的對帳和消除。 如果您使用貿易夥伴或對象維度辨別公司間合作對象，您可以將此維度定義為公司間會計定義的主科目固定維度。 設定主帳戶時，您應設定 **主科目類型** 欄位到 **主科目** 頁面上的 **資產負債表**。

## <a name="define-journal-names"></a>定義日記帳名稱
接著，您必須定義日記帳名稱。 設定 **日記帳類型** 欄位到 **日記帳名稱** 頁面上的 **日常帳**。 為公司間會計使用特定日記帳名稱是個好構想。

## <a name="define-intercompany-accounting-setup"></a>定義公司間會計設定
**公司間會計** 頁面用來建立可以互相交易的法人實體對。 公司間會計設定是共用的，因此所有法人實體內都可見到設定。 建立新法人實體對時，請確保您會留意定義為發起公司與目標公司的法人實體。 輸入公司間交易時，交易會判定初始化或發起交易的法人實體。 例如，公司間會計是針對 USMF (發起) 和 USSI (目的地) 設定。 如果使用者在 USSI 處於有效狀態並且進入與 USMF 的公司間交易，則此筆交易將不會過帳，因為公司間會計只針對發起人的 USMF 定義。 如果任一間公司可發起交易，您將必須建立第二個法人實體對進行互惠設定。 

請為發起與目的地法人實體選取 **借記帳戶 (收款到期日)** 和 **貸記帳戶 (付款到期)**。 **日記帳名稱** 的定義將於目的地公司建立交易時使用。 發起公司日記帳為已知帳，因為它由使用者在建立公司間交易時選取。 

最後，選取將收到佐證金額會計帳務的法人實體，例如現金折扣或集中付款的已實現利益/損失。 

互惠關係可以等到第一間法人實體建立後，藉由在 **公司間會計** 頁面使用 **建立互惠關係** 按鈕輕鬆設定。 互惠對建立時，目的地公司資訊將複製到發起公司，反之亦然。 為目的地公司定義的日記帳將保持不變。 大多數組織對其日記帳名稱使用相同命名慣例，因此日記帳名稱會相同。 如果日記帳名稱不同，欄位上會出現警告，通知您日記帳不存在，可選取不同日記帳。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]