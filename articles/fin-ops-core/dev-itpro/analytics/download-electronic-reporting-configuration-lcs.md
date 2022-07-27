---
title: 從 Lifecycle Services 下載電子報表設定
description: 本主題說明如何從 Microsoft Dynamics Lifecycle Services (LCS) 下載電子報表 (ER) 設定。
author: NickSelin
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: ea603d01d05e98ac69d5a0d12802b5f23ee34793bf4c9b4f885f0e4303f77d2b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460226"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>從 Lifecycle Services 下載電子報表設定

[!include [banner](../includes/banner.md)]

本主題說明如何從 Microsoft Dynamics Lifecycle Services (LCS) 中的[共用資產庫](../lifecycle-services/asset-library.md)下載最新版本的[電子報表 (ER) 設定](general-electronic-reporting.md#Configuration)。

> [!IMPORTANT]
> 已[棄用](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release) LCS 作為 ER 設定的存放庫。 如需相關資訊，請參閱[Regulatory Configuration Service (RCS) - Lifecycle Services (LCS) 儲存棄用](../../../finance/localizations/rcs-lcs-repo-dep-faq.md)。

1. 使用以下角色之一登入應用程式：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

2. 進入 **組織管理**&gt;**工作區**&gt;**電子報表**。
3. 在 **設定提供者** 區段，選取 **Microsoft** 圖格。
4. 在 **Microsoft** 圖格上，選取 **存放庫**。

    [![本地化設定頁面上的 Microsoft 圖格。](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. 在 **設定存放庫** 頁面上，在格線中，選取 **LCS** 類型的現有存放庫。 如果此存放庫未出現在格線中，請執行以下步驟：

    1. 選取 **新增** 以新增存放庫。
    2. 選取 **LCS** 作為存放庫類型。
    3. 選取 **建立存放庫**。
    4. 如果系統提示您授權，請按照螢幕上的說明進行操作。
    5. 輸入存放庫的名稱和描述。
    6. 選取 **確定** 確認新的存放庫條目。
    7. 在格線中，選取 **LCS** 類型的新存放庫。

6. 選取 **開啟** 以查看所選存放庫的 ER 設定清單。

    [![設定存放庫頁面。](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

    > [!TIP]
    > 如果您無法存取 LCS 存放庫以從 LCS 中的共用資產庫下載設定，您可以改為從[全域存放庫](er-download-configurations-global-repo.md)下載設定。

7. 在左側窗格的設定樹狀結構中，選取所需的 ER 設定。
8. 在 **版本** FastTab 上，選取所選 ER 設定的所需版本。
9. 選取 **匯入** 以將所選版本從 LCS 下載到現行實體。

    > [!NOTE]
    > 對於現行實體中已經存在的 ER 設定版本而言，**匯入** 按鈕不可用。

    [![設定存放庫頁面。](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> 根據 ER 設定，設定在匯入後進行驗證。 您可能會收到有關發現的任何不一致問題的通知。 您必須先解決這些問題，然後才能使用匯入的設定版本。 如需相關資訊，請參閱本主題的相關主題清單。

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[從設定服務的全域存放庫下載 ER 設定](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
