---
title: 設定租賃參數 (預覽版)
description: 本主題介紹資產租賃的配置設定，例如安全性資訊和會計設定。
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a644b3c9d9ed4fc86a816af1ab338b96b1aa7ad
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "8451356"
---
# <a name="configure-lease-parameters"></a>設定租賃參數

[!include [banner](../includes/banner.md)]

有些配置設定會影響資產租賃的行為。 這些設定包括日記帳名稱、一般參數和過帳設定檔設定。

1. 前往 **資產租賃\>設定\>資產租賃參數**。
2. 在 **租賃** 索引標籤，選擇 **一般** FastTab。

    **允許手動分類覆寫** 參數以確定在確認付款計劃之前是否可以覆寫租賃分類。

    **跨實體批次** 參數確定您是否可以從目前法律實體過帳到其他法律實體。 如果啟用此參數，則可以為您有權存取的法律實體建立日記帳分錄。

3. 將 **允許刪除已確認的租賃** 選項設為 **是**，以允許刪除已確認付款計劃的租賃。 如果已過帳或未過帳的交易與其相關聯，則無論此選項的設定如何，都無法刪除租賃。 租賃記錄在刪除後無法恢復。 如果您手動或透過資料實體上傳已刪除租賃的任何記錄，則上傳的資訊將視為新資訊，而不是對現有租賃的更新。

    如果將此選項設定為 **是**，帳簿的轉換類型為 **累積採納選項 A 或 B**，系統將 **增量借款利率** 欄位的值設定為 **帳簿設定** 頁面上 **轉換期增量借款利率** 欄位的值。 如果此選項設定為 **否**，則將總租賃利率設為 **帳簿詳細資料** 頁面上的 **增量借貸利率** 欄位的值，而不論帳簿的轉換類型為何。

4. 將 **允許對已結帳簿進行折舊沖銷** 選項設定為 **是**，以允許沖銷折舊費用交易。 即使帳簿籍版本已結，也可以沖銷費用交易。

    > [!NOTE]
    > 建議您將此選項保持設定為 **否**。 此選項的設定用作驗證和控制，以防止已結帳簿版本意外折舊。 將選項設定為 **否**，有助於保持帳面淨值和未來折舊計算的準確性。

5. 將 **允許付款金額明細** 選項設定為 **是**，以允許在 **租賃** 頁面的 **付款計劃行** FastTab 上分解付款金額。 在 **付款金額類型** 頁面的 **設定** 下定義了付款明細類型。 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
