---
title: 研究或解決例外狀況
description: 當您使用 [廠商發票] 頁面過帳廠商發票，以及當您開啟廠商發票 [原則違反] 頁面時，將執行廠商發票原則。
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32ff53198f61e1d1af3c437e9488c2a246cf820a
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451566"
---
# <a name="research-or-resolve-exceptions"></a>研究或解決例外狀況

[!include [banner](../../includes/banner.md)]

當您使用 **廠商發票** 頁面過帳廠商發票，以及當您開啟廠商發票 **原則違反** 頁面時，將執行廠商發票原則。 您還可以將廠商發票工作流程設定為每次將發票提交到工作流時執行廠商發票原則。 

廠商發票原則不適用於 **發票登記** 或 **發票日記帳** 中建立的發票。 

發票比對驗證不使用廠商發票原則，而是在 **應付帳款參數** 頁面中設定。

此錄製內容使用 USMF 示範公司。 應付帳款經理或會計經理角色將執行這些步驟。 在開始之前，請確保已選取 **發票比對組態** 金鑰。


## <a name="prepare-to-create-vendor-invoice-policies"></a>準備建立廠商發票原則
1. 前往 **應付帳款 > 設定 > 應付帳款參數**。
2. 按一下 **發票驗證** 索引標籤。
3. 選取或清除 **自動更新發票標題狀態** 核取方塊。
4. 按一下 **確定**。
5. 在 **過帳有差異的發票** 欄位中，選取一個選項。
6. 關閉頁面。
7. 前往 **應付帳款 > 原則設定 > 廠商發票原則**。
8. 按一下 **參數**。
9. 按一下 **新增**。
10. 關閉頁面。

## <a name="create-policy-rule-types-for-vendor-invoices"></a>建立廠商發票原則規則類型
1. 前往 **應付帳款 > 原則設定 > 廠商發票原則規則類型**。
2. 按一下 **新建**。
3. 在 **規則名稱** 欄位中，輸入一個值。
4. 在 **描述** 欄位中，輸入一個值。
5. 在 **查詢名稱** 欄位中，按一下下拉式按鈕開啟查詢。
6. 在清單中，尋找並選取所需的記錄。
7. 在清單中，點選已選取列的連結。
8. 按一下 **儲存**。
9. 關閉頁面。

## <a name="define-a-vendor-invoice-policy"></a>定義廠商發票原則
1. 前往 **應付帳款 > 原則設定 > 廠商發票原則**。
2. 按一下 **新建**。
3. 在 **名稱** 欄位中，輸入一個值。
4. 在 **描述** 欄位中，輸入一個值。
5. 展開或摺疊 **原則組織** 區段。
6. 在樹狀結構中，選擇「Contoso 娛樂系統 (美國)」。
7. 按一下 **新增**。
8. 展開或摺疊 **原則規則** 區段。
9. 按一下 **建立原則規則**。
10. 在 **原則規則說明** 欄位中，輸入一個值。
11. 按一下 **篩選**。
12. 按一下 **新增**。
13. 在清單中，標示選取的列。
14. 在 **資料表** 欄位中，按一下下拉式按鈕開啟查詢。
15. 在清單中，點選已選取列的連結。
16. 在 **衍生資料表** 欄位中，按一下下拉式按鈕開啟查詢。
17. 在清單中，點選已選取列的連結。
18. 在 **欄位** 欄位中，按一下下拉式按鈕開啟查詢。
19. 在 **欄位** 欄位中，輸入一個值。
20. 關閉頁面。
21. 在 **條件** 欄位中，輸入一個值。
22. 按一下 **確定**。
23. 按一下 **確定**。
24. 關閉頁面。
25. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
