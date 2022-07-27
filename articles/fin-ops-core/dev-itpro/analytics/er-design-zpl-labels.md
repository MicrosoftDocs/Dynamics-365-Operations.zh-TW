---
title: 設計新的 ER 解決方案來列印 ZPL 標籤
description: 本主題介紹如何設計新的電子報表 (ER) 解決方案來列印 Zebra 程式設計語言 (ZPL) 標籤。
author: NickSelin
ms.date: 02/28/2022
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
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 4fb89f4b56ce8189482bf1a86582ef7e3684b15a
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2022
ms.locfileid: "8460596"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>設計新的 ER 解決方案來列印 ZPL 標籤

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

本主題解釋了系統管理員、電子報表開發人員或電子報表函數顧問角色的使用者如何設定[電子報表 (ER)](general-electronic-reporting.md)架構的參數，設計新ER解決方案所需的 ER [設定](general-electronic-reporting.md#Configuration)以存取 Warehouse Management 系統的資料，並以 Zebra 程式設計語言 (ZPL) II 格式產生自訂倉庫位置標籤。 這些步驟可以在 **USRT** 公司。

## <a name="business-scenario"></a>商務案例

您代表公司在 Microsoft Dynamics 365 Finance 系統中實施倉庫管理。 每個倉庫位置都必須貼有包含條碼的自黏性標籤。 倉庫工作人員將使用手持條碼掃描器來掃描條碼。

所有倉庫位置都已標記在上線前活動的範圍內。 但是，如果現有標籤損壞或重新設定倉庫貨架，您還必須能夠按需列印倉庫位置標籤。 透過使用最近發布的 ER 函數，您可以設定新的 ER 解決方案，讓倉庫主管將標籤直接列印到感熱印表機。

## <a name="configure-the-er-framework"></a>設定 ER 架構

按照[設定 ER 架構](er-quick-start2-customize-report.md#ConfigureFramework)中的步驟設定最小的 ER 參數集。 在開始使用 ER 架構設計新的 ER 解決方案之前，您必須完成此安裝。

## <a name="design-a-domain-specific-data-model"></a>設計特定領域的資料模型

建立新的 ER 設定，包含 Warehouse Management 領域的[資料模型](er-overview-components.md#data-model-component)組件。 這個資料模型將在以後您設計 ER 格式產生倉庫位置標籤時作為資料來源使用。

### <a name="import-a-data-model-configuration"></a>匯入資料模型設定

按照以下步驟從 Microsoft 提供的 XML 檔案匯入所需的資料模型。 或者，您可以建立自己的資料模型，如下一節所述。

1. 下載[倉庫模型.版本.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml)檔案，並將其儲存到本地電腦。
2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **電子報表** 工作區中，選取 **報表設定**。
4. 在 **設定** 頁面上，在動作窗格上，選取 **Exchange**\>**從 XML 檔案載入**。
5. 選取 **瀏覽**，然後尋找並選取 **倉庫模型.版本.1.xml** 檔案。
6. 選取 **確定** 以匯入設定。

![在設定頁面上匯入 ER 資料模型設定。](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>建立資料模型設定

您可以從頭開始建立資料模型，而不是匯入 Microsoft 提供的資料模型檔案。 如需有關顯示如何完成此工作的範例，請參閱[建立新的資料模型設定](er-quick-start1-new-solution.md#DesignDataModel)。

### <a name="review-the-data-model"></a>查看資料模型

您可以在 **資料模型設計工具** 頁面上查看設定的資料模型的可編輯版本。

![資料模型設計工具頁面上 ER 資料模型的結構。](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>為設定的資料模型設計模型對應

作為電子報表開發人員角色的使用者，您必須建立新的 ER 設定，其中包含倉庫資料模型的[模型對應](er-overview-components.md#model-mapping-component)組件。 此組件為 Dynamics 365 Finance 實施已設定資料模型並且專用於該應用程式。 您必須對其進行設定以指定將用於在執行階段用應用程式資料填入已設定資料模型的應用程式對象。 若要完成此工作，您必須了解 Warehouse Management 業務領域的資料結構在 Finance 中是如何實現的。

### <a name="import-a-model-mapping-configuration"></a>匯入模型對應設定

按照以下步驟從 Microsoft 提供的 XML 檔案匯入所需的模型對應。 或者，您可以建立自己的模型對應，如下一節所述。

1. 下載[倉庫模型對應.版本.1.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml)檔案，並將其儲存到本地電腦。
2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **電子報表** 工作區中，選取 **報表設定**。
4. 在 **設定** 頁面上，在動作窗格上，選取 **Exchange**\>**從 XML 檔案載入**。
5. 選取 **瀏覽**，然後找到並選取 **倉庫模型對應.版本.1.1.xml** 檔案。
6. 選取 **確定** 以匯入設定。

![在設定頁面上匯入 ER 模型對應設定。](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>建立模型對應設定

您可以從頭開始建立模型對應，而不是匯入 Microsoft 提供的模型對應檔案。 如需有關顯示如何完成此工作的範例，請參閱[建立新的模型對應設定](er-quick-start1-new-solution.md#CreateModelMapping)。

### <a name="review-the-model-mapping"></a>查看模型對應

您可以在 **模型對應設計工具** 頁面上查看設定的模型對應的可編輯版本。

![模型對應設計工具頁面上 ER 模型對應的結構。](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>設計格式

作為電子報表函數顧問角色的使用者，您必須建立新的 ER 設定，其中包含[格式](er-overview-components.md#format-component)組件。 若要設定此組件，您將使用 ZPL II 代碼來指定倉庫位置標籤的配置。

### <a name="import-a-format-configuration"></a>匯入格式設定

按照以下步驟從 Microsoft 提供的 XML 檔案匯入所需的格式。 或者，您可以建立自己的格式，如下一節所述。

1. 下載[倉庫位置標籤.版本.1.1.xml](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml)檔案，並將其儲存到本地電腦。
2. 進入 **組織管理**\>**工作區**\>**電子報表**。
3. 在 **電子報表** 工作區中，選取 **報表設定**。
4. 在 **設定** 頁面上，在動作窗格上，選取 **Exchange**\>**從 XML 檔案載入**。
5. 選取 **瀏覽**，然後找到並選取 **倉庫位置標籤.版本.1.1.xml** 檔案。
6. 選取 **確定** 以匯入設定。

![在設定頁面上匯入 ER 格式設定。](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>建立格式設定

您可以從頭開始建立格式，而不是匯入 Microsoft 提供的格式檔案。 如需有關顯示如何完成此工作的範例，請參閱[建立新的格式設定](er-quick-start1-new-solution.md#FormatCreate)。

### <a name="review-the-format"></a>查看格式

您可以在 **格式工具** 頁面上查看已設定格式的可編輯版本。

![在格式設計工具頁面上的 ER 格式結構。](./media/er-design-zpl-labels-format.png)

該格式的 `model.Location.Label` 資料來源被設定為產生包含以下資訊的標籤：

- 作為文字的倉庫標題
- 作為條碼的倉庫標題
- 位置標題
- 檢查數字

在資料來源的 **公式設計工具** 頁面上，用於產生標籤的 ER 公式包括一個 `CONCATENATE` 函數，將資訊組合到所需的配置中。

![公式設計工具頁面上的資料來源的公式。](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> 標籤配置的設計使位置標題和校驗位在標籤的中心對齊。 但是，ZPL II 不支援條碼的中心對齊。 因此，`model.Location.Warehouse.Alignment` 資料來源的公式用於對齊標籤中心的條碼。 此公式根據倉庫標題中的字元數計算條碼的左偏移量。

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>準備好您的環境以預覽產生的標籤

以下範例使用 ZPL 標籤的印表機模擬器應用程式在螢幕上顯示產生標籤的預覽。 按照這些步驟啟用該選項。

1. 為 **倉庫位置標籤** 的 ER 格式新增[印表機](er-destination-type-print.md) ER 目的地，並將其設定為將產生的標籤從 Finance 發送到[文件路由代理程式 (DRA)](install-document-routing-agent.md)。
2. 安裝和設定 DRA 以將產生的標籤從 Finance 路由到可從現行工作站存取的本地印表機。
3. 為現行工作站新增本地印表機，並將其設定為將產生的標籤從 DRA 傳遞到印表機模起器應用程式。
4. 安裝資料印表機模擬器應用程式為 Chrome 網路瀏覽器的擴充函數，並將其設定為將產生的標籤從本地資料印表機傳遞到 Web 服務，該服務將轉譯產生的標籤並將它們返回給資料印表機模擬器進行預覽。

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>ER 報告</p>
<p>印表機目的地</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>文件路由代理程式</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>本地印表機</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>印表機模擬器</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>轉譯 Web 服務</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>安裝和設定印表機模擬器應用程式

將 ZPL 轉譯引擎的資料印表機模擬器應用程式新增到您的 Chrome 網路瀏覽器。 本例使用基於 [Labelary ZPL Web 服務](http://labelary.com/service.html)的 [Zpl 印表機](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo)模擬器。 印表機模擬器應用程式會將產生的 ZPL 格式的標籤從本地印表機傳遞到 Web 服務，然後將標籤作為 PDF 或 PNG 檔案返回以供預覽。

1. 在 Chrome 線上應用程式商店中，尋找並選取您要使用的印表機模擬器應用程式。 然後選取 **新增到 Chrome** 將其新增到您的 Chrome 網路瀏覽器。

    ![從 Chrome 線上應用程式商店將資料印表機模擬器應用程式新增到 Chrome 網路瀏覽器。](./media/er-design-zpl-labels-add-app.png)

2. 選取 **啟動應用程式** 從 Chrome 網路瀏覽器執資料印表機模擬器應用程式。

    ![從 Chrome 網路瀏覽器執行印表機模擬器應用程式。](./media/er-design-zpl-labels-run-app.png)

3. 設定正在執行的應用程式：

    1. 關閉應用程式。
    2. 在印表機設定中，將主機設定為 **127.0.0.1**。
    3. 將連接埠設定為 **9100**。

        ![設定印表機模擬器應用程式。](./media/er-design-zpl-labels-configure-app.png)

    4. 重新打開應用程式。 您應該會收到訊息，指出印表機已在指定的主機和接收埠上啟動。

        ![印表機模擬器應用程式重新打開。](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> 由於本範例中使用的印表機模擬器應用程式依賴於 Web 服務來轉譯標籤，因此請確保您的安全設定允許您與該服務通訊。 否則，應用程式將不會收到轉譯的標籤，並且無法提供這些標籤的預覽函數。

### <a name="add-and-configure-a-local-printer"></a>新增和設定本地印表機

[新增新的本地印表機](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b)，現行設備可用於將產生的標籤從 DRA 傳遞到印表機模擬器應用程式。

1. 在 Windows 中，選取 **開始**\>**設定**\>**裝置**\>**印表機\&掃描機**。
2. 選取 **印表機\&掃描機設定**。
3. 如需 **新增印表機或掃描機**，選取 **新增裝置**。
4. 如需 **我想要的印表機沒有列出**，選取 **手動新增**。
5. 在 **透過其他選項尋找印表機** 欄位中，選取 **透過手動設定新增本地印表機或網路印表機**.
6. 在 **選取印表機連接埠** 欄位中，選取 **建立新連接埠**，然後按照以下步驟操作：

    1. 在 **連接埠類型** 欄位中，選取 **標準 TCP/IP 連接埠**。
    2. 在 **主機名稱或 IP 位址** 欄位中，輸入 **127.0.0.1**。
    3. 在 **連接埠名稱** 欄位中，輸入 **ZPL**。
    4. 等到 **檢測 TCP/IP 連接埠** 作業已完成。
    5. 在 **裝置類型** 欄位中，選取 **自訂**，然後選取 **設定**。
    6. 確保指定了以下連接埠設定：

        - **連接埠名稱：** ZPL
        - **印表機名稱或IP 位址：** 127.0.0.1
        - **通訊協定：** 原始
        - **連接埠編號：** 9100

7. 在 **安裝印表機驅動程式** 欄位中，選取 **常用/僅限文字**。
8. 在 **印表機名稱** 欄位中，輸入 **ZebraPrinter**。

![為現行裝置新增本地印表機。](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>安裝和設定 DRA

準備 DRA 以將產生的標籤從 Finance 傳遞到設定的本地印表機。

1. [安裝 DRA](install-document-routing-agent.md#install-the-document-routing-agent)。
2. [設定 DRA](install-document-routing-agent.md#configure-the-document-routing-agent)。
3. 在 DRA 中[註冊本地印表機](install-document-routing-agent.md#register-network-printers)。
4. 在您的 Finance 環境中[啟用本地印表機](install-document-routing-agent.md#administer-network-printers)。

![準備 DRA 以列印產生的標籤。](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>設定 ER 目的地

準備 ER 目的地以將產生的標籤從 Finance 傳遞到 DRA。

1. 進入 **組織管理**\>**電子報表**\>**電子報表目的地**。
2. 在 **電子報表目的地** 頁面上，在動作窗格上，選取 **新建**。
3. 在 **參考** 欄位中，選取 **倉庫位置標籤**。
4. 在 **檔案目的地** FastTab 上，選取 **新建**。
5. 在 **名稱** 欄位中，輸入 **Labels**。
6. 在 **檔案組件名稱** 欄位中，選取 **報告**。
7. 選取 **設定**。
8. 在 **目的地設定** 對話方塊，在 **印表機** 索引標籤，將 **已啟用** 選項設定 **是**。
9. 在 **印表機名稱** 欄位中，選取 **ZebraPrinter**。
10. 在 **文件路由類型** 欄位中，選取 **ZPL**。
11. 選取 **確定**。

![在電子報表目的地頁面上為倉庫位置標籤格式設定 ER 目的地。](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>查看倉庫位置

1. 進入 **Warehouse Management**\>**安裝**\>**倉庫**\>**位置**。
2. 在 **位置** 頁面上，過濾以便只查看在 **檢查數字** 欄位中有一個值的位置。

![在位置頁面上查看倉庫位置。](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>列印倉庫位置標籤

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面，在設定樹狀結構中，展開 **倉庫模型**，並選取 **倉庫位置標籤**。
3. 在動作窗格中，選取 **執行**。
4. 在 **電子報表參數** 對話方塊中，在 **要納入的記錄** 索引標籤，選取 **篩選**。
5. 在 **範圍** 索引標籤上，找到 **資料表** 欄位被設定為 **位置** 以及 **欄位** 被設定為 **位置** 的那一資料列。 在 **標準** 欄位，輸入 **LPEnabled**。
6. 選取 **確定**。
7. 選取 **確定**。 在印表機模擬器應用程式的預覽頁面上產生並顯示標籤。

![在 Zpl 印表機模擬器應用程式的預覽頁上查看產生的標籤。](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>修改標籤的配置

您可以更改倉庫位置標籤的現行配置。 以下範例顯示如何更改配置，以便產生的標籤包含位置設定檔 ID。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 將 **使用目的地作為草稿狀態** [ER 使用者參數](electronic-reporting-destinations.md#applicability)設定為 **是**。
3. 在 **設定** 頁面，在設定樹狀結構中，展開 **倉庫模型**，並選取 **倉庫位置標籤**。
4. 選取 **設計工具**。
5. 在 **格式設計工具** 頁面上，在 **對應** 索引標籤上，選取 `model.Location.Label` 資料來源。
6. 在 **資料來源屬性** 對話方塊中，選取 **編輯**\>**編輯公式**。
7. 在 **公式設計工具** 頁面上，在 **公式** 欄位，查看用於產生標籤的 ER 公式。

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. 更新公式以將位置設定檔 ID 新增到產生的標籤。

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. 選取 **儲存**。
10. 選取 **確定**。
11. 在動作窗格中，選取 **執行**。
12. 在 **電子報表參數** 對話方塊中，在 **要納入的記錄** 索引標籤，選取 **篩選**。
13. 在 **範圍** 索引標籤上，找到 **資料表** 欄位被設定為 **位置** 以及 **欄位** 被設定為 **位置** 的那一資料列。 在 **標準** 欄位，輸入 **Bay**。
14. 選取 **確定**。
15. 選取 **確定**。 在印表機模擬器應用程式的預覽頁面上產生並顯示標籤。

![在 Zpl 印表機模擬器應用程式的預覽頁面上查看包含位置設定檔 ID 的產生標籤。](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>編碼

> [!NOTE]
> 您必須使可編輯 ER 格式的 **常用\\檔案** 組件的編碼設定與所設計的標籤的適當設定同步。 **常用\\檔案** 組件的 **[編碼](er-suppress-bom-characters.md)** 欄位的值不應與用於控制標籤編碼的 ZPL 命令相矛盾 (例如，`^CI` 命令)。 ER 不會驗證這些設定是否同步。

## <a name="additional-resources"></a>其他資源

[印表機目的地](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
