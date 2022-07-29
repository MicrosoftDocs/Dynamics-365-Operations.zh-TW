---
title: 新增或複製租賃 (預覽版)
description: 本主題介紹如何透過在資產租賃中輸入資訊或從現有租賃複製資訊來建立新租賃。
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b09a87c7d4f5ba076647218c3586d17a13e6c558
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "8451350"
---
# <a name="add-or-copy-leases-preview"></a>新增或複製租賃 (預覽版)

[!include [banner](../includes/banner.md)]

本主題說明如何在資產租賃中從頭開始建立租賃，以及如何透過複製現有租賃來建立租賃。 從頭開始建立租賃的流程包括輸入新租賃的資訊，然後建立租賃排程。 在設定了至少一個租賃之後，您可能會發現從現有租賃中複製資訊，然後根據需要編輯該資訊以建立新租賃會更輕鬆。

## <a name="create-a-lease"></a>建立租賃

請按照以下步驟在資產租賃中建立租賃。

1. 在 **租賃** 頁面上的動作窗格選擇 **新增**。
2. 輸入租賃資訊。 具有紅色邊框的為必填欄位。

租賃付款的開始日期不能早於租賃開始日期。 如果您輸入的租賃付款開始日期早於租賃的開始日期，您將收到錯誤訊息。

根據預設，如果 **資產租賃參數** 頁上的 **允許付款分解** 選項設定為 **是**，則 **租賃詳細資料** 頁的 **一般** 快速索引標籤上的 **分解付款金額** 選項設定為 **否**。 

如果 **分解付款金額** 選項設定為 **是**，則 **付款排程行** 快速索引標籤上的 **付款金額** 欄位將鎖定。 它將設定為 **付款金額明細** 目錄中稍後輸入的付款金額總計。

選擇 **付款金額明細** 打開一個頁面，您可以在其中新增分項付款類型。 **將總計新增到付款金額** 按鈕會將總計移動到 **付款金額** 欄位。

> [!NOTE]
> 如果您新增分項付款金額，然後選擇 **Esc** 鍵，則輸入的金額不會新增到 **付款排程行** 快速索引標籤的 **付款金額** 欄位。 相反，它們將儲存在 **付款金額明細** 對話方塊中。 如果您希望對話方塊顯示總金額，請選擇 **金額** 行，選取並按住 (或按一下右鍵)，然後選擇 **計算此行總計**。 

**複製行** 按鈕將複製分項付款明細。

## <a name="create-a-lease-schedule"></a>建立租賃排程

輸入租賃資訊後，請按照以下步驟建立租賃排程。

> [!NOTE]
> 財務維度可能會根據任何自訂財務維度而改變。

1. 選擇 **建立排程** 產生租賃帳簿。 租賃帳簿包括付款、攤銷、折舊和費用排程。
2. 要存取租賃帳簿並查看新建立的排程，請選擇 **帳簿** 索引標籤。

    **帳簿詳細資料** 頁面會顯示如何透過指派的帳簿來計算租賃。 從這裡，您可以查看租賃排程。

    付款排程包含在 **新增租賃** 頁面上的 **付款排程行** 索引標籤中進行的輸入。 您仍可以變更每個付款金額和變動付款。 租賃負債根據修改後的付款排程計算。

    > [!NOTE]
    > 租賃付款的開始日期必須等同或晚於租賃的開始日期。 如果付款的開始日期早於租賃開始日期，您將收到錯誤訊息。 

4. 檢查完付款排程後，選擇 **確認排程**。 確認排程後，將無法再編輯該租賃。

    > [!NOTE]
    > 系統會根據 **新增租賃** 頁面中的付款排程行自動計算租賃期限。
    >
    > 若要以月為單位計算租賃期限，系統會尋找特定付款排程行的開始日期和結束日期之差。 然後移動到下一個付款排程行並再次尋找差額。 最後，系統將所有數額相加，以確定以月為單位的租賃期限。

5. 若要查看計算的期間利息費用，請打開 **負債攤銷排程** 頁面。 若要查看計算的直線折舊，請打開 **資產折舊排程** 頁面。
6. 查看完計算的金額後，您可以在 **初始確認** 頁面建立初始確認日記帳。 您會收到一則訊息，指出該日記帳已建立。

    > [!NOTE]
    > 除非您手動過帳日記帳分錄，否則日記帳分錄不會過帳到總帳。

7. 若要在過帳前查看提議的初始確認分錄，請選擇 **資產租賃日記帳**。

    > [!NOTE]
    > 不能手動建立資產租賃日記帳。 它是在建立租賃排程時自動建立的。

8. 當您查看完初始確認日記帳分錄並準備過帳時，請選擇 **過帳** 在總帳中確認使用權 (ROU) 資產和租賃負債。

## <a name="copy-a-lease"></a>複製租賃

資產租賃可讓您複製租賃的詳細資料以建立具有相同資訊的新租賃。 然後，您可以在為複製的租賃建立排程之前變更租賃欄位。

1. 在 **租賃摘要** 頁面，選擇要複製的租賃，然後在動作窗格中，選擇 **複製租賃**。

    > [!NOTE]
    > 如果關閉了租賃識別碼編號規則的 **手動** 參數，將自動產生序列中的下一個編號作為複製租賃的租賃識別碼。 如果打開了 **手動** 參數，您會收到一則訊息，提示您在繼續複製租賃之前輸入租賃識別碼。

2. 選取 **複製**。 將把所選租賃的租賃詳細資料復製到新租賃。 然後，您可以在儲存新租賃並建立租賃排程之前對其進行編輯。

## <a name="asset-leasing-journal"></a>資產租賃日記帳

在資產租賃中建立的所有日記帳分錄都包含在資產租賃日記帳中。 在 **資產租賃日記帳** 頁面 (**資產租賃 \> 日記帳分錄 \> 資產租賃日記帳**)，您可以按過帳狀態進行篩選，查看特定的日記帳分錄和憑證，以及過帳未過帳的日記帳分錄。

> [!NOTE]
> 不能手動建立資產租賃日記帳。 它是在建立租賃排程時自動建立的。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]