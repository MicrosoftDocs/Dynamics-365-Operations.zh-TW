---
title: 時間及出勤登記概覽
description: 時間登記工作者可以輸入不同類型的時間登記，例如，打卡上班、打卡下班、登記間接活動和缺勤登記。 本主題介紹登記、計算、核准，並使用工作流程將結構和自動核准加入核准時間表的過程中。
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, JmgCalcApprovePickDialog, JmgGroupApprove, JmgGroupCalc, JmgGroupSigningTable, JmgRegistration, JmgTimeCalcParmeters, WorkflowTableListPageRnr, JmgRegistrationSetup, JmgStampTrans, JmgStampJournalTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "53351"
- intro-internal
ms.assetid: 885b0cdf-53d7-4cb4-92fe-da1b9e32b39f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: af257427661cb9a0d976800b657d3eb4afe7feca
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449772"
---
# <a name="time-and-attendance-registration-overview"></a>時間及出勤登記概覽

[!include [banner](../includes/banner.md)]

時間登記工作者可以輸入不同類型的時間登記，例如，打卡上班、打卡下班、登記間接活動和缺勤登記。 本主題介紹登記、計算、核准，並使用工作流程將結構和自動核准加入核准時間表的過程中。

## <a name="registrations"></a>登記

在使用時間和出勤的公司中，員工必須登記他們在工作上花費的時間以及他們的出勤率。 某些公司可能只會要求員工登記打卡上班和打卡下班時間。 在其他公司，可能還會要求員工記錄他們執行的實際活動以及休息時間的時間消耗。 時間及出勤的目標使用者是：

- 需要定期 (例如每天、每週或每兩週) 登記時間和出勤的員工。
- 負責計算、核准和轉移員工登記以供進一步處理的主管、經理和薪資官員。

| **附註**                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 如果您將時間和出勤與製造執行一起執行，則將記錄專案、專案活動、間接活動、缺勤代碼以及加班和彈性時間的所有登記，並用於計算兩個模組中的工資單。 |

## <a name="time-registrations-workers"></a>時間登記員工

為了能夠登記時間和缺勤，必須將員工設定為他們所僱用的公司的時間登記員工。

設定後，工作人員可以輸入不同類型的登記。

- 上下班時打卡上班和打卡下班。
- 生產工作的時間和品項消耗。
- 如果機器已被定義為資源，則為車間機器上使用的時間。

| **附註**                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 如果員工在開始生產作業時選擇作為機器的助手工作，則可以自動為員工分配在車間特定機器上進行的時間登記。 |

- 專案和項專案動的時間登記。
- 透過相應的專案費用日記帳和專案品項日記帳登記專案費用和品項消耗。
- 計畫性缺勤。
- 上班遲到或比計劃提前離開時缺勤。
- 工作休息、人工登記或系統自動計算。
- 間接活動，就是員工在工作日可能從事的非生產性活動。 這些活動的範例包括開會或打掃他們的工作空間。
- 加班，可以登記為加班、彈性工作時間或加班。

## <a name="adding-clock-out-registrations"></a>新增打卡下班登記

如果工作人員在工作日結束時忘記打卡，則可以通過執行批次處理作業來新增遺失的登記。 系統會根據員工關聯的檔案比較打卡上班和下班時間，並自動插入缺少的打卡登記以匹配檔案的結束時間。 打卡上班和打卡下班登記對於時間登記的後續計算和核准至關重要，然後才能轉移到工資單。

## <a name="calculating-registrations"></a>計算登記

當為登記工作人員分配一個通常與特定團隊、班次或工作組相關的計算群組時。 團隊經理或主管通常會驗證員工所做的登記，因此也會是負責每天為各計算群組執行計算的人。 作為計算過程的一部分，團隊經理或主管能夠：

- 更正錯誤的登記。 例如，變更開關代碼並調整生產作業的反饋。
- 加入缺少的登記。 例如，建立打卡下班登記和缺勤交易。
- 刪除不正確的登記。

因為在計算登記之前登記時間必須與工作人員的時間設定檔相匹配，所以您必須覆蓋對其標準工作時間設定檔有例外的任何員工的工作時間設定檔。 如果員工設定檔是日班，並且員工已同意上夜班而沒有加班費，則團隊經理或主管必須覆蓋預設員工資料，以便按標準夜班費率計算工作時間而非加班。 如果缺少缺勤登記，計算也會顯示錯誤。 必須在計算完成新增。

## <a name="approving-registrations"></a>核准登記

正如您將計算群組分配給時間登記工作人員一樣，您也必須分配一個核准群組。 通常，該群組將屬於特定團隊、班次或工作群組。 您必須核准正確計算的時間登記——這代表在沒有錯誤的情況下進行計算——然後才能生成支付項目，然後才能將其傳輸到工資系統。 工資單管理員通常會核准登記，在核准之前，他們可以：

- 推翻個別員工的工資合約。
- 新增手動保費。
- 輸入缺勤登記的相關附加資訊。

| **附註**                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 如果已經計算了特定員工的加班時間，則可以將加班時間分配給白天的特定工作。 如果工作成本是根據員工工資計算，則這是相關的內容。 |

## <a name="approving-registrations-using-workflow"></a>使用工作流程核准登記

您可以設定工作流程核准程序，自動核准符合工作流程規則的登記，只留下手動處理的偏差。 如果啟動了工作流程核准，則團隊經理或主管提交計算的登記以供審核。 工作流程程序將生成適當的核准和任務，然後將它們分配給工作流程中確定的正確使用者和角色。 時間和出勤有兩個工作流程核准。

| 工作流程                                  | 目的                                                                                                   | 登記類型                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 時間及出勤天數            | 例如，工作流程會根據當天的預期工作小時數來驗證登記。 |                                                                                                                                                                                                                                                       |
| 時間及出勤日記帳登記 | 工作流程會針對登記日期驗證各種登記類型。                           | 時間和出勤 • 打卡 • 下班 • 缺勤 • 休息 • 切換代碼 • 專案 • 專案活動 • 間接活動生產作業 • 排隊之前 • 設定 • 流程 • 重疊 • 運輸 • 排隊之後 • 開始協助 • 停止協助 |

## <a name="transferring-approved-registrations"></a>轉移核准的登記

核准登記後，您可以將它們轉移到定期工資單工作。 轉移後的登記會過帳到與其相關的活動或作業，例如生產訂單或專案。 根據登記為每個員工生成工資單交易。  

## <a name="reversing-transferred-registrations"></a>撤銷轉移的登記

撤銷交易的任務——收回——可以在工資核算期的工資轉移執行之前完成。 這代表工資單資料已傳輸到外部檔案。 撤銷後，所有登記都將被撤銷，生產訂單或專案上發布的任何交易都會被抵消和廢止。

| **附註**                                                 |
|----------------------------------------------------------|
| 外部檔案可以匯入工資系統。 |

## <a name="registrations-in-electronic-timecards"></a>電子考勤卡登記

工作任務不需要立即反饋的員工 (例如生產工作)，但從事專案活動的員工可以從使用電子考勤卡中受益。 電子考勤卡可讓您靈活地隨時以最適合您的業務日程的方式進行登記 - 每天、每週或當員工離開後再次進入辦公室時。 若要使用電子考勤卡或這些工作人員，您必須在工作人員詳細資訊中指定使用考勤卡。 電子考勤卡能讓員工登記：

- 日期
- 登記類型
- 工作參考，例如專案、間接活動或生產訂單
- 工作識別資訊
- 時間消耗
- 專案費用
- 專案品項

[!INCLUDE[footer-include](../../includes/footer-banner.md)]