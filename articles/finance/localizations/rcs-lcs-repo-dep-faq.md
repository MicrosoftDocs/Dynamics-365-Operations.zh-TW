---
title: Regulatory Configuration Service (RCS) - Lifecycle Services (LCS) 儲存設備棄用
description: 本主題提供有關 Microsoft Dynamics Lifecycle Services (LCS) 儲存設備棄用，計劃作為 Regulatory Configuration Service (RCS) Global 存放庫推出部份的資訊。
author: JaneA07
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: 68f1ed6a6d6bb0d15a81539da7f483ad71a4d696
ms.sourcegitcommit: 477efa4cb138f41d4f68bcd82552af3473bcc3d9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2021
ms.locfileid: "8451113"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) 儲存設備棄用

[!include [banner](../includes/banner.md)]

Microsoft Dynamics Lifecycle Services (LCS) 作為 Electronic 報表 (ER) 組態的儲存設備存放庫已經棄用。 這個取代將涉及下列更改：

- Microsoft 產生用於 Microsoft Dynamics 365 應用程式的組態將不再發佈到 LCS 的共用資源庫。 它們反而只透過 RCS Global 存放庫發佈。 不過，Dynamics AX 2012 組態將繼續發佈到 LCS 的共用資源庫，直到 AX 2012 的支援生命週期結束。
- 讓您從財務和營運應用程式和 RCS 上傳組態到 LCS 專案資產庫的功能將取消啟動。 不過，您仍然可以使用 LCS 的瀏覽器將組態上傳到專案資源庫。 因此，您將仍然可以新增組態到 LCS，方便它們可以納入解決方案包。
- 從 LCS 匯入的組態將在財務和營運應用程式和 RCS 繼續開放使用和支援一段時間。 不過，此功能最終將會被取代。 (確切的取代日期將於稍候公告。)

## <a name="deprecation-notice"></a>取代通知

LCS 作為儲存設備用途的取代已由[在 Dynamics 365 Finance 移除或取代功能 - LCS 取代通知中公開傳達](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release)。 計劃的取代日期是 2022 年四月 1 日。

## <a name="key-features"></a>關鍵功能

- 使用 RCS 建立和編輯 ER 組態和全球化功能。
- 將組態直接從 RCS 設計器推送到連接的應用程式，例如 Dynamics 365 Finance 環境，方便您快速進行和測試組態更改。
- 透過 Global 存放庫的集中儲存設備集中儲存、共用和管理 ER 組態和 Globalization 功能的生命週期。

## <a name="guidance-for-one-time-and-ongoing-actions"></a>一次性和持續動作的指引

本節說明一套必須一次性完成的步驟。 它也說明之後必須持續完成的步驟。

### <a name="one-time-action"></a>一次性動作

從 LCS 匯入所有必要的組態到 RCS，接著將它們從 RCS 發佈到 Global 存放庫。 如果您正在使用專案特定資產庫在 LCS 儲存衍生的組態，您必須在 LCS 仍可存取時完成下列步驟。

1. 如果 RCS 執行個體已經不開放使用，請佈建一個。 更多資訊，請參閱 [RCS 概觀](rcs-overview.md)。
2. 在佈建的 RCS 執行個體中，針對資產庫中每個包括衍生 ER 組態的 LCS 專案註冊適當的 LCS 存放庫。
3. 從 LCS 存放庫匯入 ER 組態到 RCS。 更多資訊，請參閱 [從 LCS 匯入組態](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md)。
4. 如果未自動提供 Global 存放庫，請在 RCS 註冊。
5. 從目前的 RCS 執行個體上傳所有衍生組態到 Global 存放庫。 使用 **組態包** 功能協助上傳。 更多資訊，請參閱 [RCS 全域 repo 上傳](rcs-global-repo-upload.md)。

### <a name="going-forward"></a>繼續進行

將 RCS 的視覺設計器用於下列用途：

- 擴充 Microsoft 提供的範本。
- 建立貴組織需要的新組態。
- 客製化 Electronic Invoicing 功能和 Tax Calculation Service 的 Globalization 功能。

將 Globalization 存放庫用於下列用途：

- 存取 Microsoft 產生的組態和 Globalization 功能。
- 將您建立或擴充的組態上傳到 Global 存放庫儲存，並在貴組織內部的 Dynamics 365 應用程式環境或與外部組織共用。 更多資訊，請參閱 [在 RCS 建立 ER 組態並上傳到 Global repo](rcs-global-repo-upload.md)。

## <a name="frequently-asked-questions"></a>常見問題

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>這項更改是否意味著 LCS 不能當作組態的中央儲存設備？

是的。 讓您從財務和營運應用程式上傳組態到 LCS 專案資產庫的功能將被取代。 不過，您仍然可以依您需要的程度使用 LCS 的瀏覽器將組態上傳到專案資源庫。

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>我認為 RCS 是匯入全域範本檔案的替代存放庫。 我不認為它用來儲存組態。 哪個是正確的？

RCS 是用於建立和編輯 ER 組態的設計服務。 RCS 有自己的存放庫，稱為 Global 存放庫。 此存放庫用來儲存在 RCS 建立的組態。 待取代把 LCS 當作儲存設備的做法後，Global 存放庫將成為 Microsoft 組態的單一來源。 您必須完成一次性動作才能將您需要的所有組態從 LCS 匯入 RCS，接著從 RCS 發佈到 Global 存放庫。

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>如果沒有 LCS，儲存組態的建議方式是什麼，才能輕鬆管理和傳輸 "測試" 和 "生產" 組態？

RCS 使用 *連接的應用程式* 概念。 連接的應用程式在 RCS 和財務和營運應用程式的任何執行個體之間形成連接。 因為 RCS 可用來編輯組態，連接的應用程式可用來將組態直接從設計器推送到財務和營運應用程式環境。 因此，您可以快速更改和測試您的組態，不必再經過 LCS 專案級儲存設備。

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>是否有顯示設定和管理的範例？

沒有，但您可以完成本主題稍早提到的步驟，將您的組態遷移到 RCS Global 存放庫。

### <a name="is-rcs-a-prerequisite-to-configure-electronic-reporting"></a>RCS 是 Electronic 報表組態的先決行件嗎？

是的。 RCS 包括支援由 Globalozation Services 使用 Globalization 設定的功能，例如 Electronic Invoicing 和 Tax Calculation Service。 不過，服務具有相同的視覺化設計器功能，讓您擴充或建立新 ER 組態。 RCS 也為 ER 組態和 Globalization 功能提供生命週期管理。

### <a name="which-regions-can-rcs-be-deployed-in"></a>RCS 可以部署在哪些區域？

RCS 在下列 Azure 區域已全面開放使用：

- 美國
- 印度
- 法國
- 歐洲

更多有關產品支援的資訊，請參閱 [Dynamics Globalization 服務概觀](globalization-services-overview.md)。 有關地理位置支援資訊，請參閱 [Dynamics 365 和 Power Platform：可用性、資料位置、語言和在地化](https://aka.ms/rcs/D365Productavailabilityguide)。

### <a name="whats-the-cost-of-using-rcs"></a>使用 RCS 的成本是多少？

RCS 和 Globalization 存放庫免費提供給既有的財務和營運應用程式授權部分。 使用 RCS 設計服務或在 Global 存放庫儲存組態無關分開的成本。 目前組態或連接的應用程式數量不受限制。
