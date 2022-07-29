---
title: 定義來源單據的稽核原則
description: 本主題說明如何設定和執行稽核原則規則。
author: panolte
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0779589a3583909984e35014a2ec0e86455cd30a3833110556f095241e7172ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450207"
---
# <a name="define-audit-policies-for-source-documents"></a>定義來源單據的稽核原則

[!include [banner](../../includes/banner.md)]

本主題說明如何設定和執行稽核原則規則。 本範例使用酒店費用類型的費用報表。 此程序使用的是 USMF 示範公司。 稽核者角色包含正確的權限以執行這些任務。

1. 在瀏覽窗格中，前往 **模組 > 稽核工作台 > 設定 > 原則規則類型**。
2. 選取 **新增**。
3. 在 **規則名稱** 欄位中，輸入一個值。
4. 在 **描述** 欄位中，輸入一個值。
5. 在 **查詢名稱** 欄位中，選擇 **費用報表行**
6. 在 **查詢類型** 欄位中，選取 **彙總**
7. 在 **法律實體** 欄位中，選擇 **法律實體**
8. 在 **單據日期參考** 欄位中，選擇 **已修改的日期和時間**
9. 選擇 **儲存**。
10. 在瀏覽窗格中，前往 **模組 > 稽核工作台 > 設定 > 稽核原則**。
11. 選取 **新增**。
12. 在 **名稱** 欄位中，輸入一個值。
13. 展開 **原則組織** 區段。
14. 在樹狀結構中，選取 **Contoso 娛樂系統 (美國)**，然後選取 **新增**。
15. 在樹狀結構中，選取 **Contoso 諮詢 (美國)**，然後選取 **新增**。
16. 在樹狀結構中，選取 **Contoso 零售 (美國)**，然後選取 **新增**。
17. 摺疊 **原則組織** 區段。
18. 展開 **原則規則** 區段。
19. 請在清單中，璇找並選擇之前建立的原則規則。
20. 按一下 **建立原則規則**。
21. 在 **生效日期** 欄位中，輸入日期和時間。
22. 選取 **篩選**。
23. 在清單中，選擇 **費用類別** 行，並將詳細資訊設定為 **酒店**。
24. 在 **條件** 欄位中，輸入或選取一個值。
25. 選取 **彙總** 索引標籤。
26. 選取 **新增**。
27. 在清單中，選擇 **交易金額** 欄位值。
28. 在 **欄位** 欄位中，輸入或選擇值。
29. 在 **AggregateFunction** 欄位中，選取 **合計**。
30. 選取 **群組依據** 索引標籤。
31. 選取 **新增**。
32. 在清單中，選取 **員工** 值。
33. 選取 **新增**。
34. 在清單中，選取 **費用類別** 值。
35. 在 **欄位** 欄位中，輸入或選擇值。
36. 選取 **具有** 索引標籤。
37. 選取 **新增**。
38. 選取 **交易金額**。
39. 在 **欄位** 欄位中，輸入或選擇值。
40. 在 **AggregateFunction** 欄位中，選取 **合計**。
41. 在 **條件** 欄位中，輸入 `>2000`。
42. 選取 **確定**。
43. 選取 **測試**。
44. 請在 **單據選取開始日期** 欄位中輸入日期和時間。
45. 請在 **單據選取結束日期** 欄位中輸入日期和時間。
46. 選取 **執行測試**。
47. 在動作窗格上，選擇 **稽核原則**。
48. 選取 **其他選項**。
49. 在 **開始日期** 欄位中，輸入日期和時間。
50. 在 **結束日期** 欄位中，輸入日期和時間。
51. 選取 **批次**。
52. 展開 **在背景執行** 區段。
53. 請在 **批次處理** 欄位中選取 **是**。
54. 選取 **確定**。
55. 在瀏覽窗格中，前往 **模組 > 稽核工作台 > 稽核案例**。
56. 在清單中，尋找並選取所需的記錄。
57. 展開 **關聯** 區段。
58. 在清單中，尋找並選取所需的記錄。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]