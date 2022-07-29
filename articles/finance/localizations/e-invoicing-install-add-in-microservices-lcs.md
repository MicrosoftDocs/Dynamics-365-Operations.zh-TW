---
title: 在 Lifecycle Services 中安裝微服務增益集
description: 本主題說明如何在 Microsoft Dynamics Lifecycle Services (LCS) 安裝電子開票增益集。
author: dkalyuzh
ms.date: 02/11/2022
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
ms.openlocfilehash: a575f3e26489607dc2143ba05c941240969a0feb
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451731"
---
# <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>在 Lifecycle Services 中安裝微服務增益集

[!include [banner](../includes/banner.md)]

電子發票服務中的驗證要求您透過 Microsoft Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 中安裝適用於您環境的增益集，來在服務平台中註冊您的 Microsoft Dynamics Lifecycle Services (LCS)。

要註冊環境，請按照下列步驟操作。

1. 登入您的 LCS 帳戶。
2. 在專案儀表板上，選擇一個 LCS 專案。
2. 在該專案中，在 **環境** 儀表板上選擇您的已部署環境。 您選擇的環境必須正在執行。
3. 在 **Power Platform 整合** 索引標籤上，在 **環境增益集** 區段，選擇 **安裝新增益集**。
4. 選取 **電子開票**。
5. 在 **AAD 應用程式識別碼** 欄位中，輸入 **091c98b0-a1c9-4b02-b62c-7753395ccabe**。 此值是固定值。 確保只輸入全域唯一識別碼 (GUID)。 請勿包含任何其他符號，例如空格、逗號、句點或引號。
6. 在 **AAD 租用戶識別碼** 欄位中，輸入您的 Azure 訂閱帳戶的租用戶識別碼。 您指定的 Azure Active Directory (Azure AD) 租用戶應該是用於 Regulatory Configuration Service (RCS) 的同一個租用戶。
7. 查看條款和條件，然後選擇核取方塊。
8. 選擇 **安裝**。 幾分鐘後，狀態應該會從 **正在安裝** 變更為 **已安裝**。 您可能需要重新整理頁面才會看到此變更。

現在可以使用電子開票了。

> [!NOTE]
> 公司通常會有多個 Finance 或 Supply Chain Management 環境。 這些環境包括生產環境、使用者驗收測試 (UAT) 環境和開發 (沙盒) 環境。 對於要連接到電子開票的所有環境，您必須完成上述程序。
