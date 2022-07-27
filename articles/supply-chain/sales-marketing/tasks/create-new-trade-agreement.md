---
title: 建立新的貿易合約
description: 此程序說明如何創建貿易合約，您可以在其中登記您與特定客戶達成一致的新產品銷售價格。
author: Henrikan
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a16a39d95605900be0fa1e339b8cd0755ba85189
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448617"
---
# <a name="create-a-new-trade-agreement"></a>建立新的貿易合約

[!include [banner](../../includes/banner.md)]

此程序說明如何創建貿易合約，您可以在其中登記您與特定客戶達成一致的新產品銷售價格。 您可使用示範資料公司 USMF 或自己的資料來執行此程序。 如果您使用自己的數據，在開始本指南之前，您需要確保存貿易合約中的日誌名稱，預設關係設定為「價格 (銷售)」。

## <a name="create-and-post-a-new-trade-agreement-journal"></a>創建並張貼新的貿易合約日誌

1. 前往 **導航窗格 > 模組 > 銷售和營銷 > 價格和折扣 > 貿易合約日誌**。
2. 按一下 **新增**。
3. 在 **名稱** 欄位中，點選下拉式按鈕開啟查詢。
4. 在清單中，尋找並選擇所需紀錄。
5. 在 **動作窗格**，按一下 **行**。
6. 請在 **帳戶代碼** 欄位，選擇「資料表」。
    
    在此範例中，您要更新特定客戶的價格，這代表您需要選擇資料表。 如果您要更新產品的標價，則應選擇「全部」，這樣新價格對所有客戶都有效。 如果您是要區分不同客戶群之間的價格，則要選擇群組。 若要選擇群組，您必須事先設定客戶價格群組。  

7. 在 **帳戶選擇** 欄位中，按一下下拉式按鈕開啟查詢。
8. 在清單中，尋找並選擇所需紀錄。
9. 請在 **項目代碼** 欄位，選擇「資料表」。
    
    當您輸入「價格 (銷售)」類型的貿易合約時，您必須只能在 **項目代碼** 欄位選擇「資料表」。 因為價格是一個絕對值，不可能所有產品或產品群組都相同。
    
10. 在 **品項關係** 欄位中，點選下拉式按鈕開啟查詢。
11. 在列表中，選擇要包含在合約中的產品。 記下您已選擇的產品。  
12. 在 **起始** 欄位，輸入最小數量。
    - 如果客戶必須滿足最低訂購數量，才能符合新價格的資格，那麼您需要在此指定該數量。  
    - 在 **上限** 欄位指定合約價格無效的最大數量。 如果您根據多個數量區段提供價格和折扣，則需要為每個數量區段指定一組最小和最大數量，分別為 **起始** 和 **上限** 欄位。
13. 在 **貨幣欄位中的金額**，輸入價格。
14. 在 **詳細資訊** 部分中的 **起始日期** 欄位，輸入本合約生效的日期。
15. 按一下 **儲存**。
16. 按一下 **驗證**。
17. 按一下 **驗證選定的行**。
18. 按一下 **確定**。
19. 按一下 **張貼**。
20. 按一下 **確定**。

## <a name="view-trade-agreements-for-a-product"></a>查看產品的貿易合約

1. 移至 **瀏覽窗格 > 模組 > 產品資訊管理 > 產品 > 已發佈產品**。
2. 在列表中，找到並選擇您剛剛更新價格的產品。
3. 在 **動作窗格** 上，按一下 **販售**。
4. 按一下 **查看貿易合約**。
    
    查看您剛剛創建的價格貿易合約的詳細資訊。

5. 關閉頁面。

## <a name="additional-resources"></a>其他資源

### <a name="whitepaper"></a>技術白皮書

如需更多資訊，請下載以下技術白皮書 (為支持 AX2012 而編寫，但仍適用於 Dynamics 365 Supply Chain Management)

- [貿易合約](https://download.microsoft.com/download/0/2/9/02972c8b-0159-4936-a3ef-1e64252b2d2f/TradeAgreementsInAX.pdf)

### <a name="community-blogs"></a>社群部落格

- [Dynamics 365 for Finance and Operations 中的銷售價格](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]