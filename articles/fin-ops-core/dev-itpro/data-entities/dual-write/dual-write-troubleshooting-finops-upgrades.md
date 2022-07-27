---
title: 對財務和營運應用程式升級問題進行疑難排解
description: 本主題提供疑難排解信息，可幫助您解決與財務和營運應用程式升級相關的問題。
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c7c036ef44b0470c9b3f8087e7b5b1e16dde1b34
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460203"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>對財務和營運應用程式升級問題進行疑難排解

[!include [banner](../../includes/banner.md)]





本主題提供有關財務和營運應用程式與 Dataverse 之間的雙重寫入整合的疑難排解信息。 具體來說，它提供的信息可幫助您解決與財務和營運應用程式升級相關的問題。

> [!IMPORTANT]
> 本主題解決的一些問題可能需要系統管理員角色或 Microsoft Azure Active Directory (Azure AD) 租使用者管理員認證。 每個問題的部分說明是否需要特定角色或認證。

## <a name="database-synchronization-errors"></a>資料庫同步處理錯誤

**解決問題所需的角色：** 系統管理員

當您嘗試使用 **DualWriteProjectConfiguration** 表將財務和營運應用程式更新到平台更新 30 時，您可能會收到類似於以下範例的錯誤訊息。

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

若要修復問題，請按照以下步驟操作。

1. 登入到財務和營運應用程式的虛擬機器 (VM)。
2. 以管理員身份打開 Visual Studio，然後打開應用程式物件樹狀結構 (AOT)。
3. 搜尋 **DualWriteProjectConfiguration**。
4. 在 AOT 中，按右鍵點選 **DualWriteProjectConfiguration**，並選取 **新增到新專案**。 選取 **確定** 建立使用預設選項的新專案。
5. 在解決方案總管中，按右鍵點選 **專案屬性**，並將 **在組建上同步資料庫** 設定為 **True**。
6. 構建專案，並確認構建成功。
7. 在 **Dynamics 365** 選單上，選取 **同步資料庫**。
8. 選取 **同步** 做一個完整的資料庫同步。
9. 完整資料庫同步成功後，重新執行 Microsoft Dynamics Lifecycle Services (LCS) 中的資料庫同步步驟，並根據需要使用手動升級腳本，以便繼續進行更新。

## <a name="missing-table-columns-issue-on-maps"></a>對應上缺少資料表欄問題

**解決問題所需的角色：** 系統管理員

在 **雙重寫入** 頁面上，您可能會收到類似於以下範例的錯誤訊息：

*結構描述中缺少來源欄位 \<field name\>。*

![缺少來源資料欄錯誤訊息的範例。](media/error_missing_field.png)

若要解決此問題，請先按照以下步驟確保資料欄在資料表中。

1. 登入到財務和營運應用程式的 VM。
2. 進入 **工作區\>資料管理**，選取 **架構參數** 圖格，然後，在 **資料表設定** 索引標籤上，選取 **重新整理資料表清單** 重新整理資料表。
3. 進入 **工作區\>資料管理**，選取 **資料表** 索引標籤，並確保該資料表已列出。 如果未列出該資料表，請登入到財務和營運應用程式的 VM，並確保該表可用。
4. 從財務和營運應用程式的 **雙重寫入** 頁面打開 **資料表對應** 頁面。
5. 選取 **重新整理資料表清單** 自動填入資料表對應中的資料欄。

如果問題仍未解決，請按照以下步驟操作。

> [!IMPORTANT]
> 這些步驟將指導您完成刪除表然後再次新增它的過程。 為避免出現問題，請務必嚴格按照步驟操作。

1. 在財務和營運應用程式中，進入 **工作區\>資料管理**，並選取 **資料表** 圖格。
2. 尋找缺少該屬性的資料表。 點選工具欄中的 **修改目標對應**。
3. 在 **將暫存對應到目標** 窗格上，點選 **產生對應**。
4. 從財務和營運應用程式的 **雙重寫入** 頁面打開 **資料表對應** 頁面。
5. 如果該屬性未在對應上自動填入，請透過點選 **新增屬性** 按鈕手動新增，然後點選 **儲存**。 
6. 選取對應並點選 **執行**。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]