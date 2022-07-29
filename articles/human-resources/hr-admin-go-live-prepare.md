---
title: 人力資源上線前置作業
description: 本頁提供如何準備 Dynamics 365 Human Resources 上線的指引。
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ff7d689129a4015b6085685f4b19ae61bdd549d2
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452232"
---
# <a name="prepare-for-human-resources-go-live"></a>人力資源上線前置作業

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../includes/peap-2.md)]

本主題說明如何使用 Microsoft Dynamics  Lifecycle Services (LCS) 準備 Dynamics 365 Human Resources 專案上線。 

本圖顯示上線流程的各個階段。 

![上線流程。](./media/hr-admin-go-live-prepare-process.png)

下表列出流程中的所有步驟、預期持續時間以及操作負責人。

| 階段 | 動作 | 持續時間/時間點 | 對象 | 附註 |
| --- | --- | --- | --- |--- |
| 1 | 更新 LCS 的上線日期 | 最晚提前 2-3 個月 | 合作夥伴/客戶 | 里程碑日期應持續更新。 |
| 2 | 完成並傳送核項清單 | 待用戶驗收測試 (UAT) 完成後 | 合作夥伴/客戶 | 按照 [FastTrack 上線評估](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment) 提供的說明操作。 |
| 3 | 專案評估 (FastTrack) | FastTrack 架構師* | 架構師收到核項清單後開始評量並繼續審查到問題獲得澄清，且緩解措施到位為止 (依適用情況為之)。 |
| 4 | 專案工作坊 (FastTrack) | FastTrack 架構師* | |
| 5 | 資料包匯入 | 端賴專案而定 | 合作夥伴/客戶 | 請按照[資料管理概觀](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md) 的說明操作．|
| 6 | 實際執行前置作業完成 | 待所有上一頁步驟完成之後 | 合作夥伴/客戶 | 合作夥伴/客戶可以控制正式環境。|
| 7 | 切換活動 | 端賴專案而定 | 合作夥伴/客戶 | |
| 8 | 上線 | 端賴專案而定 | 客戶 | |

> [!IMPORTANT]
> *步驟 3 和 4 只適用符合 FastTrack 資格的客戶。

## <a name="completing-the-lcs-methodology"></a>完成 LCS 方法論

每個落實專案的重要里程碑皆為切換到正式環境。 完成步驟的流程分成兩部分： 

- 執行實際工作，例如適應力-差距分析或用戶驗收測試 (UAT)。 
- 將對應 LCS 方法的步驟標示為已完成。 

完成方法論裡的步驟是不錯的實際作法，因為在落實方面已經有所進展。 切勿等到最後一分鐘。 穩紮穩打的落實符合客戶的最大利益。 

## <a name="uat-for-your-solution"></a>UAT 專為您的解決方案開發

UAT 階段期間，您必須在落實專案的沙箱環境測試已經落實的所有業務流程及已經進行的任何客製化動作。 為了有助於確保成功上線，完成 UAT 階段時應考慮下列事項： 

- 我們建議您的 UAT 流程從乾淨全新整理的環境開始，因為 UAT 流程開始之前，資料就會從您的 GOLD 組態複製到環境中。 我們建議您上線之前先將正式環境當成 GOLD 環境使用，環境這時會變成正式環境。
- 測試個案涵蓋整個要求範圍。 
- 使用遷移資料測試。 這應該包括背景工作角色、工作和職位等資料。 也包括期初餘額，如累計的休假和缺勤天數。 最後，包括未結交易，例如目前的福利註冊。 使用所有類型的資料完成測試，即使資料集合尚未定案。 
- 使用指派給用戶的正確資訊安全角色 (預設角色和自訂角色) 測試。 
- 確定解決方案符合任何公司和產業指明的監管要求。 
- 記錄所有功能並取得客戶核准和簽字認可。 

## <a name="mock-go-live"></a>模擬上線

上線之前，您必須執行模擬上線測試從舊版系統切換到新版系統所需的步驟。 您應該在沙箱環境裡執行模擬上線，並將所有步驟納入您的切換計劃。

- 我們建議您上線之前先將正式環境當成 GOLD 組態環境。
- 確保您的強大治理流程已經準備就緒，能保護正式環境在上線之前遭到意外交易或更新的影響。
- 當您準備好執行 UAT 或模擬上線時，請從正式環境重新整理沙箱環境。 更多相關資訊，請參閱[複製執行個體](hr-admin-setup-copy-instance.md)。
- 在沙箱環境測試切換計劃的每個步驟，然後借由從正式環境執行抽查或從 UAT 程式碼執行測試來驗證沙盒箱環境。
  - 測試應包括所有資料移轉，包括上線所需的轉換。
  - 這段流程應包括對任何舊版系統進行截斷實務作法。
  - 請務必確定在您的模擬切換中納入任何整合切換步驟或外部系統步驟。
- 如果模擬截斷期間發現任何問題，您可能需要進行第二次模擬切換。 為此，我們建議您在專案計劃中計劃兩道模擬切換手續。

## <a name="fasttrack-go-live-assessment"></a>FastTrack 上線評量

具備 FastTrack 使用資格並參與 FastTrack Solution Architect 的客戶將使用 Microsoft FastTrack 完成上線審查。 更多資訊，請參閱 [Microsoft FastTrack](/dynamics365/fasttrack/)。 

上線前大約八週的時候，FastTrack 團隊會請您填寫一份[上線核項清單](https://go.microsoft.com/fwlink/?linkid=2146013)。

專案經理或關鍵專案成員必須在專案上線前的預備階段完成上線核項清單。 典型作法是在完成或幾近完成 UAT 時，在提議的上線日期前四到六週完成核項清單 。 

完成上線核項清單後，請傳送電子郵件到 您的 FastTrack Solution Architect 。 請務必在電子郵件納入客戶和施行夥伴的關鍵利害關係人。 

提交核對清單後，您的 FastTrack Solution Architect 將審核專案並提供評量單，內文描述潛在風險、最佳實務作法和專案上線成功的建議事項。 某些情況下，Solution Architect 可能會特別強調風險因素並要求制訂緩解計劃。 

## <a name="see-also"></a>也請參閱

[上線常見問答集](hr-admin-go-live-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
