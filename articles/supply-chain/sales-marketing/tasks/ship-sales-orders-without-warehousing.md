---
title: 無需倉儲即可裝運銷售訂單
description: 本主題說明如何在將產品裝運給客戶時更新銷售訂單。
author: Henrikan
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10e21bcdef22caf4f4d97ba7dd36ebf1a6e6e055
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449154"
---
# <a name="ship-sales-orders-without-warehousing"></a>無需倉儲即可裝運銷售訂單

[!include [banner](../../includes/banner.md)]

本主題說明如何在將產品裝運給客戶時更新銷售訂單。 本指南適用於沒有為倉庫管理設定的履行流程 (無論是基礎倉儲還是進階倉儲)，因此不需要在裝運前登記產品揀貨。 您可使用自己的資料或 USMF 示範資料公司來執行此程序。 在這兩種情況下，在開始此工作之前，請為數量大於 1 的庫存產品建立銷售訂單。 為避免過帳錯誤，您需要檢查您在訂單中選擇的站點和倉庫中產品的現有數量是否涵蓋了訂單數量。

## <a name="post-packing-slip-for-an-order"></a>過帳訂單的裝箱單
1. 在瀏覽窗格中，移至 **模組 > 銷售和行銷 > 銷售訂單 > 所有銷售訂單**。
2. 在清單中，尋找並選擇您為此工作建立的訂單。
3. 在 [動作窗格] 上選取 **揀料並裝箱**。
4. 選取 **過帳裝箱單**。
5. 展開或摺疊 **參數** 區段。
6. 在 **數量** 欄位中，選取 **全部**。
    - 其他選項包括 **立即交貨** 和 **揀料**。 如果訂單行要部分裝運並且訂單行上的 **立即發貨** 欄位包含數量，您可以選擇 **立即發貨**。 如果您組織的履行流程中，領料作為單獨的流程並根據揀料單管理和登記，您可以選擇 **揀料**。  
    - 確認 **過帳** 選項設為 **是**。  
7. 將 **列印裝箱單** 選項設為 **是**。 **概觀** 索引標籤包含要在此過帳中產生的裝箱單清單。 如果您要裝運單個訂單，通常只有一個裝箱單。 但是，如果該訂單的行要從不同的站點裝運，過帳將自動拆分為適當數量的文件。 這是強制性的，無法變更。 同樣，如果訂單的行將裝運到不同的交貨地址，並且運輸原則設定為要求拆分，則過帳也將拆分為多個文件。  
8. 在 **行** 索引標籤，選擇要裝運的訂單行所在的行。
9. 在 **更新** 欄位中，輸入一個低於原始數量的數字。
10. 選取 **確定**。
11. 選取 **是**。
12. 關閉頁面。
13. 在 [動作窗格] 上，選擇 **選項**。
14. 選擇 **變更檢視**。
15. 選擇 **標題檢視**。
    - 如果訂單上的所有行都已完全發貨，則訂單狀態會從 [未結] 變更為 [已交貨]。  
    - 在此範例中，訂單行已部分裝運。 這就是訂單處於 [未結] 狀態的原因。     
    - 由於至少有一個訂單行已裝運，**文件狀態** 欄位設定為 [裝箱單]。  
16. 在 [動作窗格] 上，選取 **一般**。
17. 選擇 **行數量**。
18. 關閉頁面。
19. 在 [動作窗格] 上選取 **揀料並裝箱**。
20. 選取 **裝箱單**。 **裝箱單日記帳** 頁面包含為您的訂單產生的所有裝箱單文件。 如果您願意，可以查看每個文件的詳細資料並列印。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]