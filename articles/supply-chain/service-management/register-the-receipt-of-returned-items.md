---
title: 登記退回品項的收貨
description: 您可以使用「到貨摘要」表單或「登記」表單登記退回品項的收貨。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a1dc18e50dd10568c719c4f87d805be526d6746
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448905"
---
# <a name="register-the-receipt-of-returned-items"></a>登記退回品項的收貨 

[!include [banner](../includes/banner.md)]


可透過兩種方法來登記退回品項的收貨。 第一種方法是倉庫收貨流程，它使用 **到貨摘要** 表單。 第二種使用 **登記** 表單。

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a>在到貨摘要表單中登記退回品項的收貨

您可以使用 **到貨摘要** 表單，透過退貨授權 (RMA) 編號識別退貨。 如果在 **設定** 索引標籤中定義日記帳名稱，且對應於 **到貨摘要** 表單中所選取明細的日記帳明細存在，按一下 **開始到貨** 時，建立新的日記帳標題。

1.  按一下 **庫存管理**\>**定期**\>**到貨摘要**。

2.  在 **設定名稱** 欄位，選擇 **退貨單**，然後按一下 **更新**。
    

    > [!TIP]
    > <P>可以使用<STRONG>範圍</STRONG>欄位以縮小搜尋範圍。 在 <STRONG>RMA 號碼</STRONG>欄位中輸入或選取 RMA 號碼以得到精確的搜尋結果。 若要定義和儲存一組用於限制顯示哪些入庫到貨的篩選器，則按一下<STRONG>設定</STRONG>索引標籤。可用篩選器包括類型、倉庫和碼頭。</P>

    

    > [!WARNING]
    > <P>退貨單不能與<STRONG>到貨摘要</STRONG>表單中的其他到貨類型混合。 因此，該參考將始終是銷售訂單，但是不會在日記帳標題中指定銷售訂單識別碼。</P>



3.  在 **收貨** 網格中查找與要退回品項相符的明細，然後在 **選取到貨記錄** 行中選中該核取方塊。

4.  若要從退貨收貨中排除某些明細，例如不包括在退回貨件原始訂單中的品項，則在表單下半部分的 **明細** 表中清除關聯的 **選取到貨記錄** 核取方塊。

5.  按一下 **開始到貨** 按鈕以建立到貨日記帳。
    

    > [!NOTE]
    > <P>可以選擇多張退貨單並將它們全部包含在單個到貨流程中。 每個退貨單明細將複製到相應的品項到貨日記帳明細中。</P>

    

    > [!NOTE]
    > <P>透過使用<STRONG>品項到貨</STRONG>表單，也可以手動建立到貨日記帳。 



6.  按一下 **庫存管理**\>**日記帳**\>**品項到貨**\>**品項到貨**。

7.  選擇剛建立的到貨日記帳，然後按一下 **明細** 以開啟 **日記帳明細，位置** 表單。

8.  視需要，在 **一般** 索引標籤，調整 **數量** 欄位中的數字，然後在 **處置代碼** 欄位中指派處置代碼。
    
    或者，您可以選擇 **隔離管理** 核取方塊以透過檢疫訂單內容中的檢查流程發送退回品項。
    

    > [!NOTE]
    > <P>如果您透過隔離發送退回品項，則無法指定處置代碼。</P>



9.  按一下 **驗證** 按鈕。

10. 如果驗證過程中沒有錯誤，則按一下 **過帳**。

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a>在「登記」表單中登記退回品項的收貨

作為使用 **到貨概覽** 表單的備選方案，可以使用 **登記** 表單登記退回品項的到貨。

1.  點擊 **銷售和營銷**\>**通用**\>**退貨單**\>**所有退貨單**。 建立新退貨單或從該清單中開啟退貨單。 在 **明細** FastTab，選擇退貨單明細。 按一下 **更新明細**，然後按一下 **登記**。

2.  在 **處置代碼** 欄位中指派處置代碼，然後按一下 **確定**。
    

    > [!NOTE]
    > <P>無法使用<STRONG>登記</STRONG>表單作為檢疫單將品項送檢。</P>



3.  在 **交易** 網格中，選擇要登記的交易。

4.  在 **立即登記** 網格中，按一下 **新增**。 在所有退回品項出現在 **立即登記** 網格中之前，重複前兩個步驟。

5.  按一下 **全部過帳**。

## <a name="see-also"></a>另請參閱

[到貨概覽 (表單)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]