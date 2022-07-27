---
title: 雲端和內部部屬函數的比較
description: 該主題顯示了雲端和內部部屬支援的函數。
author: sericks007
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 68082ad0ae264b76a852d8d12412af8c4ad917703441c41e67743d1b499a8d73
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460420"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>雲端和內部部屬函數的比較

[!include [banner](../includes/banner.md)]

本主題顯示了以下應用程式的雲端與內部部屬提供之函數的比較：

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

[開發和管理函數](cloud-prem-comparison.md#development-and-administration-features)相關資訊也包括在內。

下表列出了應用領域。 為整個函數列出了雲端和內部部屬支援。 如果特定要素與整個區域不同，則要素列在函數資料欄的單獨行列中。

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **區域**             | **函數**                | **雲端** | **內部部屬部署** |
|---------------------|-----------------------------|-----------|-----------------|
| 合規性和認證        |                                                                                           | 是       | 是             |
|                                      | SOC 1 類型 1 認證                                                                | 是       | 否              |
| 資料管理和整合      |                                                                                           | 是       | 是             |
|                                      | 將資料匯出到您自己的資料倉庫                                                    | 是       | 是             |
|                                      | 啟用將增量更新匯出到資料實體的函數                                 | 是       | 是             |
|                                      | 資料整合                                                                         | 是       | 是             |
| 文件管理                  |                                                                                           | 是       | 是             |
| 財務管理                 |                                                                                           | 是       | 是             |
| 說明                                 |                                                                                           | 是       | 否              |
| 人力資源                      |                                                                                           | 是       | 是             |
| 智慧                         |                                                                                           | 是       | 是             |
|                                      | 電子報表 (ER)                                                                 | 是       | 是             |
|                                      | ER：與 LCS 整合                                                                  | 是       | 否              |
|                                      | ER：與 SharePoint 整合                                                           | 是       | 否              |
|                                      | ER：與 Regulatory Configuration Services (RCS) 整合                              | 是       | 否              |
|                                      | ER：使用本地檔案系統作為可透過 ER 存放庫存取的 ER 設定的儲存體 | 否        | 是             |
|                                      | 與 PowerBI.com 整合                                                              | 是       | 否              |
|                                      | 與 PowerBI Desktop 整合                                                          | 否        | 是             |
|                                      | 分析性工作區                                                                     | 是       | 否              |
|                                      | 智慧型業務流程：建議                                             | 是       | 否              |
|                                      | 使用 Power BI Desktop 或 Excel PowerQuery 工具製作含 OData 的 Power BI 報表    | 是       | 否              |
|                                      | SQL Server Reporting Services (SSRS) 支援擴展                                 | 是       | 是             |
|                                      | 遙測資料傳輸到雲端                                                   | 是       | 否              |
| Lifecycle Services                   |                                                                                           | 是       | 是             |
|                                      | 可設定的業務流程                                                           | 是       | 否              |
| 當地語系化                        |                                                                                           | 是       | 是             |
| 行動裝置應用程式、工作區和平台 |                                                                                           | 是       | 是             |
| Office 整合                   |                                                                                           | 是       | 是             |
| 組織管理          |                                                                                           | 是       | 是             |
| 薪資表                              |                                                                                           | 是       | 是             |
|                                      | 直接存款                                                                            | 是       | 否              |
| 專案管理和會計    |                                                                                           | 是       | 是             |
| 安全性                             |                                                                                           | 是       | 是             |
| 服務管理                   |                                                                                           | 是       | 是             |
| 網路用戶端                           |                                                                                           | 是       | 是             |
|                                      | 工作記錄器 - 從 BPM 庫儲存或載入工作記錄                         | 是       | 否              |
| 支援                              |                                                                                           | 是       | 是             |
|                                      | 透過協助和支援選單存取支援                                             | 是       | 否              |
|                                      | 商業活動                                                                           | 是       | 是 (需要網路連線能力或必須實施自訂端點以便在內部網路傳送/接收商業活動)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **區域**                | **函數**             | **雲端** | **內部部署** |
|-------------------------|-------------------|-----------|-----------------|
| 資產管理                     |                                                                                           | 是       | 是             |
| 合規性和認證        |                                                                                           | 是       | 是             |
|                                      | SOC 1 類型 1 認證                                                                | 是       | 否              |
| 成本會計                      |                                                                                           | 是       | 是             |
|                                      | Power BI 的成本會計內容套件                                                 | 是       | 否              |
|                                      | 行動裝置應用程式的成本會計工作區                                                  | 是       | 否              |
| 成本管理                      |                                                                                           | 是       | 是             |
|                                      | Power BI 的成本管理內容套件                                                 | 是       | 否              |
| 資料管理和整合      |                                                                                           | 是       | 是             |
|                                      | 設定驅動的擴充函數                                                            | 是       | 否              |
|                                      | 將資料匯出到您自己的資料倉庫                                                    | 是       | 是             |
|                                      | 啟用將增量更新匯出到資料實體的函數                                 | 是       | 是             |
|                                      | 資料整合                                                                         | 是       | 是             |
| 文件管理                  |                                                                                           | 是       | 是             |
| 說明                                 |                                                                                           | 是       | 否              |
| 智慧                         |                                                                                           | 是       | 是             |
|                                      | 電子報表 (ER)                                                                 | 是       | 是             |
|                                      | ER：與 LCS 整合                                                                  | 是       | 否              |
|                                      | ER：與 SharePoint 整合                                                           | 是       | 否              |
|                                      | ER：與 Regulatory Configuration Services (RCS) 整合                              | 是       | 否              |
|                                      | ER：使用本地檔案系統作為可透過 ER 存放庫存取的 ER 設定的儲存體 | 否        | 是             |
|                                      | 與 PowerBI.com 整合                                                              | 是       | 否              |
|                                      | 與 PowerBI Desktop 整合                                                          | 否        | 是             |
|                                      | 分析性工作區                                                                     | 是       | 否              |
|                                      | 智慧型業務流程：建議                                             | 是       | 否              |
|                                      | 使用 Power BI Desktop 或 Excel PowerQuery 工具製作含 OData 的 Power BI 報表    | 是       | 否              |
|                                      | SQL Server Reporting Services (SSRS) 支援擴展                                 | 是       | 是             |
|                                      | 遙測資料傳輸到雲端                                                   | 是       | 否              |
| 庫存管理                 |                                                                                           | 是       | 是             |
| Lifecycle Services                   |                                                                                           | 是       | 是             |
|                                      | 可設定的業務流程                                                           | 是       | 否              |
| 當地語系化                        |                                                                                           | 是       | 是             |
| 製造                        |                                                                                           | 是       | 是             |
| 總體規劃和預測      |                                                                                           | 是       | 是             |
| 規劃最佳化                |                                                                                           | 是       | 否              |
| 行動裝置應用程式、工作區和平台 |                                                                                           | 是       | 是             |
| Office 整合                   |                                                                                           | 是       | 是             |
| 組織管理          |                                                                                           | 是       | 是             |
| 採購             |                                                                                           | 是       | 是             |
|                                      | 從採購申請 PunchOut 到外部目錄                                   | 是       | 否              |
|                                      | 採購支出分析 Power BI 報告                                                  | 是       | 否              |
| 產品資訊管理       |                                                                                           | 是       | 是             |
| 基準產品資料                  |                                                                                           | 是       | 是             |
| 生產                           |                                                                                           | 是       | 是             |
|                                      | 生產表現 Power BI 報告                                                   | 是       | 否              |
| 專案管理和會計    |                                                                                           | 是       | 是             |
| 銷售                                |                                                                                           | 是       | 是             |
|                                      | 銷售和獲利表現 Power BI 報告                                      | 是       | 否              |
| 安全性                             |                                                                                           | 是       | 是             |
| 服務管理                   |                                                                                           | 是       | 是             |
| Supply Chain Management              |                                                                                           | 是       | 是             |
| 運輸管理            |                                                                                           | 是       | 是             |
| 廠商共同作業                 |                                                                                           | 是       | 否              |
|  Warehouse Management                  |                                                                                           | 是       | 是             |
|                                      | 行動裝置倉庫應用程式                                                                      | 是       | 是             |
|                                      | 倉儲 Power BI 報告                                                              | 是       | 否              |
| 網路用戶端                           |                                                                                           | 是       | 是             |
|                                      | 工作記錄器 - 從 BPM 庫儲存或載入工作記錄                         | 是       | 否              |
| 支援                              |                                                                                           | 是       | 是             |
|                                      | 透過協助和支援選單存取支援                                             | 是       | 否              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

若要查看內部部署中提供的函數清單，請參閱[內部部署中提供的商業功能 ](../../../commerce/retail-onprem.md)。

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **區域**         | **函數**         | **雲端** | **內部部署** |
|------------------|---------------------|-----------|-----------------|
| 所有人力資源領域 | 所有人力資源函數 | 是       | 否              |

## <a name="development-and-administration-features"></a>開發和管理函數

| **區域**                   | **函數**                               | **雲端** | **內部部署** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| 組建和測試             |                                           | 是       | 是             |
| 可擴展性              |                                           | 是       | 是             |
| 監控和遙測   |                                           | 是       | 是             |
| 平台相容性     |                                           | 是       | 是             |
| 服務                  |                                           | 是       | 是             |
|                            | 服務環境                    | 是       | 否              |
| 追蹤剖析器               |                                           | 是       | 是             |
| PerfTimer                  |                                           | 是       | 是\*           |
| 升級                    |                                           | 是       | 是             |
|                            | 升級                                   | 是       | 否              |
|                            | 升級並支援以前的版本 | 是       | 否              |
| Visual Studio 開發  |                                           | 是       | 是             |

\*在內部部署環境中，PerfTimer 僅顯示用戶端的結果。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
