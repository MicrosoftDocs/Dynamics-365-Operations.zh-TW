---
title: 有害物質概述
description: 本主題概述產品資訊管理和倉庫管理期間有關處理和記錄有害物質的功能。
author: t-benebo
ms.date: 06/10/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: cfea2cd6a2699bdf2a14de72a8bdeb3e8cd32a17
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449775"
---
# <a name="hazardous-materials-overview"></a>有害物質概述

[!include [banner](../includes/banner.md)]

為了符合貨運和運輸規範，組織在運送歸類為危險品的物質時，必須在貨物中包含額外文書。 有害物質功能可讓客戶儲存與已發佈項目相關的資訊。 然後，此資訊可用於幫助準備貨運文件。 運送危險品的組織必須有自己的流程和程序來管理運送流程。 Microsoft Dynamics 365 Supply Chain Management 只是一種工具，可以幫助產生所需的文件。

下圖說明設定和使用有害物質功能所需的步驟。

![有害物質功能的設定和使用。](media/hazmat-overview.png "有害物質功能的設定和使用")

有害物質功能在產品資訊管理中設定，提供可透過倉庫管理列印的文件。 因此，從廣義上講，這些區域是您檢閱、設定和使用此功能的兩個主要區域：

- **產品資訊管理** - 設定將應用於已發佈產品的代碼。
- **倉庫管理** - 處理將為裝運列印的額外貨運文件。

> [!IMPORTANT]
> Supply Chain Management 中的有害物質功能提供一系列有用的產品資訊欄位和相關功能，可幫助您記錄和參考與有害產品相關的資訊。 這些功能還可以幫助您設計和列印裝運文件，其中包含有關您運送任何有害物質的部分相同資訊。 但是，系統不會自動讓您遵守所在國家或地區的所有適用法規。 儘管這些工具旨在幫助您遵守共同法規，但工具本身並不足以也不能保證如此。 您的組織有責任瞭解所有適用法規，並採取所有必要措施來遵守這些法規。

## <a name="product-information-management"></a>產品資訊管理

產品資訊管理提供一系列設定資料表，您可以在其中輸入陸運、空運和海運的各種危險品清單的參考資訊。

開發此功能時參考了以下共同法規：

- **ADR** - 與國際公路運輸危險貨物有關的法規
- **CFR 49** - 美國關於危險品運輸的規定
- **IMDG** - 國際海運危險品 (IMDG) 代碼
- **IATA** - 國際航空運輸協會 (IATA) 危險品法規

每套法規都提供了危險品和參考代碼的標準化清單。 因此，Supply Chain Management 為這些清單中的常用代碼提供了一個參考資料表。 每個清單還有一些您可以定義的唯一代碼。

有關如何為有害物質設定法規和值，以及如何為相關產品指派值的更多資訊，請參閱以下主題：

- [設定有害物質](hazmat-setup.md)
- [產品、訂單、裝運和裝載中的危險物質](hazmat-items.md)

## <a name="warehouse-management"></a>倉庫管理

您在倉庫管理中準備裝運時，您將能夠列印多項新報告，其中使用您在產品資訊管理中設定的資訊。 有關可用報告及其如何使用的詳細資訊，請參閱[有害物質查詢和報告](hazmat-reports.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]