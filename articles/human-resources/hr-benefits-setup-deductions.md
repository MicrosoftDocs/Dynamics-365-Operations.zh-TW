---
title: 配置扣除額
description: 在 Microsoft Dynamics 365 Human Resources 中使用扣除額功能判定從員工薪水扣除每項福利的金額 (如果有)。
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf7ddbfb8717c0311fab7388f346f03618a7b43d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452166"
---
# <a name="configure-deductions"></a>配置扣除額


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

在 Microsoft Dynamics 365 Human Resources 中使用扣除額功能判定從員工薪水扣除每項福利的金額 (如果有)。 扣除額是有生效日期的，因此您可以保留扣除額資訊的歷史記錄。 

1. 請在 **設定** 下方的 **福利管理** 工作區選取 **扣除額**。

2. 選取 **新增**。

3. 請指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **扣除額**  | 用來標別福利扣除額的唯一識別碼。 |
   | **描述** | 扣除額說明。 |
   | **生效** | 開始日期。 預設值為目前的系統日期。 |
   | **到期** | 結束日期。 預設值為 12/31/2154，代表從未發生。 |
   | **標題** | 處理工資單福利時，此扣除額將用於員工扣除額部分的工資單系統標題代碼。 這在您使用第三方工資單提供商時使用。 |
   | **員工工資單扣除額參考** | 處理工資單福利時，此扣除額將用於員工扣除額部分的工資單系統扣除額代碼。 |
   | **金額標題** | 處理工資單福利時，此扣除金額將用於員工扣除額部分的工資單系統標題代碼。 這一般在您使用第三方工資單提供商時使用。 |
   | **可以刪除** | 指定從 Dynamics 365 for Finance and Operations 的匯出值是否會造成工資單系統刪除此值。 |
   | **配對欄位** | 指定是否將相鄰配對欄位的標題和扣除金額匯出到工資單系統。 |
   | **變更生效日期** | 福利扣除額變更生效日期。 本日期當天，福利扣除額變更且其相關所有福利計劃皆會更新，只要您執行 **扣除額變更更新** 處理。 |
   | **扣除額變更完成** | 一旦福利扣除額變更經由扣除額更新變更處理完成，將自動選取 **扣除額變更完成** 勾選方塊。 |
   
4. 若要追蹤和維護對福利費率設定的變更，請選取 **動作** 和 **維護版本**。

5. 選取 **儲存**。 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
