---
title: 設定列印管理記錄特定的 ER 目的地
description: 本主題說明如何為設定為產生輸出文件的電子報表 (ER) 格式設定列印管理記錄特定目的地。
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1e06fafe8d8bbe92ddf4fcd94d7271a1fbb6362a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "8460580"
---
# <a name="configure-print-management-record-specific-er-destinations"></a>設定列印管理記錄特定的 ER 目的地

[!include [banner](../includes/banner.md)]

本主題說明具有系統管理員或應收帳款記帳員角色的使用者如何執行以下工作：

- 為產生普通發票的 ER 解決方案設定命名[電子報表 (ER)](general-electronic-reporting.md) 目的地。
- 將 ER 目的地指派給單個[列印管理](document-reporting-services.md)記錄。

該程序可以在 USMF 公司中完成。 無需編碼。

## <a name="introduction"></a>簡介

您可以在用於產生輸出文件的 ER [格式](general-electronic-reporting.md#FormatComponentOutbound)[設定](general-electronic-reporting.md#Configuration)的檔案輸出組件中為每個資料夾設定[目的地](electronic-reporting-destinations.md)。 當您執行這種類型的 ER 格式時，如果您具有適當的存取權限，您還可以在執行階段更改已設定的目的地設定。

在 Microsoft Dynamics 365 Finance **10.0.17 及更高版本** 中，可以為 ER 格式[設定](er-apis-app10-0-17.md)操作代碼，以指定使用者透過執行該 ER 格式執行的操作。 例如，在 **應收帳款** 模組，在列印管理設定中，您可以選取產生特定商業檔案的 ER 格式，例如普通發票。 然後，您可以選取 **檢視** 以預覽發票或選取 **列印** 以將其發送到印表機。 如果在執行階段為正在執行的 ER 格式傳遞了一個操作，您可以[為不同的使用者操作設定不同的 ER 目的地](er-action-dependent-destinations.md)。

在 Finance **10.0.21 和更高版本** 中，可以為 ER 格式[設定](er-apis-app10-0-21.md)命名目的地，並將其指派給執行該 ER 格式時處理的列印管理記錄。 例如，在 **應收帳款** 模組，在列印管理設定中，您要設定的 **原始** 記錄以執行以下操作：

- 執行 ER 格式。
- 將產生的發票透過電子郵件發送給客戶。
- 設定 **複製** 記錄以執行相同的格式。
- 將發票副本列印到網路印表機。

在這種情況下，您必須為正在執行的 ER 格式設定不同的 ER 目的地，並且必須為不同的列印管理記錄選取目的地。

## <a name="prerequisites"></a>先決條件

在開始之前，必須在 [功能管理](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace)工作區中打開 **允許為每個列印管理項目設定 ER 目的地** 功能。 還必須更改源代碼以允許在現行 Finance 實體中設定命名的 ER 目的地並啟用[新的](er-apis-app10-0-21.md) ER API。

此外，必須將 **普通發票 (Excel)** ER 設定[匯入](er-download-configurations-global-repo.md)您的 Finance 實體。

## <a name="configure-a-new-er-destination"></a>設定新的 ER 目的地

1. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
2. 為客戶帳戶 **US-001** 選取發票。
3. 在 **普通發票** 頁上的 **發票** 索引標籤上，在 **列印管理** 組中，選取 **列印管理**。
4. 在 **列印管理安裝** 頁面，展開 **模組 - 應收帳款**\>**文件**\>**普通發票**，選取 **原始** 記錄，然後按照以下步驟操作：

    1.  觀察所選記錄的現行設定：
        -   在 **報表格式** 欄位中選取預設的 SSRS 報表 **FreeTextInvoice.Report**。
        -   **\<Default\>** 名稱顯示在 **目的地** 欄位中，通知沒有為指派的 SSRS 報表選取自訂目的地。 
    2.  在 **報表格式** 欄位，選取 **普通發票 (Excel)** ER 格式設定。
        -   **目的地** 欄位的名稱更改為 **目的地名稱**。
        -   **\<No named destination\>** 名稱顯示在 **目的地名稱** 欄位中，通知沒有為指派的 ER 格式選取命名目的地。
    3.  選取 **目的地名稱** 欄位右側的箭頭按鈕。    
    4. 在 **電子報表命名目的地** 頁，在 **名稱** 欄位，輸入 **主要目的地**。
    5. 選取 **儲存**。
    6. 在 **檔案目的地** FastTab 上，為 **報表** 組件 [設定](er-destination-type-email.md)**電子郵件** 目的地。
    7. 關閉 **電子報表命名目的地** 頁。
    8. 在 **列印管理安裝** 頁上的 **目的地名稱** 欄位中，選取 **主要目的地** 命名目的地。

    ![為所選 ER 格式安裝命名 ER 目的地並將其指派給列印管理安裝頁面上安裝的列印管理記錄](./media/er-named-destinations-01.gif)

    您現在已經為 **普通發票 (Excel)** 格式設定了命名的 ER 目的地 **主要目的地**，並將其指派給 **模組 - 應收帳款**\>**文件**\>**普通發票** 下的 **原始** 列印管理記錄。

5. 展開 **模組 - 應收帳款**\>**帳戶 - US-001**\>**普通發票**，選取 **原始** 記錄，然後按照以下步驟操作：

    1. 選取並按住 (或按右鍵點選) 記錄，然後選取 **覆寫**。
    2. 選取 **目的地名稱** 欄位右側的箭頭按鈕。
    3. 在 **電子報表命名目的地** 頁面上，在動作窗格上，選取 **新建**。
    4. 在 **名稱** 欄位中，輸入 **US-001 destination**。
    5. 在 **檔案目的地** FastTab 上，為 **報表** 組件 [設定](er-destination-type-print.md)**印表機** 目的地。
    6. 關閉 **電子報表命名目的地** 頁。
    7. 在 **列印管理安裝** 頁上的 **目的地名稱** 欄位中，選取 **US-001 目的地** 命名目的地。

    ![為所選 ER 格式安裝命名 ER 目的地並將其指派給列印管理安裝頁面上安裝的列印管理記錄](./media/er-named-destinations-02.gif)

    您現在已經為 **普通發票 (Excel)** 格式設定了命名的 ER 目的地 **US-001 目的地**，並將其指派給 **模組 - 應收帳款**\>**帳戶 - US-001**\>**普通發票** 下的 **原始** 列印管理記錄。

現在，當處理普通發票時，則執行 **普通發票 (Excel)** ER 格式，並發生以下事件之一：

- 如果普通發票是針對 US-001 以外的客戶的，則產生的文件將透過電子郵件發送。
- 如果普通發票是針對客戶 US-001 的，則會列印產生的文件。

> [!NOTE]
> 如果尚未為執行階段處理的列印管理記錄定義命名目的地，則使用預設 ER 目的地 (如果它們可用於正在執行的 ER 格式)。

> [!IMPORTANT]
> 在 **電子報表目的地** 頁 (**組織管理**\>**電子報表**\>**電子報表目的地**)，如果您選取至少設定了一個命名目的地的 ER 格式，則會通知您存在命名目的地。
>
> ![在電子報表目的地頁面上存在有關所選 ER 格式的已設定命名目的地的通知](./media/er-named-destinations-03.png)
>
> 如果您刪除預設目的地，所有命名的目的地也會被刪除。 如果為列印管理記錄選取了那些命名目的地，則取消這些命名目的地的選取。

## <a name="copy-an-existing-er-destination-as-a-new-named-destination"></a>將現有的 ER 目的地複製為新的命名目的地

當預設命名的 ER 目的地可用於 ER 格式時，它可以用作新 ER 目的地的範本。 若要建立基於預設目的地的新 ER 目的地，請在 **電子報表命名目的地** 頁面上選取 **從預設複製**。 新目的地被命名 **預設**。 您可以根據需要多次重複此步驟。

您可以選取任何現有的命名目的地作為新命名目的地的範本。 若要建立基於選定命名目的地的新命名 ER 目的地，請在 **電子報表命名目的地** 頁面上選取 **複製**。 新目的地與選定的命名目的地具有相同的名稱，但新增了後綴「複製」。 您可以根據需要多次重複此步驟。

## <a name="security-considerations"></a>安全性注意事項

僅當您有 [權限](../sysadmin/role-based-security.md#permissions)執行此工作時，才能在 **列印管理安裝** 頁面上安裝命名的 ER 目的地。 如果將 **設定電子報表格式目的地**[職責](../sysadmin/role-based-security.md#duties)指派給您其中一個[安全性角色](../sysadmin/role-based-security.md#security-roles)，則可以向您授予權限。 如需詳細資訊，請參閱[安全性考量](electronic-reporting-destinations.md#security-considerations)。

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[電子報表 (ER) 目的地](electronic-reporting-destinations.md)

[應用程式更新的電子報表架構 API 更改 10.0.17](er-apis-app10-0-17.md)

[應用程式更新的電子報表架構 API 更改 10.0.21](er-apis-app10-0-21.md)

[更改代碼以使使用者能夠設定和使用命名的 ER 目的地](er-api-named-destinations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
