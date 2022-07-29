---
title: 設定折舊帳冊
description: 此程序將逐步說明建立新折舊帳冊並將其與固定資產組關聯的流程。
author: moaamer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 42b8a15ac60fd2620c600d78b84a25e3caf6d2bf
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451254"
---
# <a name="set-up-depreciation-books"></a>設定折舊帳冊 

[!include [banner](../../includes/banner.md)]

此程序將逐步說明建立新折舊帳冊並將其與固定資產組關聯的流程。 

## <a name="create-a-depreciation-book"></a>建立折舊帳冊
1. 前往 [固定資產] > [設定] > [折舊帳冊]。
2. 按一下 [新建]。
3. 在 [折舊帳冊] 欄位中，輸入一個值。
4. 在 [描述] 欄位中，輸入一個值。
5. 勾選或取消勾選 [計算折舊] 核取方塊。
6. 在 [折舊設定檔] 欄位中，按一下下拉式按鈕開啟查詢。
7. 在清單中，尋找並選取所需的折舊設定檔。
8. 在清單中，點選已選取列的連結。
9. 在 [替代折舊設定檔] 欄位中，按一下下拉式按鈕開啟查詢。
10. 在清單中，選取所需的折舊設定檔。
11. 在清單中，點選已選取列的連結。
    * 異常折舊設定檔用於在異常情況下對資產進行額外折舊。 例如，您可以使用它來記錄自然災害導致的折舊。  
12. 勾選或取消勾選 [使用基本調整建立折舊調整] 核取方塊。
13. 在 [日曆] 欄位中，按一下下拉式按鈕開啟查詢。
14. 在清單中，點選已選取列的連結。

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>將折舊帳冊與固定資產群組關聯
1. 按一下 [固定資產群組]。
2. 在 [固定資產群組] 欄位中，按一下下拉式按鈕開啟查詢。
3. 在清單中，尋找並選取所需的記錄。
4. 在清單中，點選已選取列的連結。
5. 在 [折舊慣例] 欄位中，選擇一個選項。
6. 在 [使用年限] 欄位中輸入一個數字。
    * 請注意，在設定「使用年限」後，計算折舊期間欄位值。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
