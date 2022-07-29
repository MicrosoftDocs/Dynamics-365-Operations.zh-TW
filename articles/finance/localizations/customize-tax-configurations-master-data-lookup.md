---
title: 自訂主資料查詢的稅務設定
description: 本主題說明如何自訂稅務設定以擴充主資料查詢功能。
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 498201d5c0377058e86b25953ebbe401ae1af9e3
ms.sourcegitcommit: ed43ceae9b2ef3f616b81127bcf4c4b0862e23f5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2021
ms.locfileid: "8451110"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>自訂主資料查詢的稅務設定

[!include [banner](../includes/banner.md)]

遵循本主題中的步驟，以自訂稅務設定來擴充主資料查詢功能。

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>匯入 Microsoft 提供的稅務設定

1. 在 Regulatory Configuration Service (RCS) 的 **電子報告** 工作區中，選擇 **Microsoft** 設定提供者。
2. 選擇 **存放庫**。
3. 選擇 **全域**，然後選擇 **打開**。
4. 選擇稅務設定，例如 **稅務計算設定**，然後，在 **版本** 索引標籤上選擇一個版本。
5. 選取 **匯入**。

> [!NOTE]
> 預設情況下，將匯入 Dataverse 模型對應。 如果您在設定匯入流程中收到警告訊息，請在 Dataverse 中啟用虛擬實體。 如需更多資訊，請參閱[啟用 Dataverse 虛擬實體](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md)。

## <a name="create-a-customized-data-model-configuration"></a>建立自訂資料模型設定

1. 在 **電子報告** 工作區，選擇 **稅務設定**，然後選擇要擴充的資料模型設定。 例如，選擇 **稅務計算資料模型**。
2. 選取 **建立設定**。
3. 選擇 **衍生自名稱的應稅單據模型：稅務計算資料模型，Microsoft**。
4. 在 **名稱** 欄位中，輸入 **自訂資料模型**。
5. 選取 **建立設定**。

## <a name="create-customized-reference-models"></a>建立自訂參考模型

1. 在 **稅務設定** 頁面，選擇 **自訂資料模型**，然後選擇 **設計工具**。
2. 選擇省略符號按鈕 (**...**)，然後選擇 **參考模型** 檢視表。

    [![參考模型。](./media/pic2.png)](./media/pic2.png)

3. 建立自訂參考模型。 自訂模型是根模型。 自訂實體是一個記錄清單。 自訂欄位是您要在查詢中使用的字串欄位。 您可以根據需要新增其他欄位。
4. 選擇省略符號按鈕 (**...**)，然後選擇 **應稅單據** 檢視表。
5. 選擇要繫結到自訂參考模型的屬性。 例如，選擇 **自訂屬性**，然後按照以下步驟操作：

    1. 選擇 **選擇參考模型**。
    2. 選擇 **自訂模型**，然後選擇 **確定**。 參考模型名稱將更新為 **自然索引鍵** 欄位的值。

        [![選擇參考模型對話方塊。](./media/pic5.png)](./media/pic5.png)

    3. 選擇 **儲存**，然後選擇 **完成**。

## <a name="create-a-customized-model-mapping-configuration"></a>建立自訂模型對應設定

1. 在 **電子報告** 工作區，選擇 **稅務設定**，然後選擇 **Dataverse 模型對應** 設定。
2. 在 **模型對應的預設值** 欄位中選擇 **否**。
3. 選取 **建立設定**。
4. 選擇 **衍生自名稱的應稅單據模型對應：Dataverse 模型對應，Microsoft**。
5. 在 **名稱** 欄位中，輸入 **自訂模型對應**。
6. 在 **目標模型** 欄位中，選取 **自訂資料模型** 資料模型。
7. 選取 **建立設定**。

    [![建立設定下拉式對話方塊。](./media/pic6.png)](./media/pic6.png)

8. 選擇 **自訂模型對應**，將 **連接的應用程式** 欄位設定為在[設定用於主資料尋找的環境](tax-service-set-up-environment-master-data-lookup.md)的步驟 8 中建立的連接。
9. 將 **模型對應的預設值** 欄位設定為 **是**。

## <a name="create-customized-model-mappings"></a>建立自訂模型對應

1. 在 **稅務設定** 頁面，選擇 **自訂模型對應**。
2. 選擇 **設計工具**，然後選擇 **自訂模型**。

    [![自訂模型。](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>將模型對應對應到 Dataverse 實體

1. 在 **模型對應設計工具** 頁面，選擇 **自訂模型**，然後選擇 **設計工具**。
2. 在 **資料來源類型** 樹狀圖中，選取 **Dataverse 資料表**。
3. 在 **資料來源** 索引標籤中，選取 **新增根**。
4. 在 **名稱** 欄位中，輸入 **自訂 Dataverse**。
5. 在第二個 **名稱** 欄位，選擇一個實體。
6. 選取 **確定**。

    [![資料表資料來源屬性對話方塊。](./media/pic9.png)](./media/pic9.png)

7. 選擇 **自訂 Dataverse** 和 **自訂實體**，然後選擇 **繫結**。

    [![自訂 Dataverse 和自訂實體繫結。](./media/pic10.png)](./media/pic10.png)

8. 在 **自訂 Dataverse** 和 **自訂欄位** 下，選擇欄位，然後選擇 **繫結**。

    [![自訂 Dataverse 和自訂欄位繫結。](./media/pic11.png)](./media/pic11.png)

9. 選擇 **儲存**，然後選擇 **完成**。

## <a name="create-a-customized-tax-configuration"></a>建立自訂稅務設定

1. 在 **電子報告** 工作區，選擇 **稅務設定**，然後選擇 **稅務計算設定**。
2. 選取 **建立設定**。
3. 選擇 **衍生自名稱的稅務服務設定：稅務計算設定，Microsoft**。
4. 在 **名稱** 欄位中，輸入 **自訂設定**。
5. 選取 **建立設定**。
6. 選擇 **自訂設定**，然後選擇 **設計工具**。
7. 在 **資料模型** 欄位中，選取 **自訂資料模型**。
8. 在 **資料模型版本** 欄位內，選擇相應資料模型版本。

    [![屬性區段。](./media/pic13.png)](./media/pic13.png)

9. 選取 **完成**。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
