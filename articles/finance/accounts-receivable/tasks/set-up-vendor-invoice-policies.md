---
title: 設定廠商發票政策
description: 本主題說明如何設定廠商發票原則。
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f9707c7b283f42729126efa57e890e0df65ca8b
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451542"
---
# <a name="set-up-vendor-invoice-policies"></a>設定廠商發票政策

[!include [banner](../../includes/banner.md)]

本主題說明如何設定廠商發票原則。 當您使用 **廠商發票** 頁面過帳廠商發票，以及當您開啟廠商發票 **原則違反** 頁面時，將執行廠商發票原則。 您還可以將廠商發票工作流程設定為每次將發票提交到工作流時執行廠商發票原則。 

- 廠商發票原則不適用於發票登記或發票日記帳中建立的發票。  
- 發票比對驗證不使用廠商發票原則，而是在 **應付帳款參數** 頁面中設定的。  
- 此錄製內容使用 USMF 示範公司。 應付帳款經理或會計經理角色將執行這些步驟。 在開始之前，請確保已選取 **發票比對** 組態金鑰。


## <a name="prepare-to-create-vendor-invoice-policies"></a>準備建立廠商發票原則
1. 前往 **導覽窗格 > 模組 > 應付帳款 > 設定 > 應付帳款參數**。
2. 選取 **發票驗證** 索引標籤。
3. 選取或清除 **自動更新發票標題狀態** 核取方塊。
4. 選取 **確定**。
5. 在 **過帳有差異的發票** 欄位中，選取一個選項。
6. 關閉頁面。
7. 前往 **導覽窗格 > 模組 > 應付帳款 > 原則設定 > 廠商發票原則**。
8. 選取 **參數**。
9. 選取 **新增**。
10. 關閉頁面以返回首頁。

## <a name="create-policy-rule-types-for-vendor-invoices"></a>建立廠商發票原則規則類型
1. 前往 **導覽窗格 > 模組 > 應付帳款 > 原則設定 > 廠商發票原則規則類型**。
2. 選取 **新增**。
3. 在 **規則名稱** 與 **描述** 欄位中輸入值。
4. 在 **查詢名稱** 欄位中，選取下拉式按鈕開啟查詢，然後選取所需的記錄。
5. 選擇 **儲存**。
6. 關閉頁面以返回首頁。

## <a name="define-a-vendor-invoice-policy"></a>定義廠商發票原則
1. 前往 **導覽窗格 > 模組 > 應付帳款 > 原則設定 > 廠商發票原則**。
2. 選取 **新增**。
3. 在 **名稱** 與 **描述** 欄位中輸入值。
4. 展開或摺疊 **原則組織** 區段。
5. 在樹狀結構中，選取 **Contoso 娛樂系統 (美國)**。
6. 選取 **新增**。
7. 展開或摺疊 **原則規則** 區段。
8. 按一下 **建立原則規則**。
9. 在 **原則規則說明** 欄位中，輸入一個值。
10. 選取 **篩選**。
11. 選取 **新增**。 選取所需的記錄。
12. 在 **資料表**、**衍生資料表** 及 **欄位** 欄位中，從下拉功能表中選取或輸入選項。
13. 關閉頁面。
14. 在 **條件** 欄位中，輸入一個值。
15. 選取 **確定**。
16. 選取 **確定**。
17. 關閉頁面以返回首頁。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
