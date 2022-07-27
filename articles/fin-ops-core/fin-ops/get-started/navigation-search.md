---
title: 瀏覽搜尋
description: 本主題說明如何使用搜尋函數導覽到頁面。
author: aneesmsft
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9e689bef43930dbe364baefaa9f4d0231394ff4f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460406"
---
# <a name="navigation-search"></a>瀏覽搜尋

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題說明如何使用搜尋函數導覽到頁面。

該應用程式包括許多區域和頁面，可幫助您執行各種工作。 若要快速找到完成工作所需的頁面，請使用導覽搜尋功能。

若要使用此功能，請點選 **搜尋** 圖示以顯示 **搜尋** 方塊。 然後，您可以在方塊中輸入一個或多個單字。 系統會立即在應用程式中搜尋與您輸入單字相符的相關頁面。 例如，您可以輸入「廠商發票」作為輸入，然後系統會顯示與該輸入相符的結果。

> [!NOTE]
> **搜尋** 方塊可幫助您尋找和導覽到頁面。 它不會幫助您找到特定的資料或動作。

![搜尋方塊。](media/navigation-search.png "搜尋方塊")

## <a name="quickly-navigate-to-a-particular-page"></a>快速導覽到特定頁面

導覽搜尋功能也是您快速導覽到特定頁面的好方法。 例如，如果您是經常使用 **付款日記帳** 頁面的應付帳款記帳員，您可以在 **搜尋** 方塊中輸入「付款日記帳」。 由於輸入與頁面標題完全相符，因此該頁面列在搜尋結果的頂部，您可以快速導覽到該頁面。

搜尋結果清單顯示頁面標題以及導覽路徑。 這顯示了應用程式中頁面的位置。 它還可以幫助您區分結果中的兩個或多個相似頁面。

當您搜尋頁面時，您的輸入將與頁面標題及其導覽路徑相符。 例如，如果您在 **搜尋** 方塊中輸入「應收」，您將在應收帳款區域中看到可用頁面的結果 - 即使頁面標題不包含「應收」一詞。

## <a name="quickly-navigate-to-a-page-based-on-the-technical-form-name"></a>根據技術表單名稱快速導覽到頁面

導覽搜尋函數還包括進階使用者迫切需要的函數：能夠根據技術表單名稱快速導覽到頁面。 許多使用者對系統非常熟悉，以至於他們知道他們使用的確切表單名稱。 如果您是這些使用者之一，您可以輸入 **form:**，然後輸入您要查詢的表單的名稱。 例如，如果您輸入 **form: vendinvoice**，搜尋結果將顯示表單名稱以 **vendinvoice** 開頭的所有頁面。

## <a name="administration-and-security"></a>管理和安全性

從管理和安全的角度來看，導覽搜尋函數僅顯示兩種類型的結果：

- 目前設定中啟用的頁面 (透過組態機碼)。
- 使用者根據使用者角色有權存取的頁面。

將搜尋結果清單限制為 10 項目。 如果您沒有在結果中找到您要查詢的內容，您應該嘗試最佳化或更新輸入。

## <a name="development"></a>開發

從開發的角度來看，導覽搜尋函數很容易利用，因為在選單項的部署和它們出現在搜尋結果中的能力之間幾乎沒有延遲。 只要從瀏覽窗格或儀錶板連結到選單項目，它們就會自動成為可搜尋的。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
