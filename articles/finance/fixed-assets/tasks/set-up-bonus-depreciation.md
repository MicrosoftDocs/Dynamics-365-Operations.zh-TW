---
title: 設定額外折舊
description: 本程序顯示如何建立特別折舊寬減額並將其與固定資產帳冊關聯。
author: moaamer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bfa433c07a2acb37c8e73dfa5db7d1e1715cd1d
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451251"
---
# <a name="set-up-bonus-depreciation"></a>設定額外折舊

[!include [banner](../../includes/banner.md)]

本程序顯示如何建立特別折舊寬減額並將其與固定資產帳冊關聯。 它使用 USMF 法律實體的會計角色和示範資料。


## <a name="create-a-special-depreciation-allowance"></a>建立特別折舊寬減額
1. 前往 [固定資產] > [設定] > [特別折舊寬減額]。
2. 按一下 [新建]。
3. 在 [特別折舊寬減額] 欄位中，輸入一個值。
4. 在 [描述] 欄位中，輸入一個值。
5. 在 [百分比] 欄位中，輸入一個數字。
    * 如果未指明百分比，則設定金額。  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a>將特別折舊寬減額與固定資產群組帳冊關聯
1. 前往 [固定資產] > [設定] > [固定資產群組]。
2. 在清單中，選擇與特別折舊寬減額關聯的固定資產群組。
3. 按一下 [帳冊]。
4. 在清單中，選擇與特別折舊寬減額關聯的帳冊。
5. 按一下 [特別折舊寬減額]。
6. 按一下 [新建]。
7. 在 [特別折舊寬減額] 欄位中，輸入或選取一個值。
    * 百分比或金額的預設值來自特別折舊寬減額設定。  
8. 在 [優先順序] 欄位中，輸入一個數字。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
