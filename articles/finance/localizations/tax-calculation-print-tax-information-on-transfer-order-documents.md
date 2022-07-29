---
title: 在轉移訂單文件上列印稅務資訊
description: 本主題說明如何將稅務計算服務確定的稅務資訊列印在轉移訂單文件上。
author: Kai-Cloud
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-10-12
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 174cbd85139db5cee75481041fb721dc7646ab66
ms.sourcegitcommit: eef5d9935ccd1e20e69a1d5b773956aeba4a46bc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2021
ms.locfileid: "8451305"
---
# <a name="print-tax-information-on-transfer-order-documents"></a>在轉移訂單文件上列印稅務資訊

[!include [banner](../../includes/banner.md)]

本主題說明如何列印轉移訂單文件上的稅務資訊。 您可以列印根據歐盟 (EU) 增值稅 (VAT) 法規被視為歐盟境內供應和歐盟境內取得的庫存轉移轉移訂單的估價單文件。 

以下與稅務相關的資料將添加到轉移訂單文件: 

- 庫存轉移的名稱和出貨地址和收貨地址
- 供應商和收件者的稅務識別編號
- 供應貨物的單價和應稅金額
- 稅碼、稅率、稅額和稅收指令

要設定此資料，您必須完成以下主要步驟。

1. [啟用和設定轉移訂單的稅務功能](tasks/Tax-feature-support-for-transfer-order.md)。
2. [為法律實體建立和設定多個稅務登記編號 ](emea-multiple-vat-registration-numbers.md)。
3. 在稅碼中設定免稅代碼、說明、稅務指令和列印代碼。 對於此示例，在 Microsoft Dynamics 365 Finance中建立並同步了三個稅碼: **NL-Exempt**,**BE-RC-21**，和 **BE-RC+21**。

    1. 請在 Finance 前往 **稅務**\>**設定**\> **銷售稅**\> **銷售稅免稅代碼**。
    2. 選擇 **編輯**，並輸入 **EC** 免稅代碼的說明。 例如，輸入 **帶有稅務登記編號的免稅 EC 貨件**。
    3. 前往 **稅務** \> **間接稅** \> **銷售稅** \> **銷售稅代碼**。
    4. 選擇 **BE-RC-21** 稅碼，然後選擇 **稅收指令**。
    5. 選取 **新增**。
    6. 在 **語言** 欄位，選擇 **EN-US**。 接著，在 **Text** 欄位，輸入 **歐盟增值稅指令 2006/112/EC 第 138. 2. c) 條規定的貨物轉移文件**。
    7. 關閉頁面。
    8. 在 **一般** FastTab，在 **列印** 欄位選擇 **銷售稅率**。
    8. 選擇 **NL-Exempt** 稅碼，然後在 **一般** FastTab，在 **列印** 欄位選擇 **銷售稅率**。

    > [!NOTE] 
    > 如果沒有為稅碼維持免稅代碼說明或稅務指令，則稅碼、稅率和免稅說明不會列印在轉移訂單文件上。

## <a name="print-the-transfer-order---shipment-document"></a>列印轉移訂單-裝運文件

轉移發貨後，請按照以下步驟列印轉移訂單 - 裝運文件。

1. 前往 **庫存管理**\>**查詢和報告**\>**轉移訂單**\>**運送**。
2. 在 **參數** 索引標籤，在 **列印** 群組，啟用 **稅務資訊**。
3. 在 **要包括的記錄** 索引標籤，選擇 **篩選**，選擇轉移訂單編號，然後選擇 **確定**。
4. 選擇 **確定** 列印轉移訂單-裝運文件。

## <a name="print-the-transfer-order---receipt-document"></a>列印轉移訂單-接收文件

收到轉移後，請按照以下步驟列印轉移訂單 - 接收文件。

1. 前往 **庫存管理**\>**查詢和報告**\>**轉移訂單**\>**接收**。
2. 在 **參數** 索引標籤，在 **列印** 群組，啟用 **稅務資訊**。
3. 在 **要包括的記錄** 索引標籤，選擇 **篩選**，選擇轉移訂單編號，然後選擇 **確定**。
4. 選擇 **確定** 列印轉移訂單-接收文件。

## <a name="print-the-transfer-overview-document"></a>列印轉移概覽文件

按照以下步驟列印轉移概覽文件。

> [!NOTE]
> 僅當轉移訂單已發貨或收到時，才可使用稅務資訊。

1. 前往 **庫存管理**\>**查詢和報告**\>**轉移訂單**\>**轉移概覽**。
2. 在 **參數** 索引標籤，在 **列印** 群組，啟用 **稅務資訊**。
3. 在 **要包括的記錄** 索引標籤，選擇 **篩選**，選擇轉移訂單編號，然後選擇 **確定**。
4. 選擇 **確定** 列印轉移概覽文件。

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
