---
title: 信用和收帳管理 Power BI 內容
description: 本主題介紹信用和收帳管理 Power BI 內容中包含的內容。 它解釋了如何存取 Power BI 報表，並提供有關用於構建內容的資料模型和實體的資訊。
author: ShivamPandey-msft
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 65423f49ba106a152f58c92533c4f1a16d47a318982cfe69bb23f9091fa09846
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450666"
---
# <a name="credit-and-collections-management-power-bi-content"></a>信用和收帳管理 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **信用和收帳管理** Microsoft Power BI 內容中包含的內容。 它解釋了如何存取 Power BI 報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="overview"></a>概觀

**信用和收款管理** Power BI 內容是為信用和收款經理以及收款職員建立的。 它提供了關鍵的信用和收款指標，例如未結銷售天數、逾期餘額、信用風險和超過信用額度的客戶。 它使用交易資料並提供所有公司信用和收款的彙總檢視表。 它還提供了每個公司、客戶群組和客戶的明細。

Power BI 內容包括 10 個報表頁面：

- 兩個概觀頁面 (一個頁面用於信用概觀，一個頁面用於收款概觀)
- 八個詳細資料頁面，提供跨不同維度劃分和細分的信用和收款指標的詳細資訊

所有金額均以系統貨幣顯示。 您可以在 **系統參數** 頁面設定系統貨幣。

預設情況下，會顯示目前公司的信用和收款資料。 要查看所有公司的資料，請將 **CustCollectionsBICcrossCompany** 責任指派給角色。

## <a name="setup-needed-to-view-power-bi-content"></a>查看 Power BI 內容所需的設定

需要完成以下資料的設定才能在 **客戶信用和收款** 中顯示 Power BI 視覺效果。

1. 前往 **系統管理 > 設定 > 系統參數**，設定 **系統貨幣** 和 **系統匯率** 欄位。
2. 前往 **總帳 > 日曆 > 會計日曆** 以驗證指派給活動時間間隔的會計日曆日期。
3. 前往 **總帳 > 設定 > 分類帳**，設定 **會計貨幣** 和 **匯率類型**。
4. 定義交易貨幣與會計貨幣以及會計貨幣與系統貨幣的匯率。 若要這樣做，請前往 **總帳 > 貨幣 > 貨幣匯率**。
5. 前往 **系統管理 > 設定 > 實體店** 重新整理 **CustCollectionsBIMeasurementsV2** 彙總測量值。

>[!NOTE] 
> 必須在 **應收帳款參數 > 收款 > 收款預設** 中定義帳齡期間定義，才能在 Power BI 內容中啟用帳齡資料。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容

**信用和收款管理** Power BI 內容顯示在 **客戶信用和收款** 工作區。

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的報表

**CustCollectionsBICrossCompany** Power BI 內容包括由一組指標組成的報告。 這些指標可視覺化為圖表、圖格和資料表。 下表概述了 **CustCollectionsBICrossCompany** Power BI 內容中的視覺化。

| 報表頁面                 | 視覺化 |
|-----------------------------|---------------|
| 收款概觀        | <ul><li>客戶逾期</li><li>客戶超出信用額度</li><li>DSO 30 天</li><li>未結案例</li><li>關閉案例的前平均天數</li><li>未結活動</li><li>關閉活動前的平均天數</li><li>未結利息單</li><li>開啟催款單</li><li>客戶暫停</li><li>銷售暫停</li><li>帳齡餘額</li><li>收款狀態金額</li><li>收款代碼金額</li><li>依原因沖銷</li><li>應付餘額 (依地區劃分)</li><li>預期付款</li></ul> |
| 信用概觀             | <ul><li>客戶逾期</li><li>信用額度與應付餘額</li><li>客戶超出信用額度格線</li><li>每個公司超出信用額度的客戶</li><li>已使用信用額度與總信用額度</li><li>信用額度與已使用信用額度 (依地區畫分)</li><li>每種信用等級的客戶</li></ul> |
| 信用額度                | <ul><li>信用額度</li><li>信用額度詳細資料</li><li>每個客戶的信用額度</li><li>每個客戶群組的信用額度</li><li>每個公司的每個信用等級的信用額度</li><li>信用額度與已使用信用額度 (依地區畫分)</li></ul> |
| 客戶超出信用額度 | <ul><li>客戶超出信用額度</li><li>客戶超出信用額度詳細資料</li><li>每個公司超出信用額度的客戶</li><li>超出信用額度的客戶 (依客戶群組劃分)</li><li>客戶超出信用額度 (依地區畫分)</li></ul> |
| 客戶逾期          | <ul><li>客戶逾期</li><li>客戶逾期詳細資料</li><li>逾期客戶 (依公司劃分)</li><li>逾期客戶 (依客戶群組劃分)</li><li>客戶逾期按地區</li></ul> |
| 帳齡餘額               | <ul><li>帳齡餘額</li><li>帳齡餘額明細</li><li>帳齡餘額 (依公司劃分)</li><li>帳齡餘額 (依客戶群組劃分)</li></ul> |
| 預期付款           | <ul><li>預期付款</li><li>預期付款詳細資料</li><li>預期付款 (依公司劃分)</li><li>預期付款 (依客戶群組劃分)</li><li>預期付款 (依區域劃分)</li></ul> |
| 沖銷                  | <ul><li>依區域沖銷</li><li>沖銷詳細資料</li><li>依主科目沖銷</li><li>依公司沖銷</li><li>依客戶群組沖銷</li><li>依區域沖銷</li></ul> |
| 收款狀態          | <ul><li>爭議</li><li>承諾付款已中斷</li><li>承諾付款</li><li>收款狀態詳細資料</li><li>收款狀態金額</li><li>未結案例</li><li>未結活動</li></ul> |
| 催款單         | <ul><li>收款代碼金額</li><li>收款代碼金額詳細資料</li><li>催款單金額 (依公司劃分)</li><li>催款單金額 (依客戶群組劃分)</li><li>催款單金額 (依區域劃分)</li></ul> |

這些報表上的圖表和圖格都可以篩選並釘選到儀表板上。 如需如何在 Power BI 中篩選和釘選的相關資訊，請參閱[建立和設定儀表板](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/)。 您還可以使用匯出基礎資料功能來匯出視覺效果中匯總的基礎資料。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]