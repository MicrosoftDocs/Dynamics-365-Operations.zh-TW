---
title: ER 移轉清理
description: 本主題說明如何使用 ER 移轉清理函數解決 ER 範本問題。
author: NickSelin
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: d437bed9b9873f82bcd047e85245bd2a8c66fb3572c06660f29fc19f66aebae1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460522"
---
# <a name="er-migration-cleanup"></a>ER 移轉清理 

[!include[banner](../includes/banner.md)]

當您管理 Finance 實體時，您可能決定將現行實體移轉到另一個位置。 例如，您可以將生產實體移轉到新的沙箱環境。 如果您將電子報表 ER 架構設定為將範本儲存在 Microsoft Azure Blob 儲存體中，則新沙箱環境中的 **DocuValue** 表是指生產環境中的 Blob 儲存體實體。 但是，無法從沙箱環境存取此實體，因為移轉過程不支援移轉 Blob 儲存體中的成品。 相反，預計在新的沙箱環境中，您指的是尚未獲取 ER 範本的沙箱環境中的 Blob 儲存體實體。

如果您嘗試執行使用範本產生業務文件的 ER 格式，則會發生異常，並且您會收到有關缺少範本的通知。 還會指導您使用 ER 移轉清理選項刪除並重新匯入包含範本的 ER 格式設定。

[![執行 ER 格式。](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)

如果您導覽到 **設定** 頁面 (**組織管理**\>**電子報表**\>**設定**) 並在設定樹狀結構中嘗試刪除使用範本的 ER 格式設定，您將收到類似的錯誤。

[![刪除 ER 格式。](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)

完成以下步驟以解決您無法存取的 ER 範本問題。

1.  進入 **組織管理**\>**定期**\>**移轉清理** 頁。
2.  選取無法執行或刪除的 ER 格式設定。
3.  選取 **刪除**。
4.  確認刪除選定的 ER 格式設定。
5.  將已刪除的 ER 格式設定[匯入](download-electronic-reporting-configuration-lcs.md)到現行 Finance 實體。

## <a name="applicability"></a>適用性

> [重要]**移轉清理** 選項僅針對包含不可存取 ER 範本的 ER 格式設定。 當您使用 **移轉清理** 選項刪除 ER 格式設定時，ER 刪除與唯一應用程式資料庫中的設定成品相關的範本。 未驗證 Blob 儲存體中是否存在適當的實體檔案。 相反，假設沒有。 因此，請勿使用 **移轉清理** 選項作為 ER 設定刪除選項的替代 **設定** 頁上的選項。 僅當 **設定** 頁面上的 ER 設定刪除選項失敗時，才使用 **移轉清理** 選項。
>
> 如果在 Blob 儲存體中提供參考的範本時使用 **移轉清理** 選項刪除 ER 格式設定，則僅刪除應用程式資料庫中的相關設定成品。 Blob 儲存體中範本的實體檔案仍然存在。 不再允許在 Blob 儲存體中覆寫檔案。 如需相關資訊，請參閱[KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217)。 此外，您將無法再重新匯入在此環境中使用移轉清理刪除的設定。 若要解決此問題，您需要在 Blob 儲存體中找到相應的檔案並手動將其刪除。

[![匯入 ER 格式。](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)

如果將應用程式實體移轉到多次用作移轉目標且 Blob 儲存體已包含 ER 範本檔案的另一個位置，則可能會出現類似問題。

因為您可以有多個 ER 格式設定，所以此過程可能很耗時。 因此，偏好使用[ER 範本的備份儲存體](er-backup-storage-templates.md)自動復原具有損壞參考之範本的函數。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]