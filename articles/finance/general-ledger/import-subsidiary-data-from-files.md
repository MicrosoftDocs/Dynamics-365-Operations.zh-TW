---
title: 從檔案匯入子公司資料
description: 本主題說明如何從外部系統準備資料匯入 Microsoft Dynamics 365 Finance。
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 4be1e748724331c4e2089da8a08a9ac7e5cf88a2ac6d3d89b37b9fcd4480f516
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450258"
---
# <a name="import-subsidiary-data-from-files"></a>從檔案匯入子公司資料

[!include [banner](../includes/banner.md)]

本主題說明如何從外部系統準備資料匯入 Microsoft Dynamics 365 Finance。 您使用 **合併匯入** 頁 (**合併\>合併匯入**) 準備從外部系統傳輸子公司資料。

1. 針對合併建立子公司法人實體。 有關如何創建法人實體的資訊，請參閱[建立法人實體](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md)。 有關詳細資訊，請參閱[準備在合併過程中使用的法人實體](prepare-company-for-consolidation.md)和[為合併設立子公司法人實體](set-up-subsidiary-company-for-consolidation.md).

2. 準備將包含匯入資料的檔案。 更多有關資料匯入流程的資訊，請參閱[資料匯入和匯出工作概觀](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)。
3. 按照[資料匯入和匯出工作概觀](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)中的 "資料匯入/匯出流程" 步驟匯出資料到檔案。 您可以使用該程序合併另一個 Dynamics 365 Finance 執行個體資料或 Dynamics 365 Business Central 的資料。 如果您從外部系統匯入資料，資料必須採用[匯出子公司資料到檔案](export-subsidiary-data-to-file.md)描述的格式。
4. 前往 **合併\>合併匯入**。 請在 **合併匯入** 頁的 **標準** 索引標籤設定下列欄位，指明報表與/或匯入細節。

    | 欄位                                 | 報表值 | 匯入值 |
    |---------------------------------------|----------------------|----------------------|
    | 描述                           | 不適用 | 輸入說明辨別匯入。 |
    | 主科目                          | 定義報表應包括的科目範圍。 如果您不定義範圍，將包括所有科目。 | 定義匯入應包括的科目範圍。 如果您不定義範圍，將包括所有科目。 |
    | 合併期間                  | 定義預計合併的日期範圍。 | 定義預計合併的日期範圍。 |
    | 包括實際金額                | 設定本選項為 **是** 以便包括實際值。 | 設定本選項為 **是** 以便包括實際值。 |
    | 包括預算金額                | 設定本選項為 **是** 以便在合併中包括預算金額。 | 設定本選項為 **是** 以便在合併中包括預算金額。 |
    | 合併期間重建餘額 | 如果重建流程應該完全清除餘額和新記錄，並從頭開始重建餘額，請設定本選項為 **是**。 | 如果重建流程應該完全清除餘額和新記錄，並從頭開始重建餘額，請設定本選項為 **是**。 |
    | 預算模型                         | 不適用 | 如果您選取匯入預算金額，請輸入預計合併的預算模型。 |
    | 預算費率類型                      | 不適用 | 輸入預算匯率類型。 |

6. 如果您的會計貨幣不同，請使用 **貨幣換算** 索引標籤配置合併期間已經完成的換算。

    | 欄位                      | 描述 |
    |----------------------------|-------------|
    | 來源法人實體        | 選取您正匯入的法人實體。 |
    | 來源會計貨幣 | 此預設貨幣是與您在 **來源法人實體** 欄位選取的來源法人實體相關聯。 |
    | 來源科目和目標科目       | 定義從來源法人實體匯入的科目範圍。 |
    | 匯率類型         | 選取匯率類型。 建立主科目時會指派匯率類型。 更多資訊，請參閱[建立主科目](tasks/create-main-account.md)。 |
    | 套用匯率來源   | 輸入日期以便套用該日期生效的匯率。 或者，輸入應當成匯率的值。 |
    | 匯率              | 預設值取決於您在 **匯率類型** 欄位選取的匯率類型。 如果您輸入使用者定義的匯率，您可以自行定義匯率。 |

7. 設定 **背景執行** 選項為 **是**，使匯入流程在背景執行。
8. 設定 **批次處理** 選項為 **是**，以便在特定時間將合併當作批次工作執行。 若要立即執行合併，選取 **確定**。 

指定用來合併子公司的交易和餘額將新增到合併法人實體的適當科目。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]