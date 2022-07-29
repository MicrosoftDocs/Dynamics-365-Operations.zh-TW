---
title: 稅務計算參數中的空白稅功能列表
description: 本主題介紹如何解決稅務計算參數頁面上稅務功能列表為空白的問題。
author: wangchen
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 5b87499042c9c4bfe76e182b170adf4f1cfeac4b
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2022
ms.locfileid: "8451740"
---
# <a name="empty-tax-feature-list-in-tax-calculation-parameters"></a>稅務計算參數中的空白稅功能列表

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="symptom"></a>問題

您已在 Regulatory Configuration Service (RCS) 發布了一項功能，以便您可以在 Microsoft Dynamics 365 Finance 中使用它。  但是，當您打開 Finance 時，前往 **稅務**\>**設定**\>**稅務設定**\>**稅務計算參數**，並嘗試在 **功能設定名稱** 欄位選擇值，值列表為空白。

## <a name="reason"></a>原因

出現此問題通常是因為您的財務環境和 RCS 環境不在同一個租用戶下。

### <a name="rcs-tenant"></a>RCS 租用戶

按照以下步驟尋找您的 RCS 租用戶的識別碼。

1. 複製完整的 RCS URL。 例如，URL 可能是 `https://rcs-rts-sf-ed22b5aeea8-int-westus2.configure.global.int.dynamics.com/namespaces/817ff7a0-0d77-4aba-9360-3c9749e2c5de/?cmp=dat&mi=RCSFeatureDomainsWorkspace`。
2. 打開 InPrivate 瀏覽器視窗，將 RCS URL 貼至網址列，然後選擇 **進入**。 您將前往登入頁面，您可以在其中找到 RCS 租用戶識別碼。 例如，如果登入頁面的 URL 是`https://login.microsoftonline.com/d335a570-a05b-4bc5-8eb3-c42c65f9560d`，則租用戶識別碼是出現在`https://login.microsoftonline.com/`或 **d335a570-a05b-4bc5-8eb3-c42c65f9560d** 後面的資訊。

### <a name="finance-environment-tenant-id"></a>財務環境租用戶識別碼

要尋找財務環境的租用戶識別碼，請按照尋找 RCS 租用戶所遵循的相同步驟進行操作。 但是，請複製並貼上財務環境完整的 URL，而非完整的 RCS URL。

## <a name="resolution"></a>解決方法

如果這兩個租用戶識別碼不同，則您遇到本主題所描述的問題。 如果它們相同，則您遇到了不相關的問題。 在這種情況下，我們建議您聯繫 Microsoft 支援服務。

### <a name="solution-1"></a>解決方案 1

將您的 RCS 環境登入到您的財務環境所登入的同一租用戶。 然後建立並發布稅務功能。

### <a name="solution-2"></a>解決方案 2

與 RCS 中的財務租用戶共用稅務功能。

1. 在 RCS，前往 **全球化功能** \> **稅務計算**。
2. 選擇要共享的功能，然後在 **組織** 索引標籤選擇 **共用**。
3. 在 **組織網域名稱** 欄位內輸入名稱。 例如，輸入 **contoso.onmicrosoft.com**。
4. 選取 **共用**。

![與外部組織共用下拉式對話方塊。](media/ShareTaxFeature.png)
