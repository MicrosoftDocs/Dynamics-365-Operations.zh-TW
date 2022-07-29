---
title: 福利結算表
description: 福利結算表報告說明員工目前已註冊的福利項目。
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 602e4f9459aac8fdbea5f2752e51cc2c1b71360c
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2022
ms.locfileid: "8452697"
---
# <a name="benefit-statement"></a>福利結算表


[!INCLUDE [PEAP](../includes/peap-2.md)]

**福利結算表** 報告提供員工目前已註冊的福利結算表。 員工可以直接存取報告或由福利管理員存取。 **福利結算表** 提供員工已註冊的福利、涵蓋選項、成本和任何已註冊的家屬或受益人清單。 結算表可針對單名或多名背景工作角色列印。

> [!NOTE]
**福利結算表** 功能必須在 **功能管理** 工作區啟用。 為了做到這一點，**福利管理** 功能必須在功能管理中開啟。 


## <a name="importing-the-benefit-statement"></a>匯入福利結算表 

您必須在 **福利結算表** 開放使用之前先使用報表組態匯入 **福利結算表**。 若要做到這一點，請完成下列步驟：

1.  前往 **系統管理** 工作區。

2.  選取 **電子報表** 圖格。

3.  前往 **組態提供者** 並選取 **儲存庫**。

  ![儲存庫的選取。](https://user-images.githubusercontent.com/26801678/134203290-7faf7245-ed08-44e9-95a1-a7ba278c42c6.png)

4.  從清單選取 **人力資源**，然後選取 **打開**。

    ![組態儲存庫。](https://user-images.githubusercontent.com/26801678/134203619-b3fd087d-1fe9-45ef-a588-1afedfe38dfd.png)

5.  請選取左窗格的 **福利結算表模型** 並且展開，以便顯示 **福利結算表格式**。

6.  請選取左窗格的 **福利結算表格式**。

7.  螢幕畫面右側將有 **版本** FastTab。 選取 **匯入**。

    ![版本 FastTab。](https://user-images.githubusercontent.com/26801678/134203763-f12ef549-e326-400d-ac69-b25fc94af47b.png)

## <a name="generate-the-benefit-statement-as-a-pdf-file"></a>將福利結算表產生為 PDF 檔案

預設情況下，**福利結算表** 將列印成 Microsoft Word 文件。 若要以 PDF 格式列印，您將必須在 **電子報表目的地** 配置 PDF 選項。 

1. 為此，請前往 **系統管理工作區** > **電子報表** > **相關連結** > **電子報表目的地**。

1.  選取 **新增**。

2.  請在 **參考** 欄位中選取 **福利結算表格式**。

3.  請在 **檔案目的地** FastTab 上選尿 **新增**。

4.  請在 **名稱** 欄位中輸入 **福利結算表 PDF**。

5.  請在 **檔案組成部份名稱** 欄位中，選取 **福利結算表**。

6.  請選取 **轉換到 PDF** 勾選方塊。

7.  請從選單項目選取 **設定**。 

    ![檔案目的地。](https://user-images.githubusercontent.com/26801678/134203881-a3f1ebc3-d816-485d-a53b-026cc29cae64.png)

8.  請選取 **檔案** FastTab，然後選取 **已啟用**。

9.  選取 **確定**。
   
> [!NOTE]
> 福利管理功能在預覽狀態。 使用 **電子報表目的地** 報告的電子郵件目的地設定預期會出現問題。 您可能會收到一則錯誤訊息，並且電子郵件將無法傳送。

**福利結算表** 可以從下列頁面產生：

-   **福利管理工作區** > **連結** > **報告** > **福利結算表**

-   **員工 (舊版表單)** > **個人資訊索引標籤** > **福利結算表**

-   **簡化員工輸入** > **福利報告** > **福利結算表**

-   **員工自助服務** > **福利** > **檢視福利結算表**

> [!NOTE]
>  存取 **員工自助服務** 的 **福利結算表** 功能是由 **檢視福利結算表** 權限控制。 這是根據 **員工自助服務福利** 職責訂定。 此項權限預設情況下會授予員工。

## <a name="report-contents"></a>報告內容

**福利結算表** 將列印員工確認的計劃選取項目，包括任何棄權的計劃。 下圖顯示本報告範例。 

![福利結算表報告。](https://user-images.githubusercontent.com/26801678/134204058-61baa318-fede-4795-a256-acdf3217f9f9.png)

報告將顯示 **計劃**、**涵蓋選項**、**員工成本** 和 **雇主成本**。 報告也將列出所有涵蓋的家屬。 如果計劃有關聯受益人，則將顯示受益人及其分配優先順序和佔比。

**福利結算表** 報表可以同時使用 **福利結算表** 頁面上的 **預計包括的記錄** FastTab，列印多名員工的報告。
