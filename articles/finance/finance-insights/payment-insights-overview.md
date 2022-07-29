---
title: 客戶付款預測
description: 本主題說明能幫助您更了解客戶典型付款實務做法的付款預測功能。 本功能也會有助於辨別應能敦促您比其他可能的開始方式更早啟動收款流程的場合。
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 04897e3a7765264ab2e664422caa928c49b9cc61
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451371"
---
# <a name="customer-payment-predictions"></a>客戶付款預測

[!include [banner](../includes/banner.md)]

本主題說明能幫助您更了解客戶典型付款實務做法的付款預測功能。 本功能也會有助於辨別應能敦促您比其他可能的開始方式更早啟動收款流程的場合。

## <a name="overview"></a>概觀

各組織往往發現預測客戶何時支付發票極具挑戰性。 缺乏這項見解可能導致的問題如下：

- 較不精確的現金流量預測
- 太晚開始的收款流程
- 向可能拖欠付款的客戶釋出訂單

客戶付款預測有助於組織預測客戶支付發票的時間點。 因此，他們可以建立收款策略，協助增加他們按時收款的可能性。

## <a name="predictions"></a>預測

付款預測讓組織藉由協助他們辨別極有可能延遲支付的發票，改善他們的業務流程。 組織可以使用該項資訊採取行動，提高他們按時收到款項的機會。

客戶付款預測功能使用機器學習模型更準確預測客戶何時支付待付發票。 此機器學習模型包括歷史發票、付款和客戶資料。

以個別未結發票而言，此功能指派三種付款可能性：

- 款項將準時支付的可能性。
- 款項將晚付的可能性。
- 款項將非常晚付的可能性。

本功能也提供預期付款的彙總視圖。

[![付款預測的彙總視圖。](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

每張發票被指派準時付款的可能性。 準時付款的可能性低於 50% 的發票會標記紅圈，指出它們可能需要收款代理人留意。

[![付款可能性清單。](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

客戶付款預測功能也提供上下文資訊解釋預測。 本項資訊包括影響預測的主要因素、目前與客戶生意往來狀態以及有關客戶歷史付款行為的細節。

許多企業的收款流程一直屬於被動活動。 換句話說，收款流程是在發票到期後才會開始。 客戶付款預測讓組織更積極收款。 他們不再需要等到交易到期才開始收款流程。 他們反而可以使用付款預測功能判定積極收款是否將改善準時付款的可能性。

## <a name="methodology"></a>方法論

以往開發和部署人工智慧 (AI) 解決方案一直困難重重。 流程一直要求由資料科學家、主題專家 (SMEs) 和工程師組成的團隊，加班訂定、開發、部署和維護可用的 AI 解決方案。 客戶付款預測促使在 Microsoft Dynamics 365 Finance 中部署和使用 AI 解決方案變得容易。 Microsoft 正在預先包裝以 Microsoft AI Builder 為首建構的 AI 解決方案。 因此，使用者只需點選一次滑鼠就能部署 AI 解決方案，充分利用智慧預測的優勢。 如果您對預測的精確度不滿意，Power 使用者可以 (再點選一次滑鼠) 進入 AI Builder 擴充體驗，然後選取或清除用來產生預測的欄位。 一切準備就緒後，您就能 "訓練" 模型並發佈更改內容。 新訓練的預測模型將自動挑選出來在 Dynamics 365 Finance 產生預測。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
