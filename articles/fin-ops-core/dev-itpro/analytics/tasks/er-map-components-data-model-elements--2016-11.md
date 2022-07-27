---
title: 建立格式的 ER 對應組件到資料模型元素 (2016 年 11 月)
description: 本主題描述如何將資料模型元素對應到建立的電子報表 (ER) 設定的組件。
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ae4b3123660d123fc5c06cbe0a69d5c66d306252ec2a117a1e6045505022f5a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460237"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a>建立格式的 ER 對應組件到資料模型元素 (2016 年 11 月)

[!include [banner](../../includes/banner.md)]

以下程序顯示了系統管理員或電子報表開發人員角色的使用者如何將資料模型元素對應到建立的電子報表 (ER) 設定的組件，該設定定義了支付業務領域的電子文件格式。 此格式稍後將用於產生用於處理付款的電子文件。 在此範例中，您將為樣本公司「Litware, Inc.」建立格式設定。 這些步驟可以在任何公司中執行，因為所有公司都共用 ER 設定。 若要完成這些步驟，您必須先完成「建立格式設定」工作指南中的步驟。


## <a name="select-a-format-configuration"></a>選取格式設定
1. 進入組織管理 > 工作區 > 電子報表。
2. 點選報表設定。
3. 在樹狀結構中，展開「付款 (簡化模型)」。
4. 在樹狀結構中，選取「付款 (簡化模型)\BACS (UK fictitious)」。
5. 點選設計工具。

## <a name="map-format-components-to-data-model-elements"></a>將格式組件對應到資料模型元素
1. 點選展開/摺疊。
2. 點選對應索引標籤。
3. 在樹狀結構中，展開「模型」。
4. 在樹狀結構中，選取「Xml\Message\ProcessingDate\DateTime」。
5. 在樹狀結構中，選取「model\ProcessingDateTime」。
6. 點選繫結。
7. 在樹狀結構中，選取「Xml\Message\MessageId\String」。
8. 在樹狀結構中，選取「model\MessageIdentification」。
9. 點選繫結。
10. 在樹狀結構中，展開「模型\付款」。
11. 在樹狀結構中，選取「Xml\Message\Payments\Item\Amount\String」。
12. 在樹狀結構中，選取「model\Payments\InstructedAmount」。
13. 點選繫結。
14. 在樹狀結構狀狀結構中，選取「Xml\Message\Payments\Item\TransDate\DateTime」。
15. 在樹狀結構中，選取「model\Payments\TransactionDate」。
16. 點選繫結。
17. 在樹狀結構狀狀結構中，選取「Xml\Message\Payments\Item\Description\String」。
18. 在樹狀結構中，選取「model\Payments\Description」。
19. 點選繫結。
20. 在樹狀結構狀狀結構中，選取「Xml\Message\Payments\Item\Currency\String」。
21. 在樹狀結構中，選取「model\Payments\Currency」。
22. 點選繫結。
23. 在樹狀結構中，選取「Xml\Message\Payments\Item\Id」。
24. 在樹狀結構中，選取「model\Payments\End2EndID」。
25. 點選繫結。
26. 在樹狀結構中，展開「模型\付款\債權人」。
27. 在樹狀結構中，展開「模型\付款\債權人\帳戶」。
28. 在樹狀結構中，展開「模型\付款\債權人\代理程式」。
29. 在樹狀結構中，選取「Xml\訊息\付款\項目\廠商\名稱\字串」。
30. 在樹狀結構中，選取「model\Payments\Creditor\Name」。
31. 點選繫結。
32. 在樹狀結構狀狀結構中，選取「Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String」。
33. 在樹狀結構中，選取「model\Payments\Creditor\Agent\RoutingNumber」。
34. 點選繫結。
35. 在樹狀結構中，選取「Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String」。
36. 在樹狀結構中，選取「model\Payments\Creditor\Account\Number」。
37. 點選繫結。
38. 在樹狀結構中，選取「Xml\Message\Payments\Item\Payer\Name\String」。
39. 在樹狀結構中，展開「model\Payments\Debtor」。
40. 在樹狀結構中，展開「model\Payments\Debtor\Account」。
41. 在樹狀結構中，展開「model\Payments\Debtor\Agent」。
42. 在樹狀結構中，選取「model\Payments\Debtor\Name」。
43. 點選繫結。
44. 在樹狀結構中，選取「Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String」。
45. 在樹狀結構中，選取「model\Payments\Debtor\Agent\RoutingNumber」。
46. 點選繫結。
47. 在樹狀結構中，選取「Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String」。
48. 在樹狀結構中，選取「model\Payments\Debtor\Account\Number」。
49. 點選繫結。
50. 在樹狀結構中，選取「Xml\Message\Payments\Item」。
51. 在樹狀結構中，選取「model\Payments」。
52. 點選繫結。
53. 點選儲存。

## <a name="validate-format-mapping"></a>驗證格式對應
1. 點選「驗證」。
    * 驗證新對應以確保所有繫結都正常。  
2. 關閉頁面。

## <a name="change-status-of-the-current-version-of-format-configuration"></a>更改現行版本格式設定的狀態
在接下來的步驟中，您將格式設定的狀態從草稿更改為已完成，以使其可用於產生付款文件。  
1. 點選更改狀態。
2. 點選「完成」。
3. 在描述欄位中，輸入一個值。
    * 例如，「版本 1」。  
4. 點選確定。
5. 選取現行設定的完整版本。
    * 注意設定儲存為完成 1.1 版：1 版的格式基於 1 版的資料模型。  

## <a name="define-effective-date-for-completed-version-of-format"></a>定義完整版本格式的生效日期
每個格式版本都可以設定為從特定日期開始可供使用。 當多個格式版本在某個日期處於活動狀態時，將選取最新格式 (基於版本編號) 使用。 工作階段日期值用於正確選取版本。  

## <a name="restrict-access-to-created-format-from-companies"></a>限制從公司存取建立的格式
1. 展開 ISO 國家/地區代碼區段。
    * 可以透過識別格式適用的特定國家/地區來限制每種格式的存取。 當特定格式的國家/地區清單為空白時，該格式可用於任何公司。 在國家/地區清單中插入一些 ISO 國家/地區代碼時，該格式只能在主要地址位於該國家/地區的公司中使用。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]