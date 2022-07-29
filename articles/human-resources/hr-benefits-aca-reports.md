---
title: 產生平價醫療法案 (ACA) 報告
description: 平價醫療法案 (ACA) 報告產生 1095-B 和 1095-C 表單，作為支援平價醫療法案的 **雇主授權** 部份。
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c8f336e31e77391ef7e2bc2dca901e6a78fbb914
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452295"
---
# <a name="generate-aca-reports"></a>產生 ACA 報告


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

平價醫療法案 (ACA) 報告產生 1095-B 和 1095-C 表單，作為支援平價醫療法案的 **雇主授權** 部份。

> [!NOTE]
> ACA 報告只針對美國的法人實體啟用。

## <a name="getting-started"></a>開始使用

若要追蹤 1095-B 和 1095-C 表單資訊，您必須先建立一個或多個平價醫療承保範疇群組。 平價醫療承保範疇群組指出：

- 公司為員工投保的承保範疇
- 如果成本高於聯邦貧窮線，員工須分攤的最低月保費成本
- 雇主依適用情況使用的安全港條款

平價醫療承保範疇群組允許您管理這些欄位資訊，不必變更條件相同的每位員工記錄。 您可以使用本頁面的 **大量指派** 選項輕鬆指派平價醫療承保範疇群組給一名或多名員工。

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>維護承保範疇群組的多版本

您可以維護任何承保範疇群組的多版本。 本項功能允許您變更，不必建立新群組並指派投保的員工。 

待您建立 ACA 承保範疇群組後，您就能使用 **大量指派** 選項大量指派群組給員工。 您也可以個別指出是否追蹤和回報 ACA 資訊，並將員工指派給平價醫療承保範疇群組。

您不需要追蹤某些 ACA 承保範疇資訊，例如兼職員工。 此時請設定 **回報承保範疇** 欄位為 **否**。 雖然您必須使用可追蹤的 ACA 資訊指派每位員工給平價醫療承保範疇群組，但您仍然可以使用不同值變更下列月份選項：

- **承保範疇的投保**
- **員工分攤成本**
- **安全港條款**

若要輸入平價醫療承保範疇群組值的例外狀況，請在 **就業索引標籤** 上的 **額外資訊** 區段下方，**背景工作角色細節** 頁面上選取 **平價醫療承保範疇** 連結。

## <a name="reporting-health-care-coverage"></a>回報醫療保健承保範疇

除了追蹤為全職員工投保的醫療保健以外，如果雇主為已經登記的員工投保雇主贊助的自行投保醫療保健 (不管他們的就業狀態是全職或兼職)，額外資訊需要在 1095-C 上回報。 雇主贊助的福利計劃所涵蓋的每位員工 (包括家屬) 都必須納入涵蓋他們的月報告。 

您可以選取 **ACA 可回報** 勾選方塊指出每項福利計劃是否必須回報。

此外，如果員工已經選擇讓他們的任何家屬納入承保範疇，您可以在 **維護福利** 頁面上指出每個員工家屬投保日期。 若要指出家屬納入福利範圍內，請選取 **家屬** 快速索引標籤的動作窗格中的 **編輯** 按鈕。

您可以在 **家屬承保範疇日期管理工具** 頁面上指示家屬納入福利計劃涵蓋的日期。 在本頁面上輸入日期將自動選取 **維護福利** 頁面上的 **承保範圍** 勾選方塊。

## <a name="generate-1095-b-and-1095-c-forms"></a>產生 1095-B 和 1095-C 表單

您也可以從產品產生 1095-B 和 1095-C 表單分派給您的每位員工。 本系統也可以產生 1095-C 電子表單和 1094-C IRS 已傳輸檔案。  

產生 1095-C 表單時，請輸入適當的課稅年份並指出是否應該遮罩社會安全號碼。 如果您為 500 多名員工列印 1095-C 表單，您將收到多個 PDF 檔案。 建議您在 **文件管理參數** 視窗中將 **最大檔案大小** 增加到 150 MB。

## <a name="viewing-information"></a>檢視資訊

您可以使用 **背景工作角色平價醫療承保範疇** 頁面查看已指派給每個承保範疇群組的員工、不需要納入報告的員工以及尚未指派的員工。

如果平價醫療承保範疇群組的任何預設值已經被覆寫，則變改值旁邊將出現星號。 如果所有 12 個月的值都相同且並未被覆寫，則此值將會列印在 **全部 12 個月** 欄位。

您也可以使用查詢視窗了解已經標記為非 ACA 回報的員工。 您不需要追蹤是否為他們依承保範疇投保，也不需要在年底簽發 1095-C 給他們。 請在 **篩選條件** 欄位中選取 **非 ACA 回報**，以產生將不會收到 1095-C 表單的所有員工清單。

此外，您可以檢視尚未指派的員工 (**ACA 回報承保範疇** 欄位空白) 或指派給平價醫療承保範疇群組，在 **年份** 欄位中選取到期年份的員工。

您可以將使用任何篩選條件選項所產生的員工清單匯出到 Excel。

如果您因為提供自行投保的承保範疇而需要回報被保人，您可以檢視涵蓋於福利計劃之中，並且標記為 **ACA 可回報** 的任何家屬。 請在動作窗格上 **檢視家屬承保範疇**。

> [!NOTE]
> 只有標記為 **ACA 可回報** 的福利計劃才會顯示在查詢視窗內。


[!INCLUDE[footer-include](../includes/footer-banner.md)]