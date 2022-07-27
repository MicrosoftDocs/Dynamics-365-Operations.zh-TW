---
title: 輸入銷售合約
description: 本主題說明如何建立銷售合約，讓客戶在一段時間內購買協議數量的產品以換取特殊折扣。
author: Henrikan
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm, SalesAgreementCustomerReferencesPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee2c1494842c5fd2aa598546ba655c33d6fd3f16
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448098"
---
# <a name="enter-sales-agreements"></a>輸入銷售合約

[!include [banner](../../includes/banner.md)]

本主題說明如何建立銷售合約，讓客戶在一段時間內購買協議數量的產品以換取特殊折扣。 您可使用示範資料公司 USMF 或自己的資料來執行此程序。


## <a name="set-up-sales-agreement-header"></a>設定銷售合約標題
1. 在瀏覽窗格中，移至 **模組 > 銷售和行銷 > 銷售合約 > 銷售合約**。
2. 選取 **新增**。
3. 在 **客戶帳戶** 欄位中，從下拉式功能表選取所需的記錄。
4. 在 **銷售合約分類** 欄位中，從下拉式功能表選取所需的記錄。
5. 展開 **一般** 區段。
6. 在 **預設承諾用量** 欄位中，選取 **產品價值承諾**。 承諾類型是您必須指派給合約強制性標準，可定義如何履行合約。 四種預先定義的類型可讓您設定客戶的承諾目標 (以數量或價值表示)。 數量承諾類型僅適用特定產品，但價值型類型適用於銷售特定和非特定產品。  
7. 在 **到期日期** 欄位中，將日期設成您希望未來合約到期的日期。
8. 選取 **確定**。

## <a name="set-up-product-value-commitment-lines"></a>設定產品價值承諾明細
1. 選擇 **新增明細**。
2. 在 **項目編號** 欄位中，從下拉功能表中選擇需要的紀錄。 您為合約選取的承諾類型會影響合約明細可輸入的資訊類型。 例如，以價值型合約而言，您必須指定客戶承諾向您購買商品的總淨額 (以協議的貨幣表示)。 在此範例中，明細上沒有 **數量** 和 **單位** 欄位，因為您正建立的合約是客戶必須購買特定價值的產品。   
3. 在 **淨額** 欄位中，輸入客戶承諾購買的金額。
4. 在 **折扣百分比** 欄位中，輸入將套用至此合約連結的客戶銷售訂單明細的百分比值。
5. 展開 **行詳細資訊** 區段。
6. 在 **設定上限** 欄位中，選取 **是**。
    - 選取 **設定上限**，代表採用此承諾之特價、折扣和/或付款條件的所有銷售訂單明細總額，不得超過承諾中設定的值。  
    - 最小和最大發放金額係針對採用此合約的每筆銷售訂單，規定必須銷售的價值的範圍。   
7. 展開 **銷售合約標題** 區段。 除非合約狀態設為 **有效**，否則銷售訂單不得與之建立關聯，不算在該合約的履行範圍。 此階段可手動變更其狀態。 然而，與客戶確認合約時，狀態通常會改變。  
8. 在動作窗格上，選取 **銷售合約**。
9. 選取 **確認**。 確認 **將合約標記為有效** 選項設定為 **是**。  
10. 選取 **列印報表** 欄位中的 **是**。
11. 選取 **確定**。
12. 關閉頁面。 該合約現已生效。 您現可將客戶訂單連結至此合約，開始抵算承諾目標。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]