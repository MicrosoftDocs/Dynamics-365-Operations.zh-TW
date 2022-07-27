---
title: 根據訂購單創建資產
description: 本主題說明，如何建立資產項目清單，該清單可用於資產管理中，作為維護任務創建資產時的基礎。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectItem, EntAssetPendingAssets
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5068712a7ea1e0d940d4a05a411fb3e1b6f6d9bb9be924d5375b16676561ea1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447048"
---
# <a name="create-assets-based-on-purchase-orders"></a>根據訂購單創建資產

[!include [banner](../../includes/banner.md)]

 

本主題說明，如何建立資產項目清單，該清單可用於資產管理中，作為維護任務創建資產時的基礎。 根據資產項目，您可以查看根據項目創建的訂購單行清單。 此功能的目的，是根據訂購單在資產管理中輕鬆創建資產。

首先，您根據訂購單中的 **資產項目**，設定要用於創建資產的項目。 創建訂購單行後，在 **待處理資產** 中創建資產。 可以決定，資產要於訂購單的哪個階段創建。


## <a name="select-asset-items"></a>選擇資產項目

1. 按一下 **資產管理** > **設定** > **資產** > **項目**。
2. 按一下 **新增** 建立新的資產項目。
3. 在 **項目編號** 欄位中，選擇該項目。 當您關閉該欄位時，項目名稱會自動插入到 **產品名稱** 欄位。
4. 在 **一般** FastTab，選擇項目的資產類型。
5. 為項目選擇資產製造商和型號。
6. 儲存項目。


## <a name="create-assets-from-pending-assets"></a>從待處理資產中創建資產

1. 按一下 **資產管理** > **一般** > **資產** > **待處理資產**。
2. 您會按到根據所選擇的 **資產項目**，更新訂購單清單。
3. 您可以篩選訂購單的狀態，已選擇應在哪個生命週期狀態下創建資產。 例如，您可能只想要在收到訂購單的產品收據後，才創建資產。
4. 選擇訂購單行上連結的 **參考編號**，以查看有關該項目的詳細信息。
5. 如果要編輯 **庫存維度** FastTab 上顯示的尺寸，按一下 **顯示尺寸** 按鈕，然後進行選擇。
6. 如果您要根據訂購單行創建資產，請在清單頁面上，選擇該行的 **標記** 列核取方塊，然後按一下 **創建資產**。 會顯示一條訊息，向您告知資產 ID。
7. 選擇 **所有資產** 清單中的資產，並按一下 **編輯**，以新增資產的更多資訊。
8. 在 **待處理資產** 中，如果您因為不想創建資產，而想要刪除行，請選擇該行的 **標記** 列，然後按一下 **放棄待處理資產**。 會顯示一條訊息，向您告知資產 ID。 您並沒有刪除訂購單或銷售訂單，只是刪除了 **資產管理** 中創建資產的紀錄。

>[!NOTE]
>所有產品尺寸 (大小、顏色、配置等) 都會自動傳輸到資產屬性。 創建資產時，追蹤維度 (序列號) 會直接儲存在資產上。


## <a name="find-pending-assets"></a>尋找待處理資產

你可以執行一個 **待處理資產技術** 來檢查待處理資產。 例如，此功能可以於每次待處理資產準備好創建為資產時接收通知。

1. 按一下 **資產管理** > **週期** > **資產** > **待處理資產計數**。
2. 按一下 **確定** 以執行作業並更新 **待處理資產** 中的清單。
3. 您可以將此作業設定為批次作業執行，例如，每天一次。

**警告：** 如果您已根據相關項目創建資產，*之後* 訂購單的資料發生變更，則這些變更不會反映在資產上。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]