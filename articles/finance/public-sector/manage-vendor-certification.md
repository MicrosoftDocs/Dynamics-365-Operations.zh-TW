---
title: 維護廠商認證
description: 本主題說明廠商可用維護廠商共同作業工作區認證的步驟。
author: v-kiarnd
ms.date: 04/27/2021
ms.topic: article
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 932b8bc2982a7c38404ff4203fce7fb65c1182d4490d2aad5a6d78fd809ec768
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450348"
---
# <a name="maintain-vendor-certification"></a>維護廠商認證

[!include [banner](../includes/banner.md)]

本主題說明您的廠商可用來維護 **廠商共同作業工作區** 認證的步驟。 認證範例可能包括女性商業企業 (WBE) 或能源與環境設計領導力 (LEED) 公司。 廠商將需要在 **廠商資訊** 工作區輸入認證資訊。 廠商將從那裡選取 **更多細節**，然後選取 **認證**。

## <a name="turn-on-the-vendor-certification-feature"></a>開啟廠商認證功能

使用此功能之前，您必須先在系統中開啟。 系統管理員可使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)頁面檢查功能狀態，並視需要啟用。 在 **功能管理** 工作區，此功能以下列方式列出：

- **模組** - *應付帳款*
- **功能名稱** - *啟用廠商共同作業認證管理*

## <a name="add-a-new-certification"></a>新增認證

若要新增認證，請選取 **廠商資訊** 工作區中，**認證** 網格上方的 **新增** 按鈕。 輸入下列資訊：

- 認證號碼
- 認證類型
- 證實組織
- 認證日期
- 適用情況下的賠償金
- 生效日期
- 到期日
- 留言，選擇性

如果有特定認證相關文件，您可以藉由選取 **文件** 按鈕附上。

您的廠商在本頁面輸入的認證將指派 “廠商” 來源。 您可以代表您的廠商在廠商銀行帳號下輸入憑證資訊。 資訊將在這裡顯示，來源將顯示為 **客戶**。

廠商可以根據需求編輯或刪除他們的認證。

## <a name="vendor-collaboration-generated-certification-records"></a>廠商共同作業產生的認證記錄

廠商新增認證資訊後，資訊將顯示在 **廠商共同作業產生的認證** 頁。 若要打開本頁面，請前往 **應付帳款 > 查詢 > 廠商報表 > 廠商共同作業產生的認證**。 所有全新或修改的認證記錄皆預設為可見。 應付帳款文書人員可以檢視更改內容並透過其確認驗證流程進行資訊驗證。 資訊確認後，可選取頁面上列出的認證記錄，並標示為已審核。 將記錄標示為已審核將從預設清單移除。

所有認證更改都在 **廠商共同作業產生的認證** 頁上。 如果頁面未顯示更改，您可以藉由調整廠商帳戶的篩選條件、生效日期範圍或選擇是否包括已審核的認證更改資訊，檢視更改。

