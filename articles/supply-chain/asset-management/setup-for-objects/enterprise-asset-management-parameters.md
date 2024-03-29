---
title: 資產管理參數
description: 在資產管理中，必須設定資產、工單和工單排程相關的一般參數。
author: johanhoffmann
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1659fd3b4c173ffe09f245631309d329bba5b1bd
ms.sourcegitcommit: f2a78e0d7d461ca843ac2f9abff7690275db9196
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450051"
---
# <a name="asset-management-parameters"></a>資產管理參數

[!include [banner](../../includes/banner.md)]

在資產管理中，必須設定資產、工單和工單排程相關的一般參數。 本主題說明如何設定這些參數。 選取 **資產管理** > **設定** > **資產管理參數** 以開啟頁面。

> [!NOTE]
> 若您想要設定內含示範資料的系統，以測試資產管理功能，請參閱[部署示範環境](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md)以取得說明。

## <a name="the-assets-tab"></a>資產索引標籤

**資產** 索引標籤提供以下設定：

- **預設功能位置** 是標準功能位置，建立新資產時會自動為資產選取。  
- 在 **標準行事曆** 欄位中，選取資產未選取資源時要用來計算資產 KPI 的行事曆。  
- 在 **檢視** 欄位中，選取開啟 **資產檢視** 所呈現的標準檢視 (**資產管理** > **一般** > **資產** > **資產檢視**)。
- **預設要求類型** 是標準維護要求類型，建立新要求時會自動選取。  
- 作業類型預測會存放於 **預測專案** 欄位選取的專案。 每種工作類型都會在預測專案上自動建立新活動。 然後，作業類型預測會儲存於預測專案中。  
- 在 **模型** 欄位中，選取作業類型和工單預測使用的預測模型。

## <a name="the-work-orders-tab"></a>工單索引標籤

**工單** 索引標籤提供以下設定：

- **預設工單類型** 會定義建立工單時的標準設定。  
- **預防性工單類型** 會定義從維護計畫建立工單時使用的工單類型。 若此欄位保持空白，則會使用 **預設工單類型** 欄位的工單類型。  
- 在 **相關工單遮罩** 欄位中，您能定義可與工單相關聯的工單數量上限。 例如，## 可讓您擁有最多 99 個相關的工單。 若您在此定義遮罩，則相關工單會依 [相關聯工單識別碼]-01、-02、-03 (以此類推) 編號。 若未於此欄位定義遮罩，則相關工單會依序取得下一個工單識別碼。  
- **複製錯誤** 選取 **是**，即可將維護要求上登記的錯誤自動複製到相關工單。 
- 在 **層級** 欄位，您可定義會自動插入工單的功能位置層級，前提是所有相關工單作業皆參照相同的功能位置。 若並非所有工單作業皆參照所定義層級的相同功能位置，則工單上的 **功能位置** 欄位會保持空白。 例如，若此欄位插入數字「1」，這代表功能位置結構中的最上層。 若此欄位插入數字「0」，代表您未定義特定功能位置層級，但工單上的所有工單作業都必須與相同功能位置相關，該功能位置才會新增至工單。  
- 工單耗用過帳使用的日記帳可於 **一般** FastTab 內的 **工時**、**項目** 和 **費用** 欄位選取。  
- 在 **產品語言來源** 欄位中，選取資產管理報告產品名稱使用的語言。 您可選取公司帳戶上設定的語言，或目前登錄使用者設定的語言。  
- **即時更新** 選取 **是**，即可自動更新作業類型預設值、維護計畫和維護回合的變更。
  - 若選取 **否**，則資產管理內的作業類型預設值、維護計畫和維護回合的變更就不會自動更新。
  - 以下情形請選取 **否**：正同步大量資料、維護計畫或維護回合設定許多功能位置，或有大量維護計畫或維護回合。  
  - 若您變更作業類型預設值或維護計劃或維護回合，且即時更新選取 **否**，則這些變更影響以下事項時可能不會出現警告：
    - 維護計畫或回合的功能位置設定  
    - 維護計畫或回合的物件設定  
    - 維護計畫設定  
    - 維護回合設定  
- 在 **類別** FastTab 中，可定義與工單耗用相關的預設類別。  

## <a name="the-work-order-scheduling-tab"></a>工單排程索引標籤

**一般** FastTab 上的 **工單排程** 索引標籤提供以下設定：

- **排程時間柵欄** 會定義工單作業規劃的天數，從工單的預期開始日期算起。  
- **主計劃** 會牽涉 **組織管理** 模組內的資源。 若此欄位選取主計劃，您可檢視 **產能預留** (**組織管理** > **資源** > **資源** > 選取資源 > **資源** 索引標籤 > **產能預留** 按鈕) 內工單相關的產能預留。 若此欄位保持空白，您可檢視 **產能負載** (**組織管理** \> **資源** \> **資源** \> 選取資源 \> **資源** 索引標籤 \> **產能負載** 按鈕) 內工單相關的產能負載。  

>[!NOTE]
>**資產管理** 模組內使用主計劃的選擇，以及取得產能預留或產能負載概觀的相關表單，皆為標準設定。 依據您於 **主計劃** 欄位的設定，您將能在 **組織管理** 模組內的 **產能預留** 或 **產能負載** 內存取產能資訊。 您無法設定在兩種檢視內皆呈現產能預留。  

下列清單描述的欄位皆與工單排程期間計算工單優先順序使用的評等分數計算相關。

- **優先順序** - 連同 **重要性** 與 **開始日期** 欄位內評等分數同時計算的評等分數。 此欄位的數字會除以工單上 **優先順序** 欄位內的數字。 例如，若此欄位插入值「5.00」，且工單的優先順序為「20」，則優先順序的評等分數為 0.25。  
- **重要性** - 連同 **優先順序** 與 **開始日期** 欄位內評等分數同時計算的評等分數。 此欄位的數字會乘以工單上 **重要性** 欄位內的數字。 例如，若此欄位插入值「10.00」，且工單的重要性為「5」，則重要性的評等分數為 50。  
- **開始日期** - 連同 **優先順序** 與 **重要性** 欄位內評等分數同時計算的評等分數。 此欄位為以負值表示的每日分數，會比對工單上的 **預期開始日期** 欄位。 例如，若此欄位插入值「10.00」，且工單預期開始日期為三天後，則評等結果為負 30.00。 與上述範例中 **優先順序** 和 **重要性** 欄位結果的 0.25 和 50 相加，總和就是 20.25。 所有工單的評等分數在工單排程期間都會彼此比較，評等分數最高者會優先規劃。  
- **負責工作人員** - 連同 **負責工作人員群組**、**偏好工作人員**、**偏好工作人員群組**、**資產位置** 和 **開始日期** 評等分數值同時計算的評等分數。 若此欄位插入值「50.00」，且工單已選取負責工作人員，則此工作人員在工單排程期間的整體工作人員計算會獲得 50 分。  
- **負責工作人員群組** - 連同 **負責工作人員**、**偏好工作人員**、**偏好工作人員群組**、**資產位置** 和 **開始日期** 評等分數值同時計算的評等分數。 若此欄位插入值「50.00」，且工單已選取負責工作人員，則此工作人員在工單排程期間的整體工作人員計算會獲得 50 分。  
- **僅限於負責的** - 這會限制工單排程可使用的工作人員數量。 選取 **否**，即可計算所有工作人員的分數，不論他們的設定是否為負責工作人員或負責工作人員群組的一員。 選取 **是**，即可計算工單上設為負責工作人員的工作人員的分數，和/或工單上納入負責工作人員群組的工作人員的分數。  
- **偏好工作人員** - 連同 **負責工作人員**、**偏好工作人員**、**偏好工作人員群組**、**資產位置** 和 **開始日期** 評等分數值同時計算的評等分數。 這四個評等分數計算後相加取得的分數，即可在工單排程期間，用於選取哪個工作人員應指派哪項工作。 若此欄位插入值「10.00」，且工單已選取偏好工作人員，則該工作人員在工單排程期間的整體工作人員計算會獲得 10 分。  
- **偏好工作人員群組** - 連同 **負責工作人員**、**偏好工作人員**、**偏好工作人員群組**、**資產位置** 和 **開始日期** 評等分數值同時計算的評等分數。 若此欄位插入值「10.00」，且一名工作人員已指派至工單選取的偏好工作人員群組，則該工作人員在工單排程期間的整體工作人員計算會獲得 10 分。  
- **僅限於偏好** - 這會限制工單排程可使用的工作人員數量。 選取 **否**，即可計算所有工作人員的分數，不論他們的設定是否為偏好工作人員或偏好工作人員群組的一員。 選取 **是**，就只會計算已設為偏好工作人員和/或納入偏好工作人員群組的工作人員的分數。  
- **位置** - 連同 **負責工作人員**、**偏好工作人員**、**偏好工作人員群組**、**資產位置** 和 **開始日期** 評等分數值同時計算的評等分數。 若此欄位插入值「3,000.00」，只要工作人員的處理站或設施與作業排程上的資產位置相同，則該工作人員的計算可獲得 3,000 分。  
  - 如果公司使用功能位置，且工作人員位於與資產相關的功能位置，則這些工作人員將獲得滿分。 如果資產的功能位置具有上層資產，則該功能位置的工作人員將獲得 1/2 分數。 如果該位置也有上層，則該位置的工作人員將獲得 1/3 分數。 如果該位置也有上層，則該位置的工作人員將獲得 1/4 分數，以此類推。  
  - 如果公司使用資產位置 (不建議使用)，則會使用位置、地區和區域來計算位置分數。 若工作人員的位置與相關資產的位置、地區和區域相同，則他們會獲得滿分。 如果工作人員位置僅與位置和區域相符，則該工作人員的評等分數為滿分的 2/3。 如果工作人員位置僅與位置相符，則該工作人員的評等分數為滿分的 1/3。  
- **僅限於位置** - 這會限制工單排程可使用的工作人員數量。 選取 **否**，即可計算所有功能位置上所有工作人員的分數。 選取 **是**，則只會計算與工單功能位置相關聯的工作人員分數。

>[!NOTE]
>這三個「僅限於」欄位會限制須計算分數的工作人員數量，進而加速工單排程。

**工作人員開始日期** - 連同 **負責工作人員**、**偏好工作人員**、**偏好工作人員群組**、**資產位置** 和 **開始日期** 評等分數值同時計算的評等分數。 此欄位為以負值表示的每日分數，會比對工單上的 **預期開始日期** 欄位。 若此欄位插入值「10.00」，且工單預期開始日期為明天，則評等結果為負 10.00。

  - 假設欲排程工單並未選取負責工作人員和負責工作人員群組 - 您可加減評等分數值，例如上述範例的 **偏好工作人員**、**偏好工作人員群組**、**資產位置** 和 **開始日期** 欄位，總分就是 3,010.00。 這代表已選為偏好工作人員並納入工單偏好工作人員群組的工作人員，會獲得高分，而且該工作人員所在的設施也與欲排程作業的資產位置相同。 這代表看中的工作人員將很有機會在工單排程期間，獲選為完成此作業的人員。  
  - 若上述八個欄位其中之一的值為「0.00」，則工單排程期間將不會使用評等分數。  

## <a name="the-document-types-tab"></a>文件類型索引標籤

選取工單報告附件列印應可用的文件類型。 於 **可用** 區段選取文件類型，並選取![向前箭頭](media/15-setup-for-objects.png)即可。 若想移除所選文件類型，請於 **已選** 區段選取該文件類型，並選取![向後箭頭](media/16-setup-for-objects.png)。

## <a name="the-number-sequences-tab"></a>編號序列索引標籤

在此區塊選取需要的編號序列。 資產有兩種編號序列：一種適用於手動建立的資產，另一種適用於擱置中資產建立的資產。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
