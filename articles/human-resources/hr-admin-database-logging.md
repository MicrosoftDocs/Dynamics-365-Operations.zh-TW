---
title: 配置和管理資料庫記錄
description: 您可以使用資料庫記錄追蹤在 Dynamics 365 Human Resources 的表格與欄位變更情況。
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3cbe4c105b14935db6803e4bded0d891c564fb81
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452238"
---
# <a name="configure-and-manage-database-logging"></a>配置和管理資料庫記錄


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以使用資料庫記錄追蹤在 Dynamics 365 Human Resources 的表格與欄位變更情況。 本主題說明如何：

- 管理資料庫記錄的安全性和效能
- 設定資料庫記錄
- 清理資料庫日誌

## <a name="overview-of-database-logging"></a>資料庫記錄概觀

您可以使用資料庫記錄追蹤在 Microsoft Dynamics 365 Human Resources 的表格與欄位變更情況。 這些變更包括插入、更新或刪除。 資料庫記錄將表格或欄位變更記錄儲存在資料庫日誌資料表。

資料庫記錄的商務用途包括：

- 針對含有敏感資訊的特定資料表變更建立稽核記錄。
- 追蹤單筆交易。 資料庫記錄無意用來追蹤批次工作中執行的自動交易。

## <a name="security-for-database-logging"></a>資料庫記錄的安全性

資料庫記錄會包含敏感性資料。 限制存取只包括需要存取記錄資料的資訊安全角色。

## <a name="database-logging-and-performance"></a>資料庫記錄和效能

雖然從商業角度來看很有價值，但資料庫記錄在資源使用和管理方面所費不貲。 資料庫記錄的效能含意包括：

- 資料庫記錄資料表成長快速，會增加資料庫規模。 成長端賴您決定保存記錄的資料量而定。 預設情況下，資料庫日誌資料表只能維護 30 天的記錄資料。 

- 資料庫記錄會對長期執行的自動化流程產生不利影響，例如長期匯入資料。

### <a name="best-practices"></a>最佳實務作法

若要改善效能，請藉由選取要記錄的特定欄位，而不是整個資料表來限制記錄登錄項目。 為了有助於維持整體效能，資料庫記錄以 20 個資料表為限。

> [!NOTE]
> 只會記錄個別欄位的更新。

## <a name="set-up-database-logging"></a>設定資料庫記錄

您可以使用 **記錄資料庫變更** 精靈設定資料庫記錄。 此精靈提供靈活設定資料表或欄位的記錄方式。

1. 請前往 **系統管理 > 連結 > 資料庫 > 資料庫日誌設定**。 選取 **新** 開始 **記錄資料庫變更** 精靈。
2. 選取 **下一步**。 
3. 請在小精靈的 **表格和欄位** 頁選取希望啟用資料庫日誌記錄的資料表和欄位，然後選取 **下一個**。

   > [!Note]
   > 人力資料資料庫裡的所有表格無法使用資料庫記錄。 選取清單下方的 **顯示所有資料表** 就會展開資料表和欄位清單，顯示可使用資料庫記錄功能的所有資料庫資料表，但這將是完整資料庫資料表清單的子集合。

4. 請在精靈的 **變更類型** 頁選取您要追蹤每個資料表和欄位變更的資料作業，然後選取 **下一步**。 請參閱下方資料表了解記錄時可使用的資料作業說明。
5. 請在 **完成** 頁回顧將進行的變更內容，然後選取 **完成**。

| 作業 | 描述 |
| -- | -- |
| 追蹤新交易 | 針對資料表建立的新記錄建立記錄。 |
| 更新 | 針對資料表更新記錄，或資料表中個別選取欄位的更新內容建立記錄。 如果您選取資料表的記錄更新，則每次資料表上任何一筆記錄的任一欄位更新時，都會建立日誌記錄。 如果您選取特定欄位的記錄更新，則只在資料表記錄的欄位更新時才會建立日誌記錄。 |
| 刪除 | 針對資料表刪除的記錄建立記錄。 |
| 重新命名金鑰 | 重新命名資料表索引鍵時建立日誌記錄。 |


## <a name="clean-up-database-logs"></a>清理資料庫日誌

您可以使用下列選項刪除全部或部分資料庫日誌：

- 選取特殊資料表的所有日誌。
- 選取特定類型的資料庫日誌。
- 選取建立日誌的日期和時間。

若要設定資料庫日誌清理，請遵從下列步驟： 

1. 請前往 **系統管理員 > 連結 > 資料庫 > 資料庫記錄**。 選取 **清理日誌**。
2. 請在 **預計包括的記錄** 標題下方選取 **篩選**。
3. 選擇將用來選取要刪除日誌的方法。 請輸入下列其中一個選項：

   - 表格 ID
   - 日誌類型
   - 建立日期和時間

4. 請使用 **資料庫日誌清理** 索引標籤判定執行日誌清理任務的時間點。 預設情況下，資料庫日誌可使用 30 天。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
