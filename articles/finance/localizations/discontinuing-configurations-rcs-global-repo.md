---
title: 在 RCS Global 存放庫中中止設定
description: 本主題介紹如何中止 RCS Global 存放庫中的設定。
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 340fc96e7dfe56da9ee8d4831a5980e3e96ec3ee0f2f5a8fb2ab72f713de9737
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450132"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>在 RCS Global 存放庫中中止設定

[!include [banner](../includes/banner.md)]

本主題介紹如何中止 RCS Global 存放庫中的設定。 以前，只能刪除不再需要的設定。 但是現在您可以在 RCS Global 存放庫將已發佈的設定標記為 **已中止**。 使用此功能，您還可以執行以下作業： 
 
 - 在計劃中止設定時提供提前通知。
 - 包括有關替換設定的適用詳細資料。
 - 為特定設定設定 **支援截止日期**，以通知使用者何時中止該設定。

中止設定版本時，可以指定以下選用資訊：

  - **替換設定**
  - **替換設定版本**
  - **任意文字附註**：使用此欄位可提供文件連結或參考
  - **支援截止日期**：此欄位提供支援目前設定/版本的建議日期。 此日期必須手動更新。
  
要中止設定，請完成以下步驟。 

1. 通過將 **所有版本** 設定為 **是**，選擇在一次作業中是要停用單個版本，還是要停用具有相同設定的所有版本。 
2. 將 **中止** 參數設定為 **是**。
3. 選擇 **確定** 中止設定。 儲存變更時將填入 **中止日期** 欄位。

![中止設定資訊。](media/Discontinue-details-2.png)
  
您可以將設定恢復為 **共用**，或可隨時調整中止資訊。 如果您共用設定，請指定 **支援截止日期** 日期和與中止有關的所有其他資訊，以表明您未來中止的計劃。

如果您想共用有關計劃中止的資訊，在實際中止設定之前，使用者可以預先填寫與替換相關的所有欄位，但可以將 **中止** 參數設定為 **否**。

> [!NOTE]
> 中止不會限制設定作業。 您可以繼續匯入、執行或衍生設定，這些欄位僅供參考。

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>財務從版本 10.0.14 開始支援顯示此資訊

從版本 10.0.14 開始，Dynamics 365 Finance 支援顯示停用資訊。 在 **全域存放庫** 頁面，您可以查看與中止相關的最新資訊。 預設情況下，已停用的設定會被篩選掉。
  
**匯入的設定** (ERSolutionTable) 頁面，顯示匯入時已經中止的設定。 對於匯入後中止的設定，可以透過執行 **匯入設定更新** 工作來同步停用資訊。


