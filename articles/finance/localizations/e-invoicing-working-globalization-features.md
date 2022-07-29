---
title: 全域化功能元件
description: 本主題概述了全域化功能元件。
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
ms.openlocfilehash: 87d7dd231b9ccda7761c91f129659c18039f3299
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451722"
---
# <a name="globalization-feature-components"></a>全域化功能元件

[!include [banner](../includes/banner.md)]

全域化功能是一組元件，用於定義電子申報 (ER) 設定中的資料轉換規則。 這些元件包括處理電子文件，然後將它們發送到外部管道或從外部管道接收它們的指令。 它們還包括定義何時應為傳入商務資料執行功能的條件。

所有元件都相互依賴。 全域化功能使建立和維護這種依賴關係變得容易，並支持元件集的生命週期管理和版本控制。

## <a name="access-electronic-invoicing-feature-components"></a>存取電子發票功能元件 

1. 登入您的 Regulatory Configuration Service (RCS) 帳戶。
2. 在 **全球化功能** 工作區的 **功能** 部分中，選擇 **電子發票** 圖格。

    全域化特徵有幾個元件。 **電子開票功能** 頁面包括每個元件的單獨索引標籤。

    - **版本** – 此元件支持功能的生命週期管理。 您可以使用它來管理該功能的不同版本的狀態。
    - **設定** – 此元件允許您管理、查看和編輯在處理管道中使用的相關 ER 格式和格式對應設定。
    - **設置** – 此元件允許全域化服務 (例如電子發票服務) 的使用者管理相關功能版本的設定。 因此，它支持靈活建構通訊和回應規則。
    - **環境** – 此元件允許全球化服務 (例如電子發票服務) 的使用者管理使用功能版本設定的環境。 它還允許他們向有權存取功能版本設定的使用者授予授權。
    - **組織** – 此元件允許使用者與外部組織共用功能。
    - **標誌** – 此元件允許您標記可在全域化藍圖中使用的功能以供參考。
