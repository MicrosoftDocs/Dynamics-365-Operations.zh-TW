---
title: 將精益作業組織模型化
description: 本文提供將精益作業組織模型化的重要概念相關資訊。
author: johanhoffmann
ms.date: 09/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, KanbanFlowSelection, KanbanFlow
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f3958d21188163fe95e36ba4b8117ae8314b0fd1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448281"
---
# <a name="modeling-a-lean-organization"></a>將精益作業組織模型化

[!include [banner](../includes/banner.md)]

本文提供將精益作業組織模型化的重要概念相關資訊。 

通常，精益製造方案並非只是一組不相關的看板規則或材料供應政策。 在特定生產或供應方案中，工作單元和位置的整個材料和產品流程可視為處理程序或轉移活動的序列或小型網路。 該序列或網路稱為生產流程。

## <a name="production-flows-in-lean-manufacturing"></a>精益製造生產流程
在基於生產訂單的生產方案中，材料會發布到特定生產訂單。 在基於物料清單 (BOM) 和途程的一系列作業過程中，產品被建立且最終由供應位置接收。 生產訂單的輸送量時間從幾分鐘到幾週不等。 所有相關成本、材料和人力都會在生產訂單上累計。 

為了縮短交貨時間及避免批次生產導致工作中心之間的庫存過剩，精益製造在製造和倉庫補貨程序中導入了看板補貨和超市功能。 通常這些功能會干擾部分獨立的看板週期的生產。 半成品的看板補貨作業不再由成品訂單觸發。 

為了針對提出的各種看板方案重新建立生產和成本環境，精益製造導入以活動為基礎的生產流程做為骨幹。 所有看板規則均會參照此預先定義結構。 基於活動的模型支援設定各種方案。 不過，此模型不會增加現場人員的操作複雜度，因為所有方案都使用基於活動的相同使用者介面。

## <a name="semi-finished-products-non-bom-levels"></a>半成品 (非 BOM 層級)
精益製造將庫存產品和半成品的看板整合於單一架構中，因此可為所有案例提供一致的使用者體驗。 有了這種架構後，您不需再導入額外 BOM 層級即可將看板用於半成品。 這種架構還有助於將庫存交易降至最低。

## <a name="products-and-material-in-work-in-progress"></a>產品和在製品材料
如果每個揀貨流程或看板登錄都會產生品項消耗交易，在精益製造中將單一流程的批量減少至理想狀態可能會導致庫存交易急劇增加。 生產流程架構可將材料連同儲存體或運輸承辦單位批量中的撤銷看板，一併轉移至生產流程。 已發布材料的金額會新增至與生產流程相關的在製品 (WIP) 科目。 此行為類似於發布材料給生產訂單的行為。 同樣的原理可套用於產品和半成品。 除非這些產品是在生產流程中建立、轉移或消耗，否則不一定要進行庫存交易。 產品過帳到庫存後，生產流程的 WIP 科目會扣除相關標準成本。

## <a name="value-streams-and-value-stream-mapping"></a>價值流和價值流對應
精益製造架構由 Womack 和 Jones 制訂的五項精益作業原則啟發：客戶價值、價值流、流程、拉式管理和盡善盡美。 要在實際製造環境中實施精益製造解決方案，一種經核可的方法是價值流對應 (VSM)。 Rother 和 Shook 在精益製造研究所出版物《Learning to See》中介紹了這種方法。 

未來狀態價值流可經過模型化，成為生產流程版本。 所有價值流程序都模型化為程序活動。 如果必須登錄轉移狀態，或如果需與庫存揀選或合併裝運整合，則可以將移動或轉移作業模型化為轉移活動。 

價值流本身會模型化為一個營運單位。 因此，價值流可做為財務維度。

若需營運單位的更多相關資訊，請參閱[建立營運單位](../../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md)。

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a>根據生產流程核算精益製造成本
定期合併生產流程成本可修正相關在製品科目，並確定生產流程供應的產品差異。

## <a name="continuous-improvement"></a>持續改進
為了協助持續改進，系統會導入具時間效益的生產流程版本。 因此，現有生產流程版本與所有相關看板規則可複製到生產流程的未來版本中。 此外，可以在驗證並啟動以進行生產前，將未來狀態的生產流程模型化。 為了協助確保材料流程自轉換日期起順利執行，舊版本生產流程的現有看板會自動與新版本建立關聯。

## <a name="simplicity"></a>簡易性
在實施精益製造程序方面，我們選擇採用一種生產流程和活動方法，讓簡單和複雜的生產方案能在單一可擴充架構中模型化。 若深入瞭解活動概念，可看出這個概念可為需要的工廠和物流工作人員帶來新的簡易性。 所有精益製造變體採用一致使用者介面，並以基於活動的作業產生報告而不使用庫存交易，可讓使用者以簡單介面處理複雜的精益製造骨幹，也就是生產流程。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]