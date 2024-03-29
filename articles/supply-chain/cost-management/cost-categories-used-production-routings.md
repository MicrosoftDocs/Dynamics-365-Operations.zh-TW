---
title: 生產路線規劃中使用的成本類別
description: 本文提供有關適用於使用路線規劃的製造環境之成本類別的資訊。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjCategory, RouteCostCategoryPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78153
ms.assetid: a3fdc76c-0a27-4723-b1c7-4322f707d89e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca4c0c9cecb79366cdd41069cb6c96f01b44a2094f4caf57077c391beb6ac106
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447309"
---
# <a name="cost-categories-used-in-production-routing"></a>生產路線規劃中使用的成本類別

[!include [banner](../includes/banner.md)]

本文提供有關適用於使用路線規劃的製造環境之成本類別的資訊。

成本類別適用於使用路線規劃的製造環境。 這些類別指派至營運資源和路線規劃作業，以定義每小時成本，並在製造項目的計算成本中細分成本貢獻。 指派至成本類別的成本群組依據營運資源和活動類型 (例如設定時間和執行時間) 對製造成本貢獻進行分類。 成本群組指派的特殊性使製造費用能夠根據路線規劃資訊進行計算。 

**注意：** 在製造環境中，成本類別有其他幾個名稱，例如人工費率代碼或機器費率代碼。 

每個成本類別都有關聯的成本記錄和指派的成本群組。 不同的生產目的需要不同的成本類別。

-   根據營運資源指派不同的每小時成本。 例如，不同類型的勞動技能、機器或製造單元，成本可能不同。
-   為與路線規劃作業關聯的設定時間或執行時間指派不同的每小時成本。
-   根據輸出數量而非每小時成本指派營運資源成本，例如支付人工的論件計酬制。
-   為製造項目的計算成本提供成本貢獻的成本群組細分。 例如，您可以細分人工和機器成本。
-   為間接費用計算公式提供成本群組基礎，例如與人工和機器相關的間接費用，或與設定和執行時間相關之間接費用的公式。

可以將成本類別指派至路線規劃作業的設定時間、處理時間和數量。 例如，設定時間和製程時間之間的成本或成本群組細分不同時，應定義不同的成本類別，並將其指派至設定時間和製程時間。 設定時間、製程時間和數量的成本類別選擇性使用由指派至作業的路線群組決定。 將成本類別指派至時間和數量可以由 **生產控制參數** 頁面定義的公司範圍內原則強制執行。 

每個成本類別都有相關的成本，這些成本基於成本核算版本中成本記錄的定義。 使用 **成本類別價格** 頁面來定義指定成本核算版本和站點的成本記錄。 在首次輸入成本類別的成本記錄時，它具有 **待處理** 狀態和預期生效日期。 當您啟用項目成本記錄時，狀態將更新為 **目前使用中**，且生效日期會更新為啟用日期。 不同的成本記錄可能反映不同的地點、生效日期或狀態。 未來或歷史日期的物料清單 (BOM) 計算使用具有相關生效日期的成本記錄。 目前的活動成本記錄將用於估計生產訂單成本，並根據生產訂單評估報告的時間。 

成本類別的成本記錄可以是特定於站點的或是全公司的。 要使成本記錄特定於站點，請為其指派一個站點。 否則，空白值表示成本記錄適用於公司中的所有站點。 例如，由於站點之間的成本可能不同，因此必須將成本記錄定義為特定於站點。 

路線規劃作業通常繼承指派至營運資源或主要作業的成本類別。 建立生產訂單時，生產途程中的傳送作業會反映所選的途程版本。 您可以覆寫指派至生產途程中作業的成本類別。 

部分類型的生產工作可以套用於專案時間估算和報告。 此時針對生產和專案目的，需要成本類別。 成本類別標示為用於專案時，您必須定義更多專案相關資訊。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]