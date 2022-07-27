---
title: 重複使用產品設定
description: 您可以指定要自動重複使用產品的現有設定。 然後，當使用者完成設定工作階段後，系統會驗證是否已經存在與使用者選擇相符的設定。 如果找到相符的設定，則重新使用設定識別碼、相應的物料清單 (BOM) 和途程。
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0898bd1832fa7007fc3aa265beee2e930f157a39
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449010"
---
# <a name="reuse-product-configurations"></a>重複使用產品設定

[!include [banner](../includes/banner.md)]

您可以指定要自動重複使用產品的現有設定。 然後，當使用者完成設定工作階段後，系統會驗證是否已經存在與使用者選擇相符的設定。 如果找到相符的設定，則重新使用設定識別碼、相應的物料清單 (BOM) 和途程。

## <a name="requirements-for-reusing-configurations"></a>重複使用設定的要求

若要讓設定可重複使用，您必須在 **產品設定模型詳細資料** 頁面上為元件和屬性指定以下資訊：

-   **元件和子元件** – 在 **一般** FastTab 的 **重複使用設定** 字段，選擇 **是的**.
-   **屬性** – 在 **屬性** FastTab 上選擇 **包含在重複使用中** 選項。 此選項僅在啟用相關元件以供重複使用時出現。 如果您不選擇任何要重複使用的屬性，則一律重複使該設定，而不管使用者在設定工作階段期間的選擇為何。 現有設定中的屬性值必須與使用者的選擇相符。 例如，如果使用者選擇 **藍色** 作為設定工作階段的顏色，系統會驗證元件的現有設定是否具有藍色。

## <a name="resetting-configuration-reuse"></a>重設設定重複使用
重設設定重複使用時，不再考慮先前建立的設定。 如果 BOM 或途程已變更，但未變更相關屬性，您可能要重設設定重複使用。 在元件的 **一般** FastTab 上重設設定重複使用。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]