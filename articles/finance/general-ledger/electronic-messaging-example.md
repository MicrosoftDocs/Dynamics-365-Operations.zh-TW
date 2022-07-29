---
title: 設定並執行處理以叫用簡單的匯出 ER 格式以生成 Excel 報告
description: 本主題提供了一個範例，說明如何設定和使用電子訊息。
author: liza-golub
ms.date: 07/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a5fd466c98e0855f7a33929eeee42b9147d26ba19780b4ae7c8eb895ac27ea5e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450393"
---
# <a name="set-up-and-run-processing-to-call-a-simple-exporting-er-format-to-generate-an-excel-report"></a>設定並執行處理以叫用簡單的匯出 ER 格式以生成 Excel 報告

[!include [banner](../includes/banner.md)]

建立 ER 格式並將其對應到資料來源並完成後，您可以從 **電子報告** 工作區執行它。 報告生成後，您可以將其保存在本地。

若要控制報告程序的下列方面，請設定電子郵件處理：

- 記錄報告生成者的相關資訊。
- 報告生成時間的紀錄資訊。
- 保存為以前期間生成的報告。

以下示例顯示如何設定電子郵件以生成基於 Microsoft Excel 的匯出 ER 格式的報告。 如果要遵循此範例，必須已建立 Excel 的匯出 ER 格式，並對應到資料來源並完成。 此外，必須已經為電子訊息設定了編號規則。

建立處理時，首先定義將要設定的處理動作和狀態會很有幫助。 下圖顯示了此範例的處理程序。

![處理方案](media/processing-scheme.png)

## <a name="create-message-statuses"></a>建立訊息狀態

1. 前往 **稅務** \> **設置** \> **電子訊息** \> **訊息狀態**。
2. 建立下列訊息狀態：

    - 新產品
    - 已準備
    - 產生

    ![訊息狀態](media/message-statuses.png)

3. 在 **全新** 狀態行上，選擇 **允許刪除** 核取方塊，以允許使用者刪除具有此狀態的訊息。

## <a name="create-additional-fields"></a>建立其他欄位

1. 前往 **稅務** \> **設置** \> **電子訊息** \> **額外欄位**。
2. 新增一個額外欄位及其值。
3. 將 **使用者編輯** 選項設定為 **Yes** 以允許使用者編輯該欄位。

![其他欄位](media/additional-fields.png)

## <a name="create-message-processing-actions"></a>建立訊息處理動作

對於此範例，您將建立以下訊息處理動作：

- **建立訊息**
- **更新至已準備**
- **產生報表**
- **更新到初始狀態** (可選)

依照下列步驟建立動作。

1. 前往 **稅務** \> **設置** \> **電子訊息** \> **訊息處理動作**。
2. 建立一個名為 **建立訊息** 的動作。 在 **一般** FastTab 的 **動作類型** 欄位中，選擇 **建立訊息**。
3. 建立一個名為 **更新至已準備** 的動作，並設定以下欄位：

    - 在 **一般** FastTab 的 **動作類型** 欄位中，選擇 **訊息級使用者處理**。
    - 在 **初始狀態** FastTab 的 **訊息狀態** 欄位中，選擇 **全新**。
    - 在 **結果狀態** FastTab 的 **訊息狀態** 欄位中，選擇 **已準備**。 在 **反應類型** 欄位中，輸入 **成功執行**。

4. 建立一個名為 **一般報告** 的動作，並設定以下欄位：

    - 在 **一般** FastTab 的 **動作類型** 欄位中，選擇 **電子報告匯出**。 請在 **選擇格式** 對話方塊中選取匯出的格式。 選項有 **Excel**、**XML**、**JSON**、**Text** 和 **Other**。
    - 在 **開始狀態** FastTab 的 **訊息狀態** 欄位中，選擇 **已準備**。
    - 在 **結果狀態** FastTab 的 **訊息狀態** 欄位中，選擇 **已生成**。 在 **反應類型** 欄位中，輸入 **成功執行**。

    ![產生報表動作](media/generate-report-action.png)

5. 選用：若要讓使用者多次重新生成報告，請建立一個名為 **更新至初始狀態** 的動作，並設定以下欄位：

    - 在 **一般** FastTab 的 **動作類型** 欄位中，選擇 **訊息級使用者處理**。
    - 在 **初始狀態** FastTab 的 **訊息狀態** 欄位中，選擇 **已生成**。
    - 在 **結果狀態** FastTab 上，為兩種訊息狀態 (**已準備** 和 **全新**) 中的每一種新增單獨的行。 針對兩行，均將 **反應類型** 欄位設定為 **成功執行**。

## <a name="electronic-message-processing"></a>電子訊息處理

針對此範例，應設定所有動作以便它們單獨執行。 假設使用者將初始化每個動作。

1. 前往 **稅務** \> **設置** \> **電子訊息** \> **電子訊息處理**。
2. 為您的處理新增一則記錄，並新增所有先前定義的動作和一個附加欄位。
3. 選用：在 **資訊安全角色** FastTab 上，為您的處理定義資訊安全角色，以限制對特定報告的存取。
4. 前往 **稅務** \> **查詢和回報** \> **電子訊息** \> **電子訊息**。
5. 選取 **新增** 以建立訊息。 此時，您可以新增日期和描述。 您也可以根據需要更新附加欄位的值。

    ![正在建立電子訊息](media/create-electronic-message.png)

    **動作紀錄** FastTab 上的網格會自動填充對訊息執行的所有動作的紀錄。

    您現在可以刪除或更新訊息狀態。 

6. 若要更新訊息狀態，請選擇 **更新狀態**。 在 **全新狀態** 欄位中，選擇 **已準備**，然後選擇 **OK**。

    ![正在更新訊息狀態](media/update-status.png)

    訊息狀態更新為 **已準備**。

7. 現在選取 **生成報表** 來生成報表。

    生成報告，並更新訊息狀態和操動作紀錄。

8. 若要查看生成的報告，請選擇頁面右上角的 **附件** 按鈕 (迴紋針符號)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
