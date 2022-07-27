---
title: 設定職責隔離
description: 您可以設定規則來分隔必須由不同使用者執行的工作。
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c06ce9325d7b0894ba53d6b9782f495a48280d45e538b048d883ab86f05dabf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460535"
---
# <a name="set-up-segregation-of-duties"></a>設定職責隔離

[!include [banner](../../includes/banner.md)]

您可以設定規則來分隔必須由不同使用者執行的工作。 這個概念被命名為職責隔離。 例如，您可能不希望同一個人確認收據並處理對廠商的付款。 職責隔離可以幫助您降低欺詐風險，還可以幫助您發現錯誤或違規行為。 您還可以使用職責隔離來執行內部控制政策。 完成以下程序以建立規則。 您必須是系統管理員才能完成該程序。

1. 進入 **系統管理** > **安全** > **職責隔離** > **職責隔離規則**。
2. 點選 **新增**。
3. 在 **名稱** 欄位中，輸入規則的值。
4. 在 **第一個職責** 欄位中，點選下拉式按鈕以打開查詢。
5. 在清單中，尋找並選取所需的記錄。 選取受規則控制的第一個職責。
6. 在 **第二個職責** 欄位中，點選下拉式按鈕以打開查詢。 
7. 在清單中，尋找並選取所需的記錄。 選取受規則控制的第二個職責。
10. 在 **嚴重性** 欄位中，選取一個選項。 選取同一使用者或角色同時執行兩項職責時發生的風險的嚴重性。  
11. 在 **安全性風險** 欄位中，輸入一個值。 輸入安全性風險的描述。  
12. 在 **安全性風險降低** 欄位中，輸入一個值。 輸入您為降低安全性風險而採取的動作描述。 例如，您可以透過對流程進行更詳細的審查、每月進行一次管理審查或與其他部門共用資源來降低風險。     
13. 選取 **儲存**。

> [!IMPORTANT] 
> 建立規則時，不會驗證是否符合職責隔離規則。 您可以建立為現有角色建立衝突的規則。 現有的使用者角色指派也可能與新規則發生衝突。 您必須在建立或修改規則後驗證合規性。 如需相關資訊，請參閱[識別和解決職責隔離中的衝突](identify-resolve-conflicts-segregation-duties.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]