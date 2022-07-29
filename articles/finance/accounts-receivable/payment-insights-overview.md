---
title: 客戶付款深入解析 (預覽版)
description: 本主題說明有助於改善對個人客戶典型付款實務的理解的付款深入解析功能。 此功能協助您辨別證明比其他可能已經完成更早啟動收款流程的正當性的場合。
author: ShivamPandey-msft
ms.date: 11/06/2019
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
ms.openlocfilehash: d359e3ceef0fb7213d52aeb265da2e75120ae223
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451419"
---
# <a name="customer-payment-insights-preview"></a>客戶付款深入解析 (預覽版)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題說明有助於改善對個人客戶典型付款實務的理解的付款深入解析功能。 此功能協助您辨別證明比其他可能已經完成更早啟動收款流程的正當性的場合。 

## <a name="overview"></a>概觀

很難預測客戶何時支付發票。 缺乏深入解析會造成現金流預測不夠精確、收款流程太晚開始，以及向可能拖欠付款的客戶釋訂單。 客戶付款深入解析 (預覽版) 可幫助組織預測客戶支付發票的時間點。 本項資訊會幫助組織擬訂收款策略，改善按時付款的可能性。 

## <a name="predictions"></a>預測

付款預測將促使組織憑藉幫助他們輕鬆辨別很可能延遲付款的發票改善業務流程，並採取適當措施改善他們按時收到款項的機會。

充分運用歷史發票、付款和客戶資料的機器學習模型可促使客戶付款深入解析 (預覽版) 更準確預測客戶支付待付發票的時間點。

以每張未結發票而言，客戶付款深入解析 (預覽版) 可以預測三種付款可能性：

-   準時收到款項的可能性。 
-   晚收款項的可能性。
-   極晚收到款項的可能性。

客戶付款深入解析 (預覽版) 也提供預期付款的彙總視圖，幫助組織了解他們可以預測客戶屬於三桶當中哪一種情況，按時、延遲和非常延遲付款。

[![付款預測的彙總視圖。](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

每張發票也會指派按時付款的可能性。 如果按時付款的可能性低於 50%，發票會以紅圈標記，指出這些發票可能需要留意收款情況。 

[![付款可能性清單。](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Customer Payment Insights (預覽版) 也提供上下文資訊解釋預測，例如影響預測的前幾項因素、與客戶目前的業務往來狀態以及有關歷史客戶付款行為的細節。 許多企業的收款流程一直屬於被動性活動；收款流程須等發票到期後才會開始。 

憑藉 Customer Payment Insights (預覽版)，組織可以更主動地收款。 他們不再需要等待交易到期才能開始收款流程。 他們反而可以使用付款預測功能判定主動收款是否將改善按時付款的可能性。 付款預測也給企業證明儘早開始收款流程所需的資訊。

## <a name="methodology"></a>方法論

開發和部署 AI 解決方案困難重重。 它需要由資料科學家、主題專家和工程師組成的團隊，加班訂定、開發、部署和維護可用的 AI 解決方案。 我們正在簡化 Finance 中部署和使用 AI 解決方案的流程。 我們正在預先包裝以 Microsoft AI Builder 為首建構的 Finance AI 解決方案。 終端使用者點選一次按鈕，就能部署 AI 解決方案並開始充分利用智慧預測的優勢。 如果組織對預測的精確度不滿意，Power 使用者再點選一次就能進入 AI builder 擴充體驗，然後選取或取消選取用來產生成預測的欄位。 一旦準備就緒，他們可以訓練和發佈更改，新訓練的模型將自動挑揀到 Finance 執行預測。

## <a name="how-to-get-customer-payment-insights-preview"></a>如何取得 Customer Payment Insights (預覽版)

如果您有興趣試用 Customer Payment Insights (預覽版)，請傳送電子郵件給 [Customer Payment Insights (預覽版)](mailto:fiap@microsoft.com)。

## <a name="privacy-notice"></a>隱私權公告事項

預覽版 (1) 可以利用隱私權和安全性措施比 Dynamics 365 Finance 財務和營運應用程式服務少的特性，(2) 不納入本服務的服務等級協定，(3) 不應用來處理個人資料或其他受到法律或規管法令遵循要求規範的資料，及 (4) 支援有限。




[!INCLUDE[footer-include](../../includes/footer-banner.md)]