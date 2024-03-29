---
title: 建立批次作業
description: 批次處理作業是送出給應用程式物件伺服器 (AOS) 實體以進行自動處理的一組工作。
author: maertenm
ms.date: 11/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76c6c68f7effad0c40282b22ea2a6bf991862cf5
ms.sourcegitcommit: d7d997ad84623ad952672411c0eb6740972ae0b1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/24/2021
ms.locfileid: "8460541"
---
# <a name="create-a-batch-job"></a>建立批次作業

[!include [banner](../../includes/banner.md)]

批次處理作業是送出給應用程式物件伺服器 (AOS) 實體以進行自動處理的一組工作。 批次處理作業使用建立作業的使用者的安全性認證執行。 使用以下程序建立批次處理作業。 用來建立此程序的示範資料公司為 USMF。


## <a name="create-the-batch-job"></a>建立批次處理作業
1. 進入 **瀏覽窗格 > 模組 > 系統管理 > 查詢 > 批次處理作業**。
2. 選取 **新增**。
3. 在 **工作說明書** 欄位中，輸入批次組裡作業的描述。
4. 在 **安排好的開始日期/時間** 欄位中，輸入批次處理作業應執行的日期和時間。
5. 選取 **儲存**。

## <a name="create-a-recurrence"></a>建立週期
1. 在動作窗格上，選取 **批次作業**。
2. 選取 **定期**。 使用這些選項輸入週期和模式。  
3. 選取 **確定**。

## <a name="add-alerts"></a>新增警示
1. 在動作窗格上，選取 **批次作業**。
2. 選取 **警示**。 指示您是否希望在批次處理作業結束、出現錯誤或被取消時發送警示訊息。 然後指定是否要將警示顯示為彈出式訊息。   
3. 選取 **確定**。

## <a name="add-a-task-to-a-batch-job"></a>將工作新增到批次處理作業
1.  在 **批次處理作業** 頁面上，選取 **檢視工作**。
2.  選取 **Ctrl+N** 建立一個工作。
3.  輸入批次工作的描述。
4.  在 **公司帳戶** 欄位中，選取工作應在其中執行的公司資料庫。
5.  在 **類別名稱** 欄位中，選取工作應該執行的流程。 
6.  根據需要為工作選取一個批次組。

    使用者端工作必須指派給批次處理組。 它們會自動指派給預設批次組 (也稱為空白批次組)。

7.  選取 **Ctrl+S** 儲存工作。
8.  若要使所選工作依賴於作業中的另一個工作，請選取 **有條件** 格線，然後針對要定義的每個條件執行以下步驟：

    1. 選取 **Ctrl+N** 建立一個條件。
    2. 選取父系工作的工作識別碼。
    3. 選取父工作必須達到的狀態，從屬工作才能執行。
    4. 選取 **Ctrl+S** 儲存條件。

    如果您定義了多個條件，並且必須滿足 *所有* 條件才能執行相關工作，請選取條件類型 **全部**。 如果在滿足 *任何* 條件後依賴工作可以執行，則選取條件類型為 **任何**。

9.  選取應如何處理工作失敗。 若要忽略特定工作的失敗，請在 **一般** 索引標籤上，為該工作選取 **忽略工作失敗** 選項。 如果選取此選項，工作失敗不會導致作業失敗。 您還可以使用 **最大重試次數** 欄位來指定工作在被視為失敗之前應重試的次數。 作為最佳做法，我們建議您不要將 **最大重試次數** 欄位設定為大於 **5** 的值。

    如需批次處理重試的相關信息，請參閱[啟用批次重試](../retryable-batch.md)。

## <a name="adjust-batch-job-status"></a>調整批次作業狀態
1. 移至 **系統管理 > 查詢 > 批次作業**。
2. 選取適當的批次作業。
3. 在操作窗格上，選取 **批次處理作業 > 函數 > 更改狀態**。
4. 選取適當的狀態：
    - **預留**：將批次處理作業設定為 **預留**，以便從批次處理工作排程器中預留。 相當於 *停止*。
    - **等待中**：將批次處理作業設定為 **等待中**，以便等待批次處理工作排程器獲取。 相當於 *開始*。
5. 選取 **確定**。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
