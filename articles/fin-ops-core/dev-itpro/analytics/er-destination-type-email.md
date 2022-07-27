---
title: 電子郵件 ER 目的地類型
description: 本主題說明如何為電子報表 (ER) 格式的每個 FOLDER 或 FILE 組件設定電子郵件目的地。
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 2248b8a35b076eb778a50bbbc67d083380ceee62
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460409"
---
# <a name="email-er-destination-type"></a>電子郵件 ER 目的地類型

[!include [banner](../includes/banner.md)]

執行電子報表 (ER) 格式時，可以產生一份或多份輸出文件。 **資料夾** 或 **檔案** 格式組件在 ER 格式中用於指定輸出文件的結構。 您可以為這些類型的組件設定電子郵件目的地，以將輸出文件作為電子郵件附件發送。

您可以為 ER 格式的每個 **資料夾** 或 **檔案** 組件設定電子郵件目的地。 在這種情況下，**每個輸出文件都單獨透過電子郵件發送**。 根據此目的地設定，產生的文件將作為電子郵件的附件發送。 

> [!NOTE]
> 如果未產生文件，因為相關 **檔案** 組件的 **已啟用** 運算式已設定為回傳 **False** 布林值，則不會發送電子郵件，即使已為組件設定並啟用了電子郵件目的地。

您還可以將多個 **資料夾** 或 **檔案** 組件[組合](#grouping)在一起，然後為群組中的所有組件設定電子郵件目的地。 在這種情況下，由屬於該組的組件產生的所有輸出文件都 **作為單個電子郵件的多個附件發送**。 根據此目的地設定，每個產生的文件將作為單個電子郵件的附件發送。

> [!NOTE]
> 如果一組組件中的 **檔案** 組件至少產生一個文件，則發送電子郵件。 如果分組組件沒有產生文件，因為每個 **檔案** 組件的 **已啟用** 運算式已設定為回傳 **False** 布林值，則不會發送電子郵件，即使已為該組設定和啟用電子郵件目的地也是如此的組件。
>
> **電子郵件** 是唯一可以為一組組件設定的目的地。 若要交付基於組的電子郵件目的地設定透過電子郵件發送的文件，請再新增一個目的地記錄，選取所需的組件，然後為此記錄設定另一個目的地。

可以為單個 ER 格式設定設定多組組件。 透過這種方式，您可以為每組組件設定一個電子郵件目的地，並為每個組件設定一個電子郵件目的地。

## <a name="enable-an-email-destination"></a>啟用電子郵件目的地

若要透過電子郵件發送一個或多個輸出檔案，請執行以下步驟。

1. 在 **電子報表目的地** 頁面上，在 **檔案目的地** FastTab 上，選取格線中的一個組件或一組組件。
2. 選取 **設定**，然後在 **目的地設定** 對話方塊中的 **電子郵件** 索引標籤上，將 **啟用** 選項設定為 **是**。

[![將電子郵件目的地的已啟用選項設定為是。](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="configure-an-email-destination"></a>設定電子郵件目的地

### <a name="email-content"></a>電子郵件內容

您可以編輯電子郵件的主題和內文。

在 **主題** 欄位中，輸入應出現在執行階段產生的電子郵件主題欄位中的電子郵件主題文字。 在 **內文** 欄位中，輸入應出現在執行階段產生的電子郵件內文欄位中的電子郵件內文文字。 您可以為電子郵件主題和內文設定常數文字，也可以使用 ER [公式](er-formula-language.md)在執行階段動態建立電子郵件文字。 已設定的公式必須回傳[字串](er-formula-supported-data-types-primitive.md#string)類型。

您的電子郵件內文由 TEXT 或 HTML 格式組成，具體取決於電子郵件用戶端。 您可以使用 HTML 和內嵌階層式樣式表 (CSS) 允許的任何配置、樣式和品牌。

> [!NOTE]
> 電子郵件用戶端施加配置和樣式限制，可能需要調整 HTML 和 CSS 用於訊息內文。 我們建議您熟悉建立最流行的電子郵件用戶端支援的 HTML 的最佳做法。
>
> 使用正確的編碼來實施回車，具體取決於內文格式。 如需相關資訊，請參閱[字串](er-formula-supported-data-types-primitive.md#string)資料類型。

### <a name="email-addresses"></a>電子郵件地址

您可以指定電子郵件傳送者和電子郵件收件者。 在預設情況下，代表現行使用者發送電子郵件。 若要指定不同的電子郵件傳送者，您必須設定 **傳送地址** 欄位。

> [!NOTE]
> 設定電子郵件目的地時，**傳送地址** 欄位僅對具有 `ERFormatDestinationSenderEmailConfigure` 安全權限的使用者顯示，**為 ER 格式目的地設定傳送者電子郵件地址**。
>
> 當在 [執行階段](electronic-reporting-destinations.md#security-considerations)提供電子郵件目的地以供修改時，**傳送地址** 欄位僅對具有 `ERFormatDestinationSenderEmailMaintain` 安全權限的使用者顯示，**維護 ER 格式目的地的傳送者電子郵件地址**。
>
> 當 **傳送地址** 欄位設定為使用現行使用者以外的電子郵件地址時，必須事先正確 [設定](/microsoft-365/solutions/allow-members-to-send-as-or-send-on-behalf-of-group)**傳送人** 或 **代表傳送** 權限。 否則，在執行階段會引發以下異常：「無法從 \<current user account\> 帳戶以 \<from email account\> 的身份發送電子郵件，請檢查 \<from email account\> 的『傳送人』權限。」

您可以設定 **傳送地址** 欄位以回傳多個電子郵件地址。 在這種情況下，清單中的第一個地址用作電子郵件傳送者地址。

若要指定電子郵件收件者，您必須設定 **發送給** 和 **副本** (可選) 欄位。

您可以透過兩種方式為 ER 設定電子郵件地址。 可以透過與列印管理函數相同的方式完成設定，也可以透過公式直接參考 ER 設定來解析電子郵件地址。

## <a name="email-address-types"></a>電子郵件地址類型

如果在 **目的地設定** 對話方塊中選取 **傳送地址**、**收件地址** 或 **副本** 欄位旁邊的 **編輯**，則相應的 **電子郵件傳送地址**、**電子郵件收件地址** 或 **電子郵件副本地址** 對話方塊出現。 在那裡，您可以設定電子郵件傳送者和電子郵件收件者。 選取 **新增**，然後選取要使用的電子郵件地址類型。 現行支援兩種類型：**列印管理電子郵件** 和 **設定電子郵件**。

[![選取電子郵件地址的類型。](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>列印管理電子郵件

如果您選取 **列印管理電子郵件** 作為電子郵件地址類型，您可以透過設定在 **電子郵件傳送地址**、**電子郵件收件地址** 或 **電子郵件副本地址** 對話方塊中輸入固定的電子郵件地址以下欄位：

- 在 **電子郵件來源** 欄位中，選取 **無**。
- 在 **其他電子郵件地址，以「;」分隔** 欄位，輸入固定的電子郵件地址。

或者，您可以從您為其產生輸出文件的一方的聯絡方式中獲取電子郵件地址。 若要使用未固定的電子郵件地址，請在 **電子郵件來源** 欄位，選取檔案目的地的合作對象[角色](../../fin-ops/organization-administration/overview-global-address-book.md#party-roles)。 支援以下角色：

- 客戶
- 廠商
- 潛在人選
- 連絡人
- 競爭者
- 工作人員
- 申請者
- 潛在廠商
- 不允許的廠商
- 法律實體

例如，若要為用於處理廠商付款的 ER 格式設定電子郵件目標，請選取 **廠商** 角色。

選取所需角色後，選取 **繫結** 旁邊的按鈕 (鏈符號) **電子郵件來源帳戶** 欄位開啟[公式設計工具](general-electronic-reporting-formula-designer.md)頁。 然後，您可以使用此頁面設定一個公式，該公式在執行階段將指派給設定角色的一方的帳號從已處理的文件返回到電子郵件目的地。

> [!NOTE]
> 該公式特定於 ER 設定。

在 **公式設計工具** 頁，在 **公式** 欄位，輸入對受支援角色的特定於文件的參考。 而不是輸入參考，在 **資料來源** 窗格中，找到並選取代表已設定角色帳戶的資料來源節點，然後選取 **新增資料來源** 更新公式。 例如，如果您為用於處理廠商付款的 **ISO 20022 貸記轉帳** 設定設定電子郵件目的地，則代表廠商帳戶的節點是 `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`。

![設定電子郵件來源帳戶。](./media/er_destinations-emaildefineaddresssource.gif)

如果設定角色的帳號對於 Microsoft Dynamics 365 Finance 的整個實體是唯一的，則 **電子郵件發送至** 對話方塊中的 **電子郵件來源公司** 欄位可以保持空白。

或者，您可能會遇到這樣一種情況，即[全球通訊錄](../../fin-ops/organization-administration/overview-global-address-book.md)中的不同方已在不同的公司 ([法律實體](../../fin-ops/organization-administration/organizations-organizational-hierarchies.md#legal-entities)) 中註冊，這樣他們都使用相同的帳號來填入設定的角色。 在這種情況下，設定角色的帳號對於整個 Finance 實體來說不是唯一的。 因此，若要明確選取一方，您不能只指定一個帳號。 您還必須指定該方已在其範圍內註冊的公司以填入設定的角色。 在 **電子郵件發送至** 對話方塊中選取 **電子郵件來源的公司** 欄位旁邊的 **繫結** 按鈕 (鏈符號) 以打開[公式設計工具](general-electronic-reporting-formula-designer.md)頁面。 然後，您可以使用此頁面設定一個公式，該公式在執行階段回傳必須在其範圍內找到所需源的公司代碼。

> [!TIP]
> 如果您必須使用公司代碼來執行 ER 格式，但 ER 格式不提供可以從中獲取公司代碼的任何資料來源，請使用內建的 [GETCURRENTCOMPANY](er-functions-other-getcurrentcompany.md) 設定 `GetCurrentCompany()` 公式 ER 函數。

> [!NOTE]
> 該公式特定於 ER 設定。

若要指定執行階段必須使用的電子郵件地址類型，請在 **電子郵件發送至** 對話方塊中，選取 **收件人** 欄位旁邊的 **編輯** 開啟 **指派電子郵件地址** 下拉式對話方塊。 然後設定以下欄位：

- 在 **目的** 欄位中，選取想要的用途。 只有從被發現方的聯絡人中選取目的的電子郵寄地址才會被使用。
- 將 **主要聯絡人** 選項設定為 **是** 以使用為發現方設定的電子郵件地址作為主電子郵件地址。

> [!NOTE]
> 如果在 **目的** 欄位中選取目的並且同時將 **主要聯絡人** 選項設定為 **是**，則將在執行階段使用滿足至少一個設定標準的每封電子郵件。

### <a name="configuration-email"></a>設定電子郵件

如果您使用的設定在資料來源中有一個節點回傳單個電子郵件地址或多個用分號 (;) 分隔的電子郵件地址，請選取 **設定電子郵件** 作為電子郵件地址類型。 您可以使用公式設計工具中的資料來源和[函數](er-formula-language.md#Functions)來獲取格式正確的電子郵件地址或以分號分隔的正確格式的電子郵件地址。 例如，如果您使用 **ISO 20022 貸記轉帳** 設定，則代表廠商聯絡詳情中廠商主要電子郵件地址的節點是 `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`。

[![設定電子郵件地址來源。](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>群組格式組件

若要對格式組件進行分組，請在 **電子報表目的地** 頁面的 **檔案目的地** FastTab 上，選取格線中的組件，然後選取 **分組**。

**電子郵件** 是之前設定的唯一仍可用於選定組件的目的地。 沒有其他先前設定的目的地可用，因為它們被視為一組組件不受支援。 您將收到有關這些更改的相應通知。

您之前新增的記錄被視為已建立組的標題。 此標頭記錄儲存組的電子郵件目的地設定。 其他記錄是將使用組標題記錄的電子郵件目標設定的組成員。

若要取消分組格式組件，請在 **檔案目的地** FastTab 上，選取屬於該組的記錄，然後選取 **取消分組**。

- 如果您選取一個標題記錄，整個組將被取消分組。
- 如果您選取一個成員記錄，並且它是組中的最後一個成員記錄，則整個組將被取消分組。
- 如果您選取的成員記錄不是分組中的最後一個成員記錄，則該記錄將從現行分組中排除。

下圖顯示了設定為產生壓縮輸出檔案的 ER 格式的結構，該檔案包含催款通知單和 PDF 格式的相應客戶發票。

[![產生輸出文件的 ER 格式的結構。](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

下圖顯示了如本主題中所述對單個組件進行分組並為新組啟用 **電子郵件** 目的地的過程，以便將催款單說明與相應的客戶發票一起作為電子郵件附件發送。

[![對各個組件進行分組並啟用電子郵件目的地。](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>其他資源

- [電子報表 (ER) 概觀](general-electronic-reporting.md)
- [電子報表 (ER) 目的地](electronic-reporting-destinations.md)
- [電子報表 (ER) 中的公式設計工具](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
