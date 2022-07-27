---
title: 檢視工作流程歷程記錄
description: 本主題描述查看已送出到工作流程系統進行處理和核准的文件狀態的步驟。
author: jasongre
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ca9a8bff246cc878a0703947a7f8c1c4fc01963
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460185"
---
# <a name="view-workflow-history"></a>檢視工作流程歷程記錄

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

本主題描述查看已送出到工作流程系統進行處理和核准的文件狀態的步驟。 用來建立此程序的示範資料公司為 USMF。

1. 進入 **瀏覽窗格 > 模組 > 常用 > 查詢 > 工作流程 > 工作流程歷程記錄**。
    - 使用此表單查看已送出到工作流程系統進行處理和核准的文件的狀態。  
    - **執行個體識別碼** 是正在處理或已處理文件之工作流程執行個體的識別碼。  
    - 該 **狀態** 是文件的工作流程狀態。  
    - **工作流程識別碼** 是正在處理或已處理文件之工作流程的識別碼。  
    - 該 **文件** 是文件的識別碼。  
    - 該 **檔案類型** 是送出處理的文件類型。  
    - **工作流程** 是正在處理或已處理文件之工作流程的名稱。  
    - 該 **版本** 是正在處理或已處理文件之工作流程的版本號碼。  
    - **建立日期和時間** 是送出文件的日期和時間。  
    - **經過時間** 是自檔案送出以來經過的時間。  
    - **恢復** 按鈕允許您恢復所選文件的工作流程。  
    - 該 **重新叫用** 按鈕允許您調用選定的文件，使其不被處理。   
2. 請在清單選取所需資料列的連結。
    - 確保已擴展 **工作項目** 區塊。 在此區塊中，您可以查看與所選文件關聯的工作項。 例如，可能必須完成一項工作，或者可能必須核准文件。  
    - **重新指派** 按鈕將打開一個對話方塊，您可以在其中將工作項重新指派給另一個使用者。  
    - 確保已擴展 **追蹤詳情** 區塊。 在此區塊中，您可以查看所選文件的工作流程歷程記錄。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]