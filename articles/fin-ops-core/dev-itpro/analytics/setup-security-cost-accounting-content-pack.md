---
title: 為成本會計分析 Power BI 內容設定安全性
description: 本主題說明如何將成本會計中的存取級別安全性傳播到 Microsoft Power BI 中的列級安全性。
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f519a38b381da0efc1e91ba0f2015780d086550c3e38810e6845a0fc07976767
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460279"
---
# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>為成本會計分析 Power BI 內容設定安全性

[!include [banner](../includes/banner.md)]

本主題說明如何將成本會計中的存取級別安全性傳播到 Microsoft Power BI 中的列級安全性。 此函數有助於確保使用者只能看到他們有權存取的 Power BI 資料。

## <a name="overview"></a>概觀

**成本會計分析** Microsoft Power BI 內容使用 Power BI 列級安全性來限制使用者的存取。 安全性基於成本會計參數中設定的存取級別組織階層。 如需 **成本會計分析** Power BI 內容的相關資訊，請參閱[成本會計分析 Power BI 內容](cost-accounting-analysis-content-pack.md)。

## <a name="setup"></a>設定
若要將存取級別的安全性傳播到 Power BI，Power BI 內容的擁有者必須遵循這些步驟。

> [!NOTE]
> 發佈 **成本會計分析** Power BI 內容的使用者自動成為擁有者。 只有擁有者才能在 Power BI 中設定安全性。 此外，在擁有者在 PowerBI.com 上新增其他使用者之前，除擁有者之外的任何人都無法看到 **成本會計分析** Power BI 內容中的任何資料。

1. 將定義檔案發佈到 Power BI。
2. 登入 PowerBI.com。
3. 查詢 **成本會計分析** Power BI 內容的資料集。
4. 打開安全性頁面。

    ![開啟安全性頁面。](./media/CA-picture-1.png)

5. **成本物件控制器** 角色已經建立。 新增屬於成本會計存取級別組織階層的其他成員。

    ![新增成員。](./media/CA-picture-2.png)

根據成本會計存取級別組織階層中的定義，新增到 **成本物件控制器** 角色的使用者將只能看到允許他們查看的資料。

> [!NOTE]
> 列級安全適用於從 Power BI 嵌入的圖格和報表。

## <a name="updating-security"></a>更新安全性
如果對成本會計中的存取級別安全性進行了更新，並且您希望 Power BI 反映這些更新，則必須更新實體儲存以進行 **成本會計分析** Power BI 內容。 完成實體儲存更新後，您必須更新 PowerBI.com 上的成品。 如需如何進行實體儲存更新的相關資訊，請參閱[Power BI 與實體商店整合](power-bi-integration-entity-store.md#update-entity-store)。 如果新使用者被授予對組織階層的存取權限，則 **成本會計分析** Power BI 內容的擁有者還必須執行實體儲存更新。 此外，擁有者必須將新使用者新增到 PowerBI.com 上的 **成本物件控制器** 角色，以便為他們應用列級安全性。

## <a name="disabling-security"></a>停用安全性
我們假設您的組織想要限制資料存取。 如果由於某種原因在執行成本會計時停用了安全參數，則擁有者必須將使用者新增到 Power BI 中的 **成本會計師** 角色。 如果您將安全性從啟用狀態更改為停用狀態，最好將使用者從 **成本物件控制器** 角色移除。 如果您重新啟用安全性，反之亦然。 使用者可以同時屬於這兩個角色。 聯合存取是兩個角色的結合。 對於 **成本會計分析** Power BI 內容，具有聯合存取權限的使用者可以不受限制地存取資料。 如果您的目標是套用受限存取，則使用者必須僅指派給 **成本物件控制器** 角色。 這些列級安全更新會立即生效。 受影響的使用者應該重新整理他們的瀏覽器。

## <a name="additional-resources"></a>其他資源
若要進一部了解 Power BI 列級安全性，請參閱[在 Power BI 的模型上管理安全性](https://powerbi.microsoft.com/documentation/powerbi-admin-rls/#manage-security-on-your-model)。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]