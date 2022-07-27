---
title: 啟用時間和出勤的工資單流程
description: 此程序會顯示如何啟用時間和出勤的工資單流程。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3b196e25699c43dbac06e950aae0ad8a9457a8d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447921"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a>啟用時間和出勤的工資單流程

[!include [banner](../../includes/banner.md)]

此程序會顯示如何啟用時間和出勤的工資單流程。 建立此程序的示範資料公司為 USMF。


## <a name="create-a-pay-type-with-a-related-pay-rate"></a>以相關的薪資率建立薪資類型
1. 時間及出勤 > 設定 > 工資單 > 薪資類型
2. 按一下 「New」(新增)。
3. 在 [薪資類型] 欄位中輸入一個值。
4. 在 [描述] 欄位中輸入一個值。
5. 按一下儲存。
6. 按一下 [費率]。
    * 薪資類型的費率是針對特定時間間隔設定的，並且可以為員工建立個別的費率。 並不一定要為時間和出勤中的薪資類型建立費率。 此資訊可能已經存在於用於產生工資的工資單系統中。  
7. 按一下 「New」(新增)。
8. 在清單中，標記所選資料列。
9. 在 [費率] 欄位中，輸入一個數字。
10. 按一下儲存。

## <a name="create-a-pay-agreement"></a>建立薪資合約
1. 關閉頁面。
2. 關閉頁面。
3. 移至薪資合約。
    * 時間及出勤 > 設定 > 薪資合約  
4. 按一下 「New」(新增)。
5. 在 [薪資合約] 欄位中輸入一個值。
6. 在 [描述] 欄位中輸入一個值。
7. 按一下儲存。
8. 按一下 [合約行]。
9. 按一下 「New」(新增)。
10. 在清單中，標記所選資料列。
11. 在 [設定檔類型] 欄位中，輸入或選取一個值。
12. 在 [薪資類型] 欄位中，輸入或選取一個值。

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a>為時間和登記員工設定薪資合約
1. 關閉頁面。
2. 關閉頁面。
3. 移至時間登記員工。
    * 時間及出勤 > 設定 > 時間登記員工  
4. 在列表中，按一下所選行中的連結。
5. 按一下 [雇用] 索引標籤。
6. 展開 [時間登記] 區段。
7. 按一下 [編輯]。
8. 在 [薪資合約] 欄位中，輸入或選取一個值。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]