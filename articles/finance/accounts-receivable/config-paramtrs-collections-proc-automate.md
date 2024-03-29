---
title: 設定收帳流程自動化的參數
description: 本主題介紹影響自動收帳流程的參數，並提供設定這些參數的指南，以便自動化流程反映您的意圖和期望。
author: JodiChristiansen
ms.date: 08/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3055e10375f1b0be936e3ed0344cdf33dc7bc7e9
ms.sourcegitcommit: 3f6cbf4fcbe0458b1515c98a1276b5d875c7eda7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "8450972"
---
# <a name="configure-parameters-for-collection-process-automation"></a>設定收帳流程自動化的參數

[!include [banner](../includes/banner.md)]

本主題介紹影響自動收帳流程的參數，並提供設定這些參數的指南，以便自動化流程反映您的意圖和期望。 有關如何自動化收帳流程的資訊，請參閱[收帳流程自動化](collections-process-automate.md)。

## <a name="general"></a>一般
在 **每個批次工作的客戶百分比** 中輸入一個數字，以確定每個自動化流程的批次工作數。 將 **自動過帳催款單** 設定為 **是**，讓催款單動作類型在自動化期間過帳該催款單。 將 **為自動化建立活動** 設定為 **是**，為非活動動作類型建立和關閉活動以查看對帳戶執行的所有自動化步驟。 在 **保留收帳流程自動化歷史記錄的天數** 中定義收帳歷史記錄儲存的天數。 當發票到達收帳流程的最後一步時，如果 **啟用最後一個流程步驟後排除發票** 設定為 **是**，它將不會用於建立未來的流程自動化動作類型。 下一張最舊的發票確定下一個流程自動化步驟，以確保收帳流程自動化動作繼續進行。 

## <a name="payment-predictions"></a>付款預測
從版本 10.0.21 開始，Finance Insights 中的客戶付款將預測預測發票是否會按時、逾期或嚴重逾期支付。 您可以在 Finance Insights 中設定每個類別。 如果預計發票將逾期支付，請務必在發票到期之前開始收帳流程。 這些預測可用於在收帳流程自動化執行時建立收帳活動。 將 **啟用付款預測** 設定為 **是**，使用客戶付款預測來根據發票逾期支付的可能性建立收帳活動。 

有關客戶付款預測和 Finance insights 的更多資訊，請參閱[客戶付款預測](payment-insights-overview.md)。

當客戶付款預測模型執行時，它會為發票按時、逾期或嚴重逾期支付的預測分配一個百分比。 在預計逾期付款的情況下，您可以使用該資訊透過收帳流程自動化自動啟動收帳活動。 您可以在 **信用和收帳 > 收帳** 下的 **每個客戶的付款預測** 或 **每筆交易的付款預測** 頁面上查看這些百分比。 

如果客戶發票的平均付款預測低於基準百分比，則不會建立任何活動。 如果客戶發票的平均付款預測大於或等於基準百分比，將為每個客戶建立一個活動。 對於 **預測：逾期**，輸入達到多少 **基準百分比** 時收帳流程自動化應建立收帳活動。 這是逾期和嚴重逾期的彙總值。 選擇一個 **商業文件範本** 以用於建立的活動或建立新活動。 這將確定 **類型**、**用途** 和 **距離活動結束的天數**。 輸入任何 **附註**，這將預設為建立活動時的描述。 對於 **預測：嚴重逾期**，輸入達到多少 **基準百分比** 時收帳流程自動化應為預測會嚴重逾期支付發票的客戶建立收款活動。 選擇一個 **商業文件範本** 以用於建立的活動。 這將確定 **類型**、**用途** 和 **距離活動結束的天數**。 輸入任何 **附註**，這將預設為建立活動時的描述。 

### <a name="example"></a>範例 
如果逾期基準百分比設定為 60%。 當對每個發票執行客戶付款預測時，系統會分配按時、逾期或嚴重逾期支付的百分比預測。 如果發票將逾期支付的付款預測為 59% 或更少，則自動收帳流程不會為該發票建立收帳活動。 如果發票的客戶付款預測大於或等於 60%，則在收帳流程自動化期間建立收帳活動。 

> [!NOTE]
> 嚴重逾期預測在逾期預測之前進行評估，因為嚴重逾期包括預計將逾期支付的發票。 如果發票同時屬於逾期和嚴重逾期的基準，收帳流程只會產生一項活動。 在這種情況下，系統使用嚴重逾期的活動和商業文件，因為嚴重逾期的優先順序更高。 任何其他已經產生的動作都不會再次產生。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
