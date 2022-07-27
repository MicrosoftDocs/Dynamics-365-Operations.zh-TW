---
title: ER 在格式輸出中使用文件管理檔案 (第 1 章節 - 準備資料模型)
description: 本主題介紹如何設定電子報表 (ER) 格式以在 ER 輸出中使用文件管理檔案 (附件)。 (第 1 章節)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa4996100a839a8440bad8724680c5799e032064d4a5ec0fbbc0f2af2641b8fb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460263"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a>ER 在格式輸出中使用文件管理檔案 (第 1 章節 - 準備資料模型)

[!include [banner](../../includes/banner.md)]

以下步驟說明了指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以使用 ER 輸出中的文件管理檔案 (附件)。 這些步驟可以在任何公司進行。

若要完成這些步驟，您必須先完成「建立設定提供者並將其標記為有效」程序中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>存取 Microsoft 提供的設定清單
1. 進入組織管理 > 工作區 > 電子報表。

    確保「Litware, Inc.」 提供者可供使用並標記為有效。  

2. 選取「Litware, Inc.」 提供者。
3. 點選存放庫。

    如果「營運資源」類型的存放庫已存在，則跳過現行子工作的剩餘步驟。  

4. 點選新增以開啟下拉式對話方塊。
5. 在設定存放庫類型欄位中，輸入「Operations resources」。
6. 點選建立存放庫。
7. 點選確定。

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a>取得 Microsoft 提供的客戶發票模型設定
1. 點選顯示篩選條件。
2. 應用以下過濾器：使用「開始於」過濾器運算子在「名稱」欄位中輸入過濾器值「營運資源」；使用「開頭為」過濾器運算子在「描述」欄位中輸入過濾器值「」
3. 點選顯示篩選條件。
4. 點選開啟。
5. 在樹狀結構中，選取「Customer invoice model」。

    選取模型設定「客戶發票模型」進行匯入。  

6. 點選匯入。

    對於所選設定的 1 版，點選匯入。  

7. 點選是。
8. 關閉頁面。
9. 關閉頁面。
10. 點選報表設定。
11. 在樹狀結構中，選取「Customer invoice model」。

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a>建立衍生模型以支援對文件管理檔案的存取。
您將建立我們自己的客戶發票模型設定，該模型源自 Microsoft 提供的設定。 您將使用此設定來實現對文件管理檔案的存取，並使它們可用於您將基於此模型建立的電子文件。  
1. 點選建立設定即可打開下拉式對話方塊。
2. 在新建欄位中，輸入「Derive from Name: Customer invoice model, Microsoft」。
3. 在名稱欄位，輸入「Customer invoice model (custom)」。
4. 點選建立設定。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]