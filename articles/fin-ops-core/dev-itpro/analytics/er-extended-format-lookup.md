---
title: 電子報告 (ER) 擴展格式查詢
description: 本主題介紹當所需格式儲存在全域存放庫中時，如何在 ER 格式查詢中設定 ER 格式參考。
author: NickSelin
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2b69ba1b3b27f447b58cf98b1140a481b01b735a
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460497"
---
# <a name="allow-users-to-set-up-an-er-format-reference-inquiring-a-format-from-the-global-repository"></a>允許使用者設定 ER 格式參考從全域存放庫中查詢格式

[!include [banner](../includes/banner.md)]

您可以使用[電子報表](general-electronic-reporting.md) (ER) 架構根據各個國家/地區的法律要求設定輸出文件的格式。 您還可以使用 ER 架構來設定解析輸入文件的格式，並使用這些文件中的資訊來附加或更新應用程式資料。 這些格式中的每一種都可以在您的 Dynamics 365 Finance 實體中用於處理作為特定業務流程的一部分的輸入或輸出業務文件。

通常，您必須指定在特定業務流程中必須使用的 ER 格式。 為此，請在設定為業務流程特定參數的一部分的查詢欄位中選取單個 ER 格式。 這些查詢欄位通常使用 ER 架構的適當 API 來實施。 如需相關資訊，請參閱[ER 架構 API - 顯示格式對應查詢的代碼](er-apis-app73.md#code-to-display-a-format-mapping-lookup)。

例如，當您設定[外貿參數](../../../finance/localizations/emea-intrastat.md#set-up-foreign-trade-parameters)時，您需要設定對將用於產生 Intrastat 報表和 Intrastat 宣告控制報告的單個 ER 格式的參考。 下面的擷取螢幕畫面顯示了 **外貿參數** 頁面中 ER 格式查詢欄位的外觀。

如果現行 Finance 實體不包含與 Intrastat 業務流程相關的 ER 格式，則此查詢欄位將為空。

[![外貿參數頁面，空白報表格式對應欄位。](./media/ER-ExtLookup-Lookup1.gif)](./media/ER-ExtLookup-Lookup1.gif)

如果現行 Finance 實體包含 Intrastat 業務流程相關的 ER 格式，則此查詢欄位提供 ER 格式。

[![外貿參數頁面，含選項的報表格式對應欄位。](./media/ER-ExtLookup-Lookup2.png)](./media/ER-ExtLookup-Lookup2.png)

此查詢僅提供已匯入現行 Finance 實體的 ER 格式。 若要將 ER 解決方案[匯入](./tasks/er-import-configuration-lifecycle-services.md)現行 Finance 實體，您需要有權執行 ER 架構的相應函數，該架構支援包含 ER 格式的 ER 解決方案的[生命週期](general-electronic-reporting-manage-configuration-lifecycle.md)。

從 Finance 10.0.9 版 (2020 年 4 月發布) 開始，擴展了使用 ER 架構 API 實現的 ER 格式查詢的使用者介面。 您仍然可以在 **選取格式設定** FastTab 上選取現有的 ER 格式。 此外，擴展查詢提供了搜索全域存放庫 (GR) 以查詢特定 ER 格式的新選項。 GR 的所有 ER 格式都在 **從全域存放庫匯入** FastTab 上提供。

[![外貿參數頁面，從全域存放庫 FastTab 匯入。](./media/ER-ExtLookup-Lookup3.png)](./media/ER-ExtLookup-Lookup3.png)

與 **選取格式設定** FastTab 類似，**從全域存放庫匯入** FastTab 僅顯示適用於在此查詢欄位中選取了 ER 格式的業務流程的 ER 格式。 在本例中，產生 Intrastat 宣告。 ER 格式適用於使用者現行登入的公司，具體取決於公司所在國家/地區的內容。

在 **從全域存放庫匯入** FastTab 選取 ER 格式時，選定的 ER 格式[設定](general-electronic-reporting.md#Configuration)將從 GR 匯入到現行 Finance 實體。

[![外貿參數頁面，處理作業說明。](./media/ER-ExtLookup-FormatImport.png)](./media/ER-ExtLookup-FormatImport.png)

然後，如果匯入成功完成，對匯入的 ER 格式的參考將儲存在此查詢欄位中。 首次存取 GR 時，您需要按照提供的連結註冊用於管理對 GR 儲存的存取的[Regulatory Configuration Service](https://aka.ms/rcs) (RCS)。

[![外貿參數頁面，註冊 RCS 的連結。](./media/ER-ExtLookup-RepoSignUp.png)](./media/ER-ExtLookup-RepoSignUp.png)

在預設情況下，**從全域存放庫匯入** FastTab 會顯示臨時儲存中的 ER 格式清單，該清單是基於 GR 內容自動建立的，以提高效能。 第一次打開 **從全域存放庫匯入** FastTab 時會發生這種情況，這可能需要幾秒鐘。

如果在 **從全域存放庫匯入** FastTab 中沒有看到所需的 ER 格式，但您確定此 ER 格式儲存在 GR 中，請選取 **同步** 選項。 此選項將更新臨時儲存並將其與 GR 的現行內容同步。

## <a name="feature-activation"></a>函數啟用

此函數的可用性由 **函數管理** 中的函數 **ER 格式設定的擴展查詢允許查詢全域存放庫** 控制。 在預設情況下啟用此函數。

[![函數管理頁面。](./media/ER-ExtLookup-FeatureMngt.png)](./media/ER-ExtLookup-FeatureMngt.png)

## <a name="security-considerations"></a>安全性注意事項

**維護設定存放庫** (**ERMaintainSolutionRepositories**) 權限控制使用啟用的 **從全域存放庫匯入** FastTab 打開 ER 格式查詢的使用者對 GR 的存取。 若要允許使用者從 ER 格式查詢存取 GR 內容，您需要透過直接或使用已指派的角色和職責向使用者授予 **ERMaintainSolutionRepositories** 權限來更改安全性設定。

以下螢幕擷取畫面顯示了如何將此權限授予指派給 **帳戶** 角色的使用者。 此角色允許使用者在 **外貿參數** 頁面的 **檔案格式對應** 和 **報告格式對應** 欄位中設定外貿參數並設定對 ER 格式的參考。

[![安全性設定頁面。](./media/ER-ExtLookup-SecuritySetting.png)](./media/ER-ExtLookup-SecuritySetting.png)

## <a name="limitations"></a>限制

目前僅支援選取用於產生輸出文件的 ER 格式來存取 ER 格式查詢中的 GR。

## <a name="frequently-asked-questions"></a>常用問題

### <a name="why-cant-i-access-the-global-repository-from-the-er-format-lookup"></a>為什麼我無法透過 ER 格式查詢存取全域存放庫？

如果您在 **函數管理** 頁面上啟用了 **允許查詢全域資源庫的 ER 格式設定擴展查詢** 函數，但使用者在 **從全域存放庫匯入** FastTab 上看不到 ER 格式，**同步** 選項已顯示但被禁用，請確保 **維護設定資源庫** (**ERMaintainSolutionRepositories**) 許可權已被授予給使用者。 請聯絡您的系統管理員以獲得此權限。

## <a name="additional-resources"></a>其他資源

- [電子報表 (ER) 概觀](general-electronic-reporting.md)
- [電子報表 (ER) 架構 API](er-apis-app73.md)
- [管理電子報表 (ER) 設定生命週期](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
