---
title: 過帳定義
description: 本主題提供有關過帳定義，及如何定義和連結它們的資訊。 針對支援的過帳類型和文件，您可以使用過帳定義而不是過帳設定檔，分類會計分錄上的主科目和財務維度。
author: kweekley
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d409f154823a74e032adb71253ce97f8e3b2f101
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2021
ms.locfileid: "8451131"
---
# <a name="posting-definitions"></a>過帳定義

[!include [banner](../includes/banner.md)]

本主題提供有關過帳定義，及如何定義和連結它們的資訊。
針對支援的過帳類型和文件，您可以使用過帳定義而不是過帳設定檔，分類會計分錄上的主科目和財務維度。 您可以在 **交易過帳定義** 頁上檢視佐證文件和過帳類型。 

若要開始使用過帳定義，請選取 **總帳參數** 頁上的 **使用過帳定義** 選項。 即使當您使用過帳定義，您仍然必須為原始分錄和不支援的過帳類型和文件定義過帳設定檔。 

您必須使用過帳定義才能啟用訂購單的保留會計和採購取得的預保留會計。

## <a name="defining-posting-definitions"></a>定義過帳定義
使用 **過帳定義** 頁指明相配標準並定義相配時應該產生的分錄。 相配標準經評估為會計分配的原始分錄。 

您也可以在 **過帳定義** 頁面上指派分錄明細的優先順序編號，以便控制評估明細的順序。 優先編號最低的明細會先評估。 例如，優先級 1 的所有明細全部評估，接著是優先級 2 的明細，依此類推。 找到相配項目時會忽略其他相配標準。 此外，只有群組中與原始交易相配的群組才會建立產生的分錄。 

您可以使用 **測試過帳定義** 精靈驗證您的過帳定義。 待您定義過帳定義的範例原始分錄後，您將看見產生的分錄。 

您可以連同生效日期與過帳定義版本一起使用。 例如，您可以建立過帳定義的未來版本，以便在新會計年度過帳到不同分類帳科目。 

使用 **交易過帳定義** 頁面指派過帳定義給交易類型。

## <a name="linking-posting-definitions"></a>連結過帳定義
當您建立過帳定義時，您可以從一個過帳定義連結到另一個。 除了目前過帳定義的標準以外，您連結到的定義標準日後也會納入考慮。 此項功能有助於節省您的時間，因為如果您已經為另一個定義輸入那些明細，您不必再到 **過帳定義** 頁的 **分錄** FastTab 上針對目前過帳定義重新輸入標準。 

示意圖或表格包括您可能使用的任何連結。 為了避免與目前過帳定義發生衝突，請確定您連結的任何過帳定義明細都是唯一的。 

建立過帳定義連結時適用的限制如下：

-   已佑過帳定義可連結另一個過帳定義或從另一個過帳定義連結過來，但不是同時連結。 不過，過帳定義可連結多個過帳定義。
-   您只能相同模組的過帳定義之間設定連結。
-   您可以將過帳定義指派給任何交易類型，但交易類型必須與過帳定義在相同模組裡。 使用 **交易過帳定義** 頁面查看交易類型所在的模組。


更多資訊，請參閱[過帳定義範例](example-posting-definitions.md)。 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
