---
title: (ER) 從 RCS 匯入設定
description: 本主題提供有關使用者如何從 RCS 匯入新版本的 ER 設定的資訊。
author: NickSelin
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5674c418baaac7817c27780e2f0137ce6e7137eb3f1665f768ad843cc5b3114
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460429"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) 從 RCS 匯入設定

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何從 Microsoft Regulatory Configuration Services (RCS) 匯入電子報表 (ER) 設定的新版本。 在本例中，您將選取已在 RCS 執行個體中設定的 ER 設定版本，並將其匯入樣本公司 Litware, Inc. 的目前執行個體中。這些步驟可以在任何公司執行，因為 ER 設定在公司之間是共用的。 若要完成這些步驟，您首先必須完成本主題中的步驟，[建立設定廠商並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)。 若要完成這些步驟，您還必須有權存取包含至少一個處於 **已完成** 或 **共用** 狀態的 ER 設定的 RCS 執行個體。

1. 進入 **組織行政管理** > **工作區** > **電子報表**。 
2. 確保樣本公司 Litware, Inc. 的設定提供者可用並標記為 **作用中**。 如果您沒有看到此設定廠商，請完成主題中的步驟[建立設定廠商並將其標記為有效](er-configuration-provider-mark-it-active-2016-11.md)。 
3. 如果您沒有為您的公司設定 RCS 環境，請選取 **Regulatory services - 設定** 外部連結並按照說明設定 RCS 環境。 
4. 選取 **電子報表參數**。 
5. 選取 **RCS** 索引標籤。 
6. 如果已經為您的公司提供了 RCS 環境，請使用頁面上的 URL 來存取它。 
7. 關閉頁面。 

## <a name="register-a-new-er-repository"></a>註冊新的 ER 存放庫。 
1. 在清單中，標示選取的列。 
2. 選取 Litware, Inc. 提供者。 
3. 選取存放庫。 
4. 選取新增打開下拉式對話方塊。 
5. 在設定存放庫類型欄位中，輸入「RCS」。 
6. 選取建立存放庫。 
7. 在 RCS 環境顯示名稱欄位中，輸入或選取一個值。 
8. 選取所需的 RCS 執行個體。 您可以擁有多個。 
9. 選取確定。 

## <a name="import-er-configurations-from-rcs-based-repository"></a>從基於 RCS 的存放庫匯入 ER 設定
1. 選取 **顯示篩選條件**。 
2. 使用 **開始於** 篩選器運算子在 **名稱** 欄位中輸入篩選器值「RCS」。 
3. 當您打開選定的存放庫時，在 **連線到 Regulatory Configuration Services** 頁面上，選取 **在此處選取以連線到 Regulatory Configuration Services** 連結。 
4. 請選取 **打開**。 
5. 選取 **關閉**。 
6. 選取所需的 ER 設定版本並選取 **匯入** 以將其引入目前執行個體。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]