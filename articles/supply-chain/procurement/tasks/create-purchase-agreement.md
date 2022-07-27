---
title: 建立購買合約
description: 本主題將指導您建立購買合約。
author: Henrikan
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee2cf437446f2e4c2cdd3cc0cd3be863bbafa132
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447813"
---
# <a name="create-a-purchase-agreement"></a>建立購買合約

[!include [banner](../../includes/banner.md)]

本主題將指導您建立購買合約。 這通常由採購經理完成。 您可用示範資料公司 USMF 或自己的資料來使用此程序。 在開始之前，您需要設定購買合約分類。 建立合約後，您可以在建立 PO 時使用，這會將購買合約的條件，複製到標題及合約中任何受影響的明細。


## <a name="create-a-new-purchase-agreement"></a>建立新的購買合約
1. 前往 **功能窗格 > 模組 > 採購及開源 > 購買合約 > 購買合約**。
2. 按一下 **新增**。
3. 在 **廠商帳戶** 欄位中，選擇下拉功能表，並選擇需要記錄的列。
4. 在 **購買合約分類** 欄位中，選擇下拉功能表，並選擇需要記錄的列。
5. 展開 **一般** FastTab。
6. 在 **到期日** 欄位中，輸入日期。

    - 此到期日期將是所有承諾用量行的預設日期，並會決定每個特定承諾用量的有效期。  

7. 在 **文件標題** 欄位中，輸入您購買合約的名稱。

    - 保持 **預設承諾用量** 欄位設定為 **產品數量承諾用量** (或者，如果尚未設定，就將其變更為此設定)。  
    - 預設承諾用量的值，會決定您在合約行上的選項。 如果創建合約行時，您需要新的承諾用量類型，需要變更標題上的預設承諾用量。 有 4 種承諾用量類型：**產品數量承諾用量** - 對於特定數量的產品；**產品價值承諾用量** - 針對產品的特定貨幣金額；**產品類別價值承諾用量** - 對於採購類別中的特定貨幣金額，該金額可以是目錄項目或非目錄項目；**價值承諾用量** - 對於可以由任何產品或任何採購類別履行的特定貨幣金額。  

8. 選擇 **確定**。

## <a name="add-a-commitment"></a>新增承諾用量
1. 選擇 **新增明細**。
2. 在 **項目編號** 欄位中，從下拉功能表中選擇需要的紀錄。
3. 在 **數量** 欄位中，輸入一個數字。 這是您同意從供應商購買的總數量。  
4. 在 **單價** 欄位中，輸入一個數字。
5. 展開 **行詳細資訊** 區段。
6. 將 **強制實行最大值** 選項設定為 **是**。 **強制實行最大值** 選項限制使用承諾用量。 您最多只能購買 **數量** 欄位指定的數量。  

## <a name="add-header-conditions"></a>新增標頭條件
1. 在 [動作窗格] 上，選擇 **選項**。
2. 選擇 **變更檢視**。
3. 選擇 **標題檢視**。
4. 展開 **條款** 區段。
5. 在 **付款方式** 欄位中，從下拉功能表中選擇需要的紀錄。 預設情況下，此處會顯示廠商帳戶的付款條款。  
6. 在 **交貨模式** 欄位中，從下拉功能表中選擇需要的紀錄。
7. 在 **交貨條款** 欄位中，選擇下拉式按鈕開啟查詢。

## <a name="confirm-and-activate-the-agreement"></a>確認並啟用合約
1. 在動作窗格上，選擇 **購買合約**。
2. 選擇 **確認**。 將 **將合約標記為有效** 選項設定為 **是**。  
3. 選擇 **確定**。
4. 在動作窗格上，選擇 **購買合約**。
5. 選擇 **購買合約確認**。 **預覽/列印** 選項，允許您為購買合約生成文件，然後您可以列印或傳送給供應商。 如果您稍後更新合約並重新確認，這兩個版本都會顯示於此。  
6. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]