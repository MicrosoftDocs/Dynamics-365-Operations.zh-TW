---
title: 過帳退回產品的到貨日記帳
description: 過帳退回產品的到貨日記帳。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a16514578ff6a1ffc3514d0110f46bb71c2cc394
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448902"
---
# <a name="post-arrival-journal-for-returned-products"></a>過帳退回產品的到貨日記帳 

[!include [banner](../includes/banner.md)]


要處理退貨，首先要驗證退貨數量，更新品項到貨日記帳中的數量欄位。 然後選擇處置代碼或指示必須檢查退回的品項。 完成這些步驟後，您就可以過帳退貨單的品項到貨日記帳。

1.  按一下 **庫存管理**\>**定期**\>**到貨摘要**。

2.  在 **設定名稱** 篩選器中，選擇 **退貨單**。

3.  如果收據列表很長，請使用 **範圍** 區域中的欄位以縮小列表。

4.  找到您要過帳的退貨單行，選擇其 **選取到貨記錄** 框，然後按一下 **開始到貨**。

5.  按一下 **日記帳**\>**從收據顯示到貨** 以開啟 **位置日記帳** 表單。
    

    > [!TIP]
    > <P>要檢視詳細資訊，請選擇日記帳，然後按一下<STRONG>明細 </STRONG>。</P>


6.  進行任何必要的更新，然後按一下 **過帳**。

該日記帳過帳後，退回的品項便登記在庫存中，而 **退貨單** 表單會顯示該品項已到達倉庫。

## <a name="see-also"></a>另請參閱

[位置日記帳（表單）](https://technet.microsoft.com/library/aa584822\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]