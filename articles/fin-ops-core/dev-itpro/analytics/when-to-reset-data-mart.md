---
title: 資料超市重設常見問題
description: 本主題提供有關資料超市重設的一些常見問題的解答。
author: jinniew
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 53f45f469c39f9e389763aa0daed658e5a62d377
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2022
ms.locfileid: "8460555"
---
# <a name="data-mart-resets-faq"></a>資料超市重設常見問題

本主題提供有關資料超市重設的一些常見問題的解答。 重設資料超市可能是一個耗時的過程，並且根據具體情況，可能不是所需的解決方案。 因此，本主題包含有關資料超市重設可能有幫助的情況以及不太可能提供幫助的情況的資訊。

## <a name="what-is-a-data-mart-reset"></a>什麼是資料超市重設？

資料超市重設將停用整合工作，刪除所有資料超市資料，然後重新啟用整合。

若要確保不插入舊資料，只有在現有工作完成後才能啟動資料超市重設。 如果您嘗試在所有工作完成之前重設資料超市，您可能會收到一條訊息，例如「由於作用中工作，無法處理資料超市重設。 請稍後再試。」

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>我什麼時候必須重設資料超市？

如果以下一項或多項陳述式適用於您的情況，則您的組織可以從資料超市重設中受益：

- **應用程式資料庫已恢復**
- **您打開了支援票證**- 作為故障排除步驟的一部分，支援工程師指示您重設資料超市。
- **高百分比的過期記錄**- 過期記錄本身並不一定證明資料超市重設是合理的。 高百分比的過期資料會降低整體報表產生和整合效能，並導致額外的資料庫空間使用。 當資料超市中有超過 80% 的過期資料時，我們建議您完成資料超市重設以刪除過期資料。
 
> [!NOTE]
> 重設資料超市的過程受資料庫中總帳和預算交易數量的影響。 根據系統中的交易數量，資料集市重設可以在 15 分鐘內完成，也可以長達 4 小時。 但是，如果您的重設時間超過四個小時，我們建議您聯絡支援。
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>什麼時候資料超市重設不合適？

以下是我們不建議您重設資料超市的一些情況：

- 您遇到資料整合效能問題。
- 由於以下任何原因，您有一個定期的重設模式：

    - **報表中缺少或意外的資料**– 如果您發現資料遺失，請向 Microsoft 開具支援票證，以查看您的報表格式和可能的資料同步問題。
    - **卡住整合狀態**
   
## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>如果我重設資料超市，我會遺失我已經設計好的報表嗎？

否。 您的報表儲存在不受資料超市重設影響的 SQL 表中。 如果您擔心遺失您設計的報表，您可以備份您不想遺失的設計。 若要備份設計，請打開 Report Designer，然後進入 **公司\>公司\>建構元素\>匯出**。
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>在我可以重設資料超市之前，是否所有使用者都必須退出系統？

否。 在資料超市重設期間，使用者可以繼續在系統中工作。 但是，在完成重設之前，使用者將無法存取使用 Financial Reporter 建立的任何報表。

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
