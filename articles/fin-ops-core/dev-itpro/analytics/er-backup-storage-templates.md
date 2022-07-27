---
title: ER 範本的備份儲存
description: 本主題說明如何使用電子報表 (ER) 備份儲存來恢復範本。
author: NickSelin
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-13
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b5de8b9dc06cf10bda1932d5f4ee4484cdae591564fdcd5dd28c5036b82abc66
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460511"
---
# <a name="backup-storage-of-er-templates"></a>ER 範本的備份儲存

[!include [banner](../includes/banner.md)]

[電子報表 (ER) 概覽](general-electronic-reporting.md)讓業務使用者可以根據各個國家和地區的法律要求設定輸出文件的格式。 設定的 ER 格式可以使用預定義的範本產生各種格式的輸出文件，例如 Microsoft Excel 活頁簿、Microsoft Word 文件或 PDF 文件。 該範本中填入了為產生的文件設定的資料流程所需的資料。

每個設定的格式都可以作為 ER 解決方案的一區段發佈。 每個 ER 解決方案都可以從 Finance and Operations 的一個實體匯出並匯入另一個實體。

ER 架構使用[設定文件管理](../../fin-ops/organization-administration/configure-document-management.md)來保留現行財務和營運應用程式實體所需的範本。 根據 ER 架構的設定，可以選取 Microsoft Azure Blob 儲存或 Microsoft SharePoint 資料夾作為範本的實際主儲存位置。 (如需相關資訊，請參閱[設定電子報表 (ER) 架構](electronic-reporting-er-configure-parameters.md)。) DocuValue 表包含每個範本的單獨記錄。 在每條記錄中，**AccessInformation** 欄位儲存範本檔案的路徑，該範本檔案位於設定的儲存位置。

當您管理 Finance and Operations 實體時，您可能決定將現行實體移轉到另一個位置。 例如，您可以將生產實體移轉到新的沙箱環境。 如果您將 ER 架構設定為將範本儲存在 Blob 儲存中，則新沙箱環境中的 DocuValue 表是指生產環境中的 Blob 儲存體實體。 但是，無法從沙箱環境存取此實體，因為移轉過程不支援移轉 Blob 儲存體中的成品。 因此，如果您嘗試執行使用範本產生業務文件的 ER 格式，則會發生異常，並且您會收到有關缺少範本的通知。 還會指導您使用 ER 清理工具刪除並重新匯入包含範本的 ER 格式設定。 因為您可能有多個 ER 格式設定，所以此過程可能很耗時。

ER 範本的備份儲存函數可以幫助您製作範本，以便它們始終可用於產生業務文件。

> [!NOTE]
> 僅當選取 Blob 儲存體作為 ER 範本的實際儲存位置時，才能使用此函數。

## <a name="automated-recovery-and-notification"></a>自動恢復和通知

對於此函數，當發生以下事件時，現行環境中新的 ER 格式設定的每個範本都會自動儲存到範本的備份儲存位置 (ERDocuDatabaseStorage 資料庫表)：

- 您匯入包含範本的新 ER 格式設定。
- 您完成包含範本的 ER 格式設定的草稿版本。

範本的備份副本作為應用程式資料庫的一區段移轉到 Finance and Operations 的新實體。

如果需要 ER 格式的範本來產生輸出文件，以處理廠商付款，包括產生付款通知和控制報表，但在主儲存位置中找不到所需的範本，則會發生以下事件：

- 如果範本在備份儲存位置可用，則會自動從備份儲存位置獲取，還原到主儲存位置，並用於現行執行。
- 指派給 **電子報表開發人員** 或 **系統管理員角色** 的每個使用者都會透過動作中心收到有關缺少範本問題的通知。 顯示的訊息取決於 **自動執行批次恢復損壞範本的過程** 參數的值：

    - 如果此參數設定為 **Off**，則訊息建議您啟動批次處理以自動修復其他 ER 格式設定範本的類似問題。 該訊息包含一個可用於啟動批次處理的連結。
    - 如果此參數設定為 **On**，則訊息會通知您已發現缺少範本問題，並且已自動安排新的批次處理 **從內部資料庫備份中還原損壞的範本** 的過程。 此批次處理將自動修復其他範本的類似問題。

若要設定 **自動執行批次恢復損壞範本的過程** 參數，請完成以下步驟：

1. 在 Finance and Operations，開啟 **組織管理\>電子報表\>設定頁面**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 在 **使用者參數** 對話方塊中，為 **自動執行批次恢復損壞範本的程序** 參數設定所需的值。

> [!NOTE]
> 此參數定義為應用程式使用者和登入公司特定的。

![ER 設定頁面。](./media/GER-BackupTemplates-1.png)

下圖顯示了當 **自動執行批次恢復損壞範本的過程** 參數設定為 **On** 時出現的訊息範例。

![廠商付款日記帳頁面。](./media/GER-BackupTemplates-2.png)

下圖顯示了 **批次處理作業** 頁面上的 **從內部資料庫備份還原損壞的範本** 批次處理過程。

![批次處理作業頁面。](./media/GER-BackupTemplates-3.png)

已完成的 **從內部資料庫備份還原損壞的範本** 批次處理的執行記錄中包含了從備份儲存位置還原到主儲存位置的範本資訊。

![批次工作歷程記錄頁面。](./media/GER-BackupTemplates-4.png)

在預設情況下，自動建立駐留在 ER 格式設定中的範本的備份副本的過程是打開的。 若要停止製作範本的備份，請在 **電子報表參數** 頁面的 **附件** 索引標籤中，將 **停止製作範本的備份** 選項設定為 **是**。 您可以從 **電子報表** 工作區中開啟此頁面。

如果您將 **停止製作範本的備份副本** 選項設定為 **是** 並且不想保留以前由範本製作的備份副本，請在 **電子報表參數** 頁面上選取 **清理備份儲存**。

如果您將環境升級到 Finance and Operations 10.0.5 版 (2019 年 10 月) 並希望移轉到包含可執行的 ER 格式設定的新環境，請在移轉發生之前選取 **電子報表參數** 頁面上的 **填入備份儲存**。 此按鈕啟動為所有可用範本製作備份副本的過程，以便可以將它們儲存在範本的 ER 備份儲存位置。

![電子報表參數頁面。](./media/GER-BackupTemplates-5.png)

## <a name="manual-recovery"></a>手動恢復

進入 **組織管理**\>**電子報表**\>**備份損壞的範本** 以手動啟動將 ER 範本從備份儲存位置還原到主儲存位置的過程。 在開始此過程之前，在 **還原損壞的範本** 頁面，您可以指定是否以互動方式執行，或者為此安排批次處理。

## <a name="supported-deployments"></a>支援的部署

在 Finance and Operations 10.0.5 版中，ER 範本的備份儲存函數僅在雲端部署中可供使用。

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[設定電子報表 (ER) 架構](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]