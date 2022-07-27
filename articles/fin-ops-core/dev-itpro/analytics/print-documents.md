---
title: 文件列印概述
description: 您可以使用本機印表機或網路連線裝置列印文件。 本文概述了如何列印文件。
author: RichdiMSFT
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: IT Pro, Application User
ms.reviewer: kfend
ms.custom:
- "69161"
- intro-internal
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b9105ef39e411ac33043f1941d4e1dd32b758e5
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460376"
---
# <a name="document-printing-overview"></a>文件列印概述

[!include [banner](../includes/banner.md)]

您可以使用本機印表機或網路連線裝置列印文件。 本文概述了如何列印文件。

## <a name="printing-overview"></a>列印概述

該應用程式提供整合服務和客戶端應用程式，可以輕鬆產生、儲存和分發支援業務活動的文件。 您可以使用本機印表機或網路連線裝置列印文件。 此外，您可以直接從客戶端將頁面和報表匯出為 PDF 檔案或 Microsoft Office 文件。 最後，分佈式工作負載允許您使用網路資源直接從行動裝置列印業務文件。 儘管列印要求可能會有所不同，但所有行業通常都必須使用該應用程式建立業務文件的紙本。 從託管應用程式在網路裝置上列印文件提出了一系列獨特的挑戰。 這裡有些範例：

- 使用者裝置上可能不提供列印驅動程式。
- 使用者的裝置可能未連線到公司網路。

透過使用專用主機並遵循幾個簡單的步驟，系統管理員可以設定部署，以便使用者可以直接從網路裝置上的業務應用程式進行列印。

### <a name="application-printing-scenarios"></a>應用程式列印方案 

下表描述了三種主要的列印方案。

| 方案                        | 目標                                                      | 解決方案 |
|---------------------------------|-----------------------------------------------------------|----------|
| 1. 列印您看到的物件        | 列印瀏覽器中目前顯示的內容。             | 為瀏覽器產生網頁的「易於列印」版本。 |
| 2. 互動式列印         | 在本機連線的裝置上列印精確文件。 | 您可以匯出 PDF 版本的報表並將其下載到瀏覽器。 |
| 3. 在網路裝置上列印 | 將精確文件發送到域印表機裝置。     | 精確文件被發送到在客戶域中託管的伺服器上執行的客戶端應用程式。 |

由於解決方案因方案而異，因此應用程式會提供內建服務和工具來幫助使用者實現目標：

- **方案 1** 由瀏覽器呈現的 HTML5 客戶端支援。
- **方案 2** 使用客戶端應用程式和 Microsoft 365 服務。
- **方案 3** 需要客戶端應用程式和 Microsoft Azure 中託管服務的支援。

除了部署到 Azure 訂閱的平台之外，財務和營運應用程式還為客戶提供整合的第一方 Azure 應用程式，幫助他們更輕鬆地使用域託管裝置列印文件。

## <a name="service-overview"></a>服務概述
當託管應用程式產生的文件等待在網路裝置上列印時，它們儲存在 Azure blob 儲存體中。 [安裝 Document Routing Agent 以啟用網路列印](install-document-routing-agent.md)使用 Azure 身份驗證建立 Azure 服務的安全通道。

**執行順序**

1. 該報表由 Microsoft SQL Server Reporting Services (SSRS) 產生並儲存在 Azure Blob 儲存體中。 附加的印表機設定與文件一起儲存。
2. Document Routing Agent 在 Azure 服務總線佇列中查詢有效的作業。
3. Document Routing Agent 下載並多工緩衝到網路印表機。

以客戶端為基礎的解決方案讓客戶可以管理他們的列印需求規模。 擁有大量列印工作負載的客戶可以安裝多個 Document Routing Agents 以增加並發列印動作的數量。 或者，一些客戶只需要簡單安裝 Document Routing Agent 即可處理他們預期的列印需求。

### <a name="service-components-for-network-printing"></a>網路列印服務組件

下圖顯示了有助於支援網路列印動作的基本組件。

[![service-components-for-network-printing\_2016。](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)

請注意，一台印表機可以註冊到多個 Document Routing Agent。 為了解決印表機偏好設定，託管服務使用唯一識別每台網路印表機的網路路徑。 因此，即使印表機由多個客戶端註冊，它也會在應用程式中可用的印表機清單中顯示為單個選取。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]