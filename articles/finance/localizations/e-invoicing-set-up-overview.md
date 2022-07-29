---
title: 電子開票設定
description: 本主題概述了設置和設定電子開票功能的流程。
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8138c63e9eff1d2ca934f9d4467e4e3b73dae941
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451692"
---
# <a name="electronic-invoicing-setup"></a>電子開票設定

[!include [banner](../includes/banner.md)]

本主題概述了設置和設定電子開票功能的流程。 您必須按照此處指定的順序完成設定步驟。 如果某個步驟是必需的，但您跳過了它，則該功能將無法正常運作，並且在後續步驟或您使用該功能時會發生多次失敗。 

在開始之前，請確保所有主要元件均已正確設定，您已註冊 Regulatory Configuration Service (RCS) 並擁有 RCS 執行個體，且已為您的 Microsoft Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 環境安裝電子開票增益集。 更多資訊，請參閱[設定並安裝電子開票](e-invoicing-install-add-in-microservices-lcs.md)。

接下來，設定電子開票執行其工作所需的 Azure 資源。 如需更多資訊，請參閱[設定電子開票功能的 Azure 資源](e-invoicing-set-up-azure-resources.md)。

設定主要元件後，使用 RCS 設定電子開票的主要邏輯元件。 首先，定義您將維護的服務環境的數量。 透過這種方式，您可以定義邏輯資料和設定分區，以確保您在開發或測試環境與生產環境之間有一個邊界。 要以靈活的方式設定開發流程，您可能需要多個單獨的開發和測試環境。 除了定義服務環境之外，還可以直接從 RCS 設定指向您的商務應用程式 (例如 Finance 或 Supply Chain Management) 的連接，以設定正確操作電子發票所需的參數。 有關環境的詳細資訊，請參閱[服務環境](e-invoicing-service-environments.md)。

一切設定完成後，您可以建立自己的全球化功能，來定義處理電子文件和轉換資料，或從全域存放庫匯入文件的不同案例。 有關如何使用全球化功能的更多資訊，請參閱[使用全球化功能](e-invoicing-working-globalization-features.md)。

有關構成您將在全球化功能中建立組建流程的處理管道中的動作資訊，請參閱 **[完成！：文件處理動作]**。

如果您的案例需要與電子郵件或 SharePoint 整合來處理傳入電子文件，請參閱[處理傳入的電子文件](e-invoicing-process-incoming-electronic-documents.md)，以了解如何設定和使用這些通道的資訊。
