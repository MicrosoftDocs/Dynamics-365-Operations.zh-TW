---
title: 履行銷售合約
description: 此程序將向您展示如何透過關聯銷售訂單來履行銷售合約。
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines, SalesAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fe26d528e42da61d47fd2448e071bf9025c08f5d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448614"
---
# <a name="fulfill-sales-agreements"></a>履行銷售合約

[!include [banner](../../includes/banner.md)]

此程序將向您展示如何透過關聯銷售訂單來履行銷售合約。 您可使用示範資料公司 USMF 或自己的資料來執行此程序。 在開始本指南之前，請確認您持有「產品價值承諾」類型的有效銷售合約。 或者，您可以執行稱作「建立銷售合約」的工作指南。  




## <a name="release-a-sales-order-from-the-agreement"></a>從合約中釋出銷售訂單
1. 前往銷售和行銷 > 銷售合約 > 銷售合約。
2. 在清單中，打開您要釋出訂單的合約。
3. 在動作窗格上，按一下銷售合約。
4. 按一下釋出訂單明細。
    * 正如建立釋出訂單頁面頂部的文字指出，銷售訂單明細所需詳細資訊的差異，將視合約是依據數量還是值而定。  
    * 本指南中的合約屬於「產品價值承諾」類型。 所以此頁面的明細部分為空白。 如果承諾是根據數量決定，則明細詳細資訊將從合約進行複製。  
5. 按一下建立。
    * 該訊息會通知您已建立銷售訂單。 由於訂單不包含任何明細，您必須新增訂單明細詳細資訊才能完成釋出流程。   
6. 關閉頁面。
7. 關閉頁面。
8. 前往銷售和行銷 > 銷售訂單 > 所有銷售訂單。
9. 在清單中，找出並開啟在上一個工作中作為訂單釋出結果建立的訂單。
10. 按一下新增明細。
11. 在品項編號欄位中，按一下下拉式按鈕開啟查詢。
12. 在品項編號欄位中，鍵入或選擇關聯銷售合約中指定的項目。
13. 在數量欄位中，輸入一個數字。
    * 確認您輸入的數量使淨額低於相關銷售合約的價值。  
    * 請注意，由於銷售訂單已連結到合約，因此協商的折扣百分比將套用至訂單明細。  
14. 按一下更新明細。
15. 按一下附件。
    * 已附加合約頁面顯示明細已釋出的合約識別碼和條款。  
16. 關閉頁面。
17. 在動作窗格上按一下一般。
18. 按一下已附加銷售合約。
19. 展開行詳細資訊區段。
20. 按一下履行索引標籤。
    * 履行索引標籤會顯示與此承諾關聯的所有銷售訂單明細摘要，以及它們的履行狀態，與尚未發佈的金額或數量。   
21. 關閉頁面。
22. 關閉頁面。
23. 關閉頁面。

## <a name="apply-sales-agreement-in-the-order-process"></a>在訂單流程中套用銷售合約
1. 前往銷售和行銷 > 銷售訂單 > 所有銷售訂單。
2. 按一下新增。
3. 在客戶帳戶欄位中，按一下下拉式按鈕開啟查詢。
4. 在清單中，尋找並選擇銷售合約中指定的客戶。
5. 在列表中，按一下所選行中的連結。
6. 展開一般區段。
7. 在銷售合約識別碼欄位中，按一下下拉式按鈕以開啟查詢。
8. 在列表中，按一下所選行中的連結。
9. 按一下是。
10. 按一下確定。
11. 在清單中，標記所選資料列。
12. 在品項編號欄位中，按一下下拉式按鈕開啟查詢。
13. 在品項編號欄位中，鍵入或選擇關聯銷售合約中指定的項目。
14. 在列表中，按一下所選行中的連結。
15. 按一下儲存。
16. 在動作窗格上按一下揀貨並裝箱。
17. 按一下過帳裝箱單。
18. 展開參數區段。
19. 在張貼欄位中選擇是。
20. 按一下確定。
21. 按一下確定。
22. 在動作窗格上按一下一般。
23. 按一下已附加銷售合約。
24. 按一下履行索引標籤。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]