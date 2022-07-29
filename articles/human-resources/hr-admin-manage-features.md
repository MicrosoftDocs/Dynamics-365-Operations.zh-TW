---
title: 管理人力資源裡的功能
description: 本主題說明功能管理功能以及使用方法。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d5a27c02df841dfbb17a9375aaf75f93d05cd8e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452574"
---
# <a name="manage-features-in-human-resources"></a>管理人力資源裡的功能


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

身為我們持續為 Microsoft Dynamics 365 Human Resources 持續推出新功能的一份子，我們希望讓客戶盡快體驗新功能。 我們提供預覽功能，它們幾乎早已準備好正式發行，並且已歷經大規模測試。 正式發行之前，我們只是尋找最後一輪的客戶反饋和驗證。

更多有關人力資源裡的新功能資訊，請參閱[人力資源新出爐功能](hr-admin-whats-new.md)和 [Dynamics 365 與 Power Platform 推出計劃](/dynamics365/release-plans/?panel=products1#pivot=products)。

**功能管理** 工作區提供每次推出的功能清單。 新功能會預設為關閉。 您可以使用工作區開啟並查看它們的文件。 更多有關功能管理資訊，請參閱[功能管理概觀](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。

所有新功能的預覽期維持在至少 30 天，典型期間為 30-60 天。 主要功能一般在每年預覽期後的 10 月和 4 月開放使用。 只要您在 **功能管理** 工作區看到新功能，即可開啟它們。 某些功能可能預設開啟。

一旦功能普及化，它就能在實際執行環境開啟或關閉。 **功能管理** 工作區指出預覽功能將成為必備功能的時間點。 這個日期通常是 10 月 1 日或 4 月 1 日，方便對齊半年發行計劃。 您不能關閉強制性功能。 直到它變成強制性功能之前，您都可以在所有環境開啟和關閉。

## <a name="enable-or-disable-preview-features"></a>啟用或停用預覽功能

若要存取預覽功能，請先在您的環境中啟用它們。 啟用或停用預覽功能須依環境而定。

> [!IMPORTANT]
> 預覽功能只在 **沙箱** 環境裡開放使用。 當您開啟預覽功能時，您為身處該組織的所有使用者啟用它。 當您關閉預覽功能時，等於您停用它並使您的使用者無法存取。 預覽功能在人力資源的支援有限。 他們的隱私和安全措施可能比較少，而且不納入人力資源服務等級協定 (SLA)。 您不應使用預覽功能處理個人資料 (亦即任何可能辨別您身份的資訊)，或處理受到法律或法規性的法令遵循要求約束的其他資料。

1. 請在人力資源選取 **系統管理**。

2. 請選取 **功能管理** 圖格。

3. 若要啟用預覽功能，請從清單選取並選取 **啟用**。 若要停用預覽功能，請從清單選取並選取 **停用**。

## <a name="enable-or-disable-benefits-management"></a>啟用或停用福利管理

若要啟用福利管理，請使用[啟用或停用預覽功能](hr-admin-manage-features.md?enable-or-disable-preview-features)的相同程序。

> [!IMPORTANT]
> 啟用後，您不能在 **實際執行** 環境裡停用福利管理。 然而您可以在 **沙箱** 環境裡停用福利管理。

更多有關福利管理組態和使用的資訊，請參閱[福利管理概觀](hr-benefits-management-overview.md)。

福利管理取代 **福利** 工作區裡的功能。 當您啟用福利管理預覽功能後，您就不能再存取 **福利** 工作區裡的下列表單：

- **福利**
- **煏利要素**
- **提撥計算率**
- **福利註冊結果**
- **福利到期和延期結果**
- **福利資格政策規則類型**
- **福利資格政策**
- **資格事件**

您可以在唯讀模式下檢視這些頁面的資訊。 如果希望編輯資訊，必須先停用福利管理 (僅適用 **沙箱** 環境)。

## <a name="enable-or-disable-leave-and-absence"></a>啟用或停用請假`和缺勤

若要啟用請假`和缺勤，請使用[啟用或停用預覽功能](hr-admin-manage-features.md?enable-or-disable-preview-features)的相同程序。

> [!IMPORTANT]
> 啟用後，你不能在請假和缺勤中停用 **多重請假類型** 功能。 這適用 **沙箱** 和 **實際執行** 環境。

更多有關請假和缺勤中的預覽功能資訊，請參閱[請假和缺勤預覽功能](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)。

## <a name="send-us-feedback"></a>送出意見反應給我們

我們希望聆聽您對預覽功能的體驗狀況。 我們鼓勵您在使用這些或任何其他功能時，重覆到下列網站張貼您的反饋意見：

- [社群](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) - 本網站是使用者可以討論使用個、提問並獲得社群幫助的絕佳資源。
- 請告訴我們您希望在產品看到的功能，或者您認為我們應該對既有功能做出哪方面的變動。 對[人力資源構想](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)提出產品構想。
    
請不要在您提交的反饋或產品評論中納入個人資料 (任何可以辨別您身份的資訊)。 收集到的資訊可能會進一步分析，並不會根據適用的隱私法用來回答要求。 根據這些專項計劃分開收集的個人資料受到 [Microsoft 隱私聲明](https://privacy.microsoft.com/privacystatement)的約束。

## <a name="see-also"></a>也請參閱

- [人力資源的新面貌](hr-admin-whats-new.md)
- [Dynamics 365 和 Power Platform 新版本計劃](/dynamics365/release-plans/?panel=products1#pivot=products)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
