---
title: Base64StringToContainer ER 函數
description: 本主題提供有關如何使用 Base64StringToContainer 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/14/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 3e813c628bfe783fb8e93fc5d7e8b275405245c42710f9ea691d4c06afff0d84
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460553"
---
# <a name="base64stringtocontainer-er-function"></a>Base64StringToContainer ER 函數

[!include [banner](../includes/banner.md)]

`BASE64STRINGTOCONTAINER` [函數](er-formula-language.md#Functions)將 *字串* 類型的指定輸入轉換為 *[容器](er-functions-category-container.md)* 類型的資料項。

## <a name="syntax"></a>語法

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a>引數

`input`：*字串*

*字串* 類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*容器*

以二進位大物件 (BLOB) 格式產生的二進位值。

## <a name="usage-notes"></a>使用方式說明

如果輸入字串未提供正確的 Base64 組二進位到文字編碼方案，則會引發「參數無效」異常。

## <a name="example"></a>範例

您在模型對應中定義以下資料來源：

- *Dynamics 365 for Operations/列舉* 類型的根 **DocuTypeGroupEnum** 資料來源，指的是 **DocuTypeGroup** 應用程式列舉
- 參考 **CustTable** 應用程式表的 *Dynamics 365 for Operations/資料表記錄* 類型的根 **客戶** 資料來源
- *匯出欄位* 類型的 **\#Media** 資料來源，設定方式如下：

    - 它被新增為 **客戶** 資料來源的子資料來源。
    - 它包含運算式 `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`。

- *匯出欄位* 類型的 **\#MediaAsBase64String** 資料來源，設定方式如下：

    - 它被新增為 **Customer.'\#Media'** 資料來源的子資料來源。
    - 它包含運算式 `Customer.'#Media'.'getFileContentAsBase64String()'`。

- *匯出欄位* 類型的 **\#BlobFomBase64** 資料來源，設定方式如下：

    - 它被新增為 **Customer.'\#Media'** 資料來源的子資料來源。
    - 它包含運算式 `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`。

在這個範例中，**\# MediaAsBase64String** 資料來源將現行媒體附檔的二進位內容編碼為表示 Base64 組二進位到文字編碼方案的文字。 **\#BlobFomBase64** 資料來源解碼 Base64 字串並回傳 BLOB 格式的二進制值。

![在 ER 模型對應設計工具頁面上的樣本資料來源。](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a>其他資源

[容器函數](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
