---
title: 折舊帳簿升級概觀
description: 本主題說明固定資產中目前的帳冊功能。 此功能以早期版本可用的價值模型功能為主，但它同時也包括之前只在折舊帳冊提供的所有功能。
author: moaamer
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom:
- "221624"
- intro-internal
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: eaa47b47a93deda24a6c76572881d1e5bba29c52
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451440"
---
# <a name="depreciation-book-upgrade-overview"></a>折舊帳簿升級概觀

[!include [banner](../includes/banner.md)]

本主題說明固定資產中目前的帳冊功能。 此功能以早期版本可用的價值模型功能為主，但它同時也包括之前只在折舊帳冊提供的所有功能。 價值模型功能和折舊帳簿功能已經合併為眾所皆知的單一帳簿概念。 帳冊功能讓您使用單套頁面、查詣和報表處理貴公司的所有固定資產流程。 本主題提供了升級前應考慮的一些事項。 

升級流程將既有的設定和交易移到新帳簿結構。 價值模型將保持目前狀態不變，作為過帳到總帳的帳簿。 折舊帳簿將移到過帳到總帳選項設定為否的帳簿。 折舊帳簿日記帳名稱將移到過帳層設定為 [無] 的總帳日記帳名稱。 折舊帳簿交易將移至固定資產交易。

在執行資料升級之前，您應該了解可用於將折舊帳簿行升級為交易憑單的兩個選項，以及將用於憑單系列的編號規則。

選項 1：**系統定義的編號規則** - 這是最佳化升級效能的預設選項。 升級將不使用編號規則框架，而是使用設定式方法配置憑單。 升級後，將根據升級的交易使用適當的 **下一個編號集** 建立新的編號規則。 預設情況下，編號規則將以 FADBUpgr\#\#\#\#\#\#\#\#\# 格式使用。 使用此方法時，您可以使用一些參數來調整格式：

-   **編號規則代碼** – 識別編號規則的代碼。 此編號規則代碼不存在，因為它將由升級建立。
    -   常數名稱：**NumberSequenceDefaultCode**
    -   預設值："FADBUpgr"
-   **首碼** – 將用作憑單編號首碼的常數字串值。
    -   常數名稱：**NumberSequenceDefaultParameterPrefix**
    -   預設值："FADBUpgr"
-   **字母數字長度** – 編號規則的字母數字欄位的長度。
    -   常數名稱：**NumberSequenceDefaultParameterAlpanumericLength**
    -   預設值：9
-   **起始編號** - 編號規則要使用的第一個數字。
    -   常數名稱：**NumberSequenceDefaultParameterStartNumber**
    -   預設值：1

選項 2：**現有使用者定義編號規則** - 此選項將允許您定義用於升級的編號規則。 如果您需要進階編號規則設定，請考慮使用此選項。 要使用編號規則，必須使用以下資訊修改升級類別 ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans：

-   **編號規則代碼** – 編號規則的代碼。
    -   常數名稱：**NumberSequenceExistingCode**
    -   預設值：無預設值，必須更新到編號規則代碼。
-   **共用編號規則** – 用於標識數字序列範圍的布林值。 對所有公司的共用編號規則使用 "True"，對特定公司範圍使用 "False"。 使用 "False" 時，含有折舊帳簿交易的每一個公司都必須存在具有指定名稱的編號規則。 含有折舊帳簿交易的每一個分區都存在共用編號規則。
    -   常數名稱：**NumberSequenceExistingIsShared**
    -   預設值：True

參數位於 ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans 類別的開頭。 

*// 指定憑證分配的首選方法* 
 *// True，如果您要使用現有的編號規則代碼* 
 *// False，如果您要使用系統定義的編號規則 (預設)* const boolean NumberSequenceUseExistingCode = false;  

*// 如果使用系統定義的編號規則方法，則指定編號規則的參數。*
 *// 將使用這些參數建立新的編號規則。* const str NumberSequenceDefaultCode = 'FADBUpgr'; const str NumberSequenceDefaultParameterPrefix = 'FADBUpgr'; const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

*// 如果使用現有編號規則方法，則指定現有的編號規則代碼。* 
 *// 將對現有的編號規則逐行進行憑單分配。* const str NumberSequenceExistingCode = ''; *// 指定現有編號規則代碼的範圍* 
 *// True，如果指定的編號規則為共用* 
 *// False，如果指定的編號規則為針對特定公司* 
 *// 如果未找到具有指定範圍的編號規則代碼，將使用預設的系統定義的編號規則。* const boolean NumberSequenceExistingIsShared = true; 

修改常數後重建包含該類別的專案。 

當使用系統產生的編號規則方法 (選項 1) 時，升級將使用設定式處理來分配升級指令碼參數中指定的憑單編號。 它還將在分配後使用指定參數建立新的編號規則。 

當使用使用者定義的現有編號規則方法 (選項 2) 時，資料升級檢查具有折舊帳簿交易的每個分區和公司的資料庫中是否存在具有指定範圍的編號規則。 如果存在，則升級將使用逐行處理來指派使用編號規則框架的編號規則指定的憑單編號。 如果指定範圍內的編號規則不存在，則升級將使用系統定義的預設編號規則方式分配憑單編號，並在分配後建立一個具有指定預設參數的新編號規則。

無論採用哪種方法，資料升級指令碼都會使用為以前的折舊帳簿日記帳名稱建立的新總帳日記帳名稱上的 **憑單系列** 欄位的編號規則。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
