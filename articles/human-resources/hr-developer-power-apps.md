---
title: 擴充 Talent 和 Power Apps 與 Power Automate
description: 本文說明 Microsoft Dynamics 365 Human Resources 使用 Microsoft Power Apps 和 Microsoft Power Automate 的一些擴充性方案範例。
author: negudava
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fedf9b35e5dc8372fd82c6308ec5b1452eab7e8f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452619"
---
# <a name="extend-with-power-apps-and-power-automate"></a>擴充 Power Apps 和 Power Automate


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本文說明 Microsoft Dynamics 365 Human Resources 使用 Microsoft Power Apps 和 Microsoft Power Automate 的一些擴充性方案範例。 您可以匯入與每個範例關聯的解決套裝方案到您的 Power Apps 環境。 接著您可以將套裝方案當作指引或起點來落實適用貴組織的方案。

> [!IMPORTANT]
> 如果您希望 "按原樣" 使用本主題說明的範本和應用程式，請務必測試，才能確定它們是否涵蓋專指您落實的所有方案。

## <a name="prerequisites"></a>先決條件

- 若要匯入套裝方案，使用者必須具備 **Environment Maker** 權限。
- 若要匯出或匯入應用程式，使用者必須具備 Power Apps 計劃 2 授權或 Power Apps 計劃 2 試用授權。

## <a name="integration-with-microsoft-365-power-automate"></a>整合 Microsoft 365、Power Automate

**整合 Microsoft 365** 應用程式可用來從 Microsoft 365 抽取團隊資訊給簽字認可的使用者。 它參考 Human Resources 的背景工作角色來抽取員工身份識別類型。 經理可以檢查員工識別碼類型的到期日期。 如果員工識別碼類型正要到期，他們也可以傳送電子郵件提醒。 Power Automate 整合 Power Apps 傳送這則提醒。 傳送提醒時，確認將從 Power Apps 傳回 Power Automate。 身份識別類型包括駕照、護照和其他可接受的識別碼形式。

您可以將此應用程式擴充用於其他方案。 例如，您可以使用它顯示團隊假期資訊、行事曆事件和任何團隊特定事件。

若要下載 **整合 Microsoft 365、Power Automate** 應用程式，前往 Microsoft 下載中心的[整合 Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787)。

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – SQL 連線與執行

**Power Automate – SQL 連線與執行** 連線 Microsoft SQL Server 範本並啟用 SQL 查詢功能執行。

雖然此範本讀取和更新 SQL 資料表，但您可以擴充用於其他方案。 例如，您可以使用它在 Dataverse 會同 SQL Server 的記錄填寫暫存資料表，並使用 SQL Server 的增量推送功能定期同步暫存資料表。

Advanced Query 整合 Flow 可支援資料轉換和增量推送。

若要下載 **Power Automate – SQL 連線執行** 範本，請前往 Microsoft 下載中心的 [Power Automate – SQL 連線執行](https://go.microsoft.com/fwlink/?linkid=2081789)。

## <a name="additional-resources"></a>其他資源

[Microsoft Power Platform](/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
