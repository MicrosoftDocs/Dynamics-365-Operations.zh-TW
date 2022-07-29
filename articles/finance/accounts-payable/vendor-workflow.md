---
title: 廠商工作流程
description: 修改廠商資訊並使用工作流程進行核准。
author: sunfzam
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 48d81c727de29a285e5e33672e8f6d2eccef6249
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451164"
---
# <a name="vendor-workflow"></a>廠商工作流程

[!include [banner](../includes/banner.md)]

使用廠商工作流程時，對特定欄位所做的更改會在新增到廠商之前寄送到工作流程進行核准。

## <a name="set-up-the-vendor-workflow"></a>設定廠商工作流程

在您可以使用工作流程功能之前，您必須啟用它。

1. 前往 **應付帳款\>設定\>應付帳款參數**。
2. 在 **廠商核准** FastTab 上的 **一般** 索引標籤，將 **啟用廠商核准** 選項設定為 **是的**。
3. 在 **資料實體行為** 欄位，選取匯入資料時應使用的行為：

    - **未經核准允許更改**– 資料實體可以在不透過工作流程處理的情況下更新廠商記錄。
    - **拒絕更改**– 不能對廠商記錄進行更改。 匯入將因工作流程啟用的欄位失敗。
    - **建立變更建議**– 除為工作流程啟用的欄位外，所有欄位都將更改。 那些欄位的新值將作為建議更改新增到廠商，並且工作流程將自動啟動。

4. 在廠商欄位清單中，選取每個欄位的 **啟用** 核取方塊，在進行更改之前都必須核准。
5. 前往 **應付帳款\>設定\>應付帳款工作流程**。
6. 選擇 **新建**。
7. 選取 **建議的廠商變更工作流程**。 
8. 設定工作流程，使其與您的核准流程相符。 **建議廠商變更的工作流程核准** 工作流程核准元素會將更改內容應用到廠商上。

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a>更改廠商資訊並將更改送出到工作流程

當您更改為工作流程啟用的欄位時，**建議變更** 頁面便會出現。 此頁面顯示欄位的原始值和您輸入的新值。 您更改的欄位將恢復為其原始值。 狀態訊息還會通知您，您的更改尚未送出。 

每次更改為工作流程啟用的欄位時，該欄位都會新增到 **建議變更** 頁面。 若要放棄欄位的建議值，請使用清單中欄位旁的 **放棄** 按鈕。 若要放棄所有更改，請使用頁面底部的 **放棄所有更改** 按鈕。 選取 **確定** 關閉頁面。

在您至少提出一項建議更改後，動作窗格上會出現兩個附加索引標籤：**建議變更** 和 **工作流程**。

1. 選取 **建議變更** 打開 **建議變更** 頁面並查看您的更改。
2. 選取 **工作流程\>送出，將工作流程的更改送出**。

    頁面狀態變為 **待核准的更改**。

工作流程遵循標準工作流程過程。 核准者會被引導到 **廠商** 頁面，更改內容可以在其中查看 **建議更改** 頁面，然後選取 **工作流程\>核准**，核准工作流程。 完成所有核准後，將使用您建議的值更新欄位。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
