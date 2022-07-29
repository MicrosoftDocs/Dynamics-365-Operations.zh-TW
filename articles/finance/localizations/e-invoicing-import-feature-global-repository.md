---
title: 從全域存放庫匯入功能
description: 本主題說明如何從全域存放庫匯入全球化功能。
author: dkalyuzh
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ff3019986d089a286f7aef94346398b3d328ad54
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451683"
---
# <a name="import-features-from-the-global-repository"></a>從全域存放庫匯入功能

[!include [banner](../includes/banner.md)]

全域存放庫包含與您的設定提供者共用的電子開票功能。 Microsoft 提供的所有電子開票功能都與所有公司共用。 您自動有權存取 Microsoft 發佈到全域存放庫的所有電子開票功能。

要開始使用與您的設定提供者共用的電子開票功能，請將它們從全域存放庫匯入您的 Regulatory Configuration Service (RCS) 執行個體。 然後查看功能詳細資料，例如電子報表 (ER) 設定和處理管道。

## <a name="import-a-feature-from-the-global-repository"></a>從全域存放庫匯入功能

1. 登入您的 RCS 帳戶。
2. 在 **全球化功能** 工作區的 **功能** 部分中，選擇 **電子發票** 圖格。
3. 選取 **匯入** 以打開 **從全域存放庫匯入功能** 查詢。
4. 要瀏覽全域存放庫中可供特定設定提供者使用的電子開票功能，請選擇 **同步** 同步您組織的 RCS 執行個體。 同步完成後，可用電子開票功能的清單會在全域存放庫中更新。 此更新可能需要幾分鐘時間。
5. 選擇要匯入的功能，然後選擇 **匯入**。

要查看匯入的電子開票功能，請確保選擇了正確的設定提供者。 根據預設，活動設定提供者建立的功能會自動篩選掉。您可以調整篩選器以查看由其他提供者 (例如 Microsoft 設定提供者) 建立的功能。

您現在可以使用匯入的功能了。 您可以使用匯入的功能作為範本查看其詳細資料並建立新功能。

> [!NOTE]
> 僅當功能由目前活動的設定提供者建立時，您才能修改它。 您可以使用原始功能作為基礎來建立新功能。 然後，您可以進行所需的變更或設置參數。

當 Microsoft 或與您的公司共用全球化功能的其他公司更新您已匯入的功能時，您可以在 **全球化功能** 工作區的 **相關設置** 區段，選擇 **檢查功能更新** 來檢查是否有更新版本。

如果您看到做為範本的功能有更新，您可以在同步全域存放庫中的已發布功能清單後匯入新版本。
