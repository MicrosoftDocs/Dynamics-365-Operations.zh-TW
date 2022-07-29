---
title: 系統要求
description: 本主題列出 Microsoft Dynamics 365 Human Resources 的系統要求。
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15770595a0639c03df1138ec25010ca8168bd9a8
ms.sourcegitcommit: 49f7528d3268abe15e40f719956e1ec8696a6f4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2021
ms.locfileid: "8451935"
---
# <a name="system-requirements"></a>系統要求

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題列出 Microsoft Dynamics 365 Human Resources 的系統要求。 它也概述開放人力資源的國家/地區和各個區域，以及有關人力資源資料的語言和在地化資訊。

## <a name="supported-web-browsers"></a>支援的 Web 瀏覽器

使用者可以存取 Microsoft Dynamics 365 Human Resources 使用在指定作業系統上執行的下列任何 Web 瀏覽器： 

*   Windows 10 的 Microsoft Edge (最新公開使用版本)
*   Windows 10、Windows 8.1 或 Windows 7 上的 Internet Explorer 11
*   Google Chrome (最新公開使用版本)
*   Apple Safari (最新公開使用版本)

若要尋找每個 Web 瀏覽器的最新版本，請前往軟體廠商的網站。 

## <a name="special-considerations"></a>特殊考量事項

* 為了啟用任務記錄器擷取螢幕擷取畫面並將它們納入產生的 Microsoft Word 文件，您必須安裝預售版的 Chrome 擴充程式
* Workflow Editor 是 ClickOnce 應用程式的啟動程式。 只有 Microsoft Edge 和 Internet Explorer (Microsoft Windows 支援版本上) 支援 ClickOnce 應用程式。 Workflow Editor ClickOnce 應用程式需要 64 位元相容作業系統。
* 若要預覽 PDF 檔案，我們建議您使用現代瀏覽器如 Windows 10 上的 Microsoft Edge (最新公開使用版本) ，或 Windows 10、Windows 8.1、Windows 8、Windows 7 或 Google Nexus 10 平板電腦上的 Google Chrome (最新公開使用版本)。

## <a name="network-requirements"></a>網路要求

* 人力資源專門針對 250-300 毫秒 (ms) 或更短時間延遲的網路設計。 這是從瀏覽器使用者端到託管人力資源的 Microsoft Azure 資料中心。 我們建議您在 [www.azurespeed.com](https://www.azurespeed.com "Azure 延遲測試") 測試網路延遲。
* 人力資源的頻寬要求取決於您的方案。 典型方案需要 50 KB/秒 (KBps) 以上的頻寬。
 
> [!WARNING]
> 請勿以使用者人數乘以最頻寬要求數計算來自使用者端位置的頻寬要求。 預訂位置的同時用量很難計算。 關心頻寬要求的客戶，請使用人力資源試用版。

## <a name="supported-microsoft-office-applications"></a>支援的 Microsoft Office 應用程式

* 若要執行 Microsoft Excel 和 Word 增益集，你必須要有 Windows 或 Mac 安裝的 Microsoft Office 2016。 更多有關版本要求的詳細資訊，請參閱 [Office 整合障礙排除](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md "Office 整合障礙排除")。
* 若要檢視 Excel to Excel 或 Export to Word 功能產生的文件，您必須要有安裝的 Microsoft Office 2007 年版本或更新版本。

## <a name="regional-availability-languages-and-localization"></a>區域可用性、語言和在地化

您可以在 [Microsoft Dynamics 365 國際可用性](/dynamics365/get-started/availability) 下載各個國家/地區、區域和語言支援的人力資源 PDF 檔案。 

> [!NOTE]
> 儘管使用者界面已在地化為其他語言，但所有使用者資料都以輸入時使用的語言儲存。 您可以建立其他語言的電子郵件和範本，但如時程安排資訊等資料目前只有英文版本。

如果您是有興趣建立特定國家或地區的客製化開發人員，或者有興趣為 Microsoft 目前不支援的國家或地區建立解決方案，請參閱[全球化](/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
