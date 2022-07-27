---
title: 使用品項到貨日記帳為進階倉儲啟用的品項登記品項
description: 本主題提供的案例顯示在使用進階倉儲管理流程時如何使用品項到貨日記帳登記品項。
author: Mirzaab
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e753897d1e21ffebbcbfac48abab4b0549c3553f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447780"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>使用品項到貨日記帳為進階倉儲啟用的品項登記品項

[!include [banner](../../includes/banner.md)]

本主題提供的案例顯示在使用進階倉儲管理流程時如何使用品項到貨日記帳登記品項。 這通常由收貨員執行完成。

## <a name="enable-sample-data"></a>啟用範例資料

若要使用在本主題中指定的範例記錄和值完成此案例，您必須使用已安裝標準示範資料的系統，並且必須在開始之前選擇 *USMF* 法律實體。

相反，如果您有以下可用資料，則可以透過替換自己資料中的值來完成此案例：

- 您必須有一個已確認的訂購單，其中包含未結訂購單明細。
- 明細中的品項必須有庫存。 它不得使用產品變型，也不得具有追蹤維度。
- 品項必須與已啟用倉庫管理流程的儲存維度群組關聯。
- 必須為倉庫管理流程啟用所使用的倉庫，並且用於接收的位置必須受牌照控制。

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a>建立使用倉庫管理的品項到貨日記帳標題

以下案例顯示如何建立使用倉庫管理的品項到貨日記帳標題：

1. 確保您的系統包含已確認採購單，該訂單符合上一節中概述的要求。 此案例使用公司 *USMF*、供應商帳戶 *1001*、倉庫 *51* 的採購單，其中包含品項編號 *M9200* 的 *10 PL* (10 個棧板) 之訂單明細。
1. 記下將使用的訂購單編號。
1. 前往 **庫存管理 \> 日記帳分錄 \> 品項到貨 \> 品項到貨**。
1. 在動作窗格上，選擇 **新增**。
1. **建立倉庫管理日記帳** 對話方塊會開啟。 在 **名稱** 欄位中，選擇日記帳名稱。
    - 如果您使用的是 *USMF* 示範資料，則選擇 *WHS*。
    - 如果您使用自己的資料，則選擇的日記帳必須將 **檢查揀料地點** 設定為 *否* 並將 **隔離管理** 設定為 *否*。
1. 將 **參考** 設定為 *訂購單*。
1. 將 **帳戶號碼** 設定為 *1001*。
1. 將 **編號** 設定為您為此練習標識的採購單編號。

    ![品項到貨日記帳。](../media/item-arrival-journal-header.png "品項到貨日記帳")

1. 選擇 **確定** 以建立日記帳標題。
1. 在 **日記帳明細** 部分中，選擇 **新增明細** 並輸入以下資料：
    - **品項編號** – 設定為 *M9200*。 根據 10 個棧板 (每個棧板 1000 個) 的庫存交易資料，設定 **站點**、**倉庫** 和 **數量**。
    - **地點** – 設定為 *001*。 此特定位置不追蹤牌照。

    ![品項到貨日記帳明細。](../media/item-arrival-journal-line.png "品項到貨日記帳明細")

    > [!NOTE]
    > **日期** 欄位確定此現有數量的品項將登記入庫存的日期。  
    >
    > 如果可從提供的資訊進行唯一識別，系統將會自動填入 **批次識別碼**。 否則將必須手動輸入。 這是必填欄位，用於將此登記連結到特定來源文件明細。  

1. 在動作窗格上，選取 **驗證**。 這將檢查日記帳是否已準備好過帳。 如果驗證失敗，需要修復錯誤才能過帳日記帳。  
1. **檢查日記帳** 對話方塊會開啟。 選取 **確定**。
1. 查看訊息列。 應該有一條訊息表示操作已完成。  
1. 在動作窗格上，選取 **過帳**。
1. **過帳日記帳** 對話方塊會開啟。 選取 **確定**。
1. 查看訊息列。 應該有一條訊息表示操作已完成。
1. 在動作窗格上選擇 **功能 > 產品收貨** 以更新訂單明細並過帳產品收貨。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
