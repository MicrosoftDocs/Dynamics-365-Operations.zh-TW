---
title: 設定成本物件控管者的存取權限
description: 使用使此程序設定成本物件控管者的存取權限。
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70428b653f1263f5c753e0c2d756238b647fe4ba657add467a0142369bbbdd8b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450849"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a>設定成本物件控管者的存取權限

[!include [banner](../../includes/banner.md)]

使用使此程序設定成本物件控管者的存取權限。 此錄製內容使用 USP2 示範資料公司。


## <a name="assign-the-cost-object-controller-role"></a>指派成本物件控管者角色
1. 進入 [系統管理] > [使用者] > [使用者]。
2. 使用快速篩選條件尋找記錄。 例如，在 [使用者名稱] 欄位中篩選值 [alicia]。
3. 在清單中，點選已選取列的連結。
4. 點選 [指派角色]。
5. 在清單中，尋找並選取所需的記錄。
6. 點選 [確定]。

## <a name="enable-access-list-security"></a>啟用存取清單安全性
1. 前往 [成本會計] > [維度] > [維度階層]。
2. 在清單中，尋找並選取所需的記錄。
    * 選取 [組織]。  
3. 點選 [編輯]。
4. 在 [存取清單階層] 欄位中選擇 [是]。
5. 點選 [檢視階層]。

## <a name="assign-access-rights-to-user"></a>為使用者指派存取權限
1. 點選 [新增]。
2. 在清單中，標示選取的列。
3. 在使用者識別碼欄位中，輸入或選取一個值。
    * 選擇 [管理員]。  
4. 在樹狀結構中，選取 [Organization\CEO\CFO\FIM]。
5. 點選 [新增]。
6. 在清單中，標示選取的列。
7. 在使用者識別碼欄位中，輸入或選取一個值。
    * 選取 [Alicia]。  
8. 點選 [儲存]。

## <a name="enable-access-rights-in-cost-accounting"></a>在 [成本會計] 中啟用存取權限
1. 進入 [成本會計] > [設定] > [參數]。
2. 按一下「一般」索引標籤。
3. 在 [啟用成本物件維度成員的檢視表存取權] 欄位中選擇 [是]。
4. 點選 [儲存]。
5. 關閉頁面。
6. 前往 [成本會計] > [設定] > [成本控制工作區設定]。
7. 點選 [編輯]。
8. 在 [已發佈] 欄位中選擇 [是]。
    * 如果您選擇 [是]，則指派了以下四種角色之一的使用者可以在成本控制工作區中查看報表：成本會計經理、成本會計師、成本會計職員和成本物件控管者。 如果您選擇 [否]，則僅指派以下角色之一的使用者可查看報表：成本會計經理、成本會計師和成本會計職員。    
9. 點選 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]