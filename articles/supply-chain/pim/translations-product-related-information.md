---
title: 產品相關翻譯常見問題集
description: 本主題介紹如何管理產品、產品維度值和產品屬性的翻譯。
author: t-benebo
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysTranslationDetail, SysTranslationLanguage, SysTranslationList, EcoResProductListPage, EcoResProductVariants, EcoResProductDetailsExtended, EcoResProductCreate, EcoResProductDetails, RetailSizeGroupTable, RetailStyleGroupTable, RetailColorGroupTable, PCTranslationLanguageLookup, EcoResProductCategory
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201853
ms.assetid: c0286bba-f54b-42de-904c-81fd796bdd1d
ms.search.region: global
ms.search.industry: Product information
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24a341973b8648b1a697c8c07b6ecbc808e0e504
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448317"
---
# <a name="product-related-translations-faq"></a>產品相關翻譯常見問題集

[!include [banner](../includes/banner.md)]

本主題介紹如何管理產品、產品維度值和產品屬性的翻譯。 

## <a name="what-product-related-data-can-be-translated"></a>可以翻譯哪些產品相關資料？

您可以為以下產品相關資訊建立翻譯：
-   產品名稱和描述。
-   產品屬性值的描述、自訂名稱和說明文字。
-   產品維度值的名稱和描述。

您可以將產品相關資訊翻譯成任何可用的語言 **文字翻譯** 頁面。 有關詳細資訊，請參閱以下部分 **如何為產品相關資訊建立翻譯**。

## <a name="where-can-i-view-the-translated-information"></a>在哪裡可以查看翻譯後的資訊？
您可以在任何外部來源文件 (例如發票) 中查看產品相關資訊的翻譯，該文件會使用可提供翻譯的語言。

## <a name="how-do-i-create-translations-for-product-related-information"></a>我要如何建立產品相關資訊翻譯？
若要為產品建立翻譯，請執行以下步驟：
1.  點擊 **產品資訊管理** &gt; **常見** &gt;**已發佈產品**。
2.  選擇一個產品，然後在動作窗格中的 **語言** 分組，點擊 **翻譯**。
3.  在 **文字文本翻譯** 頁面中，在 **語言** 欄位，選擇一種語言。 若要新增更多語言，請展開 **語言** 欄位，然後點擊 **好的**。
4.  在 **翻譯文字** 群組中的 **描述** 和 **產品名稱** 欄位中輸入翻譯。

若要為產品屬性建立翻譯，請執行以下步驟：
1.  點擊 **產品資訊管理** &gt; **常見** &gt;**已發佈產品**。
2.  在 **設定** 下方，點擊 **屬性**，然後點擊 **屬性**。
3.  在 **屬性** 頁面中，點擊 **翻譯**。
4.  在 **文字文本翻譯** 頁面中，在 **語言** 欄位，選擇一種語言。 若要新增更多語言，請展開 **語言** 欄位，然後點擊 **好的**。
5.  在 **翻譯文字** 群組中的 **描述**、**自訂名稱** 和 **說明文字** 欄位中輸入翻譯。

若要為產品維度值建立翻譯，請執行以下步驟：
1.  點擊 **產品資訊管理** &gt; **常見** &gt;**已發佈產品**。
2.  選擇產品，然後點擊 **產品尺寸**。
3.  選擇產品尺寸的連結之一：**設定**、**尺寸**、**顏色** 或 **風格**。
4.  選擇一個維度值，然後點擊 **翻譯**。
5.  在 **文字文本翻譯** 頁面中，在 **語言** 欄位，選擇一種語言。 若要新增更多語言，請展開 **語言** 欄位，然後點擊 **好的**。
6.  在 **翻譯文字** 群組中的 **名稱** 和 **描述** 欄位中輸入翻譯。

## <a name="can-the-names-of-product-variants-be-translated"></a>產品種類的名稱可以翻譯嗎？
產品種類會基於已發布產品的尺寸。 產品種類名稱以維度值組合為基礎。 翻譯與產品種類相關聯的維度值時，產品種類的名稱會出現在翻譯後的版本中。  

**範例**  

您的產品是一件 T 恤，有不同的尺寸和顏色，款式名稱基於下列詳細資訊：
-   產品編號：\#3
-   尺寸：尺寸和顏色
-   尺寸維度值：小、中、大
-   顏色維度值：紅色、綠色、黑色

基於維度值小和紅色的產品種類的名稱是 **\#3：小：紅色**。  

客戶想要購買一些小的紅色 T 恤，且 T 恤的名稱必須以法語出現在發票上。 您將尺寸值小和紅色翻譯成法語，產品種類的名稱會是 **\#3:Petit:Rouge**。
<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>提示</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>若要設定客戶的偏好語言，請執行以下步驟：
<ol><br/><li>點擊<strong>銷售和行銷</strong>&gt;<strong>常見的</strong>&gt;<strong>顧客</strong>&gt;<strong>全部</strong><strong>顧客</strong>.</li>
<li>雙擊客戶開啟<strong>客戶</strong>頁面。 在<strong>一般</strong>索引標籤上，在<strong>語言</strong>欄位中選擇<strong>語言</strong>。</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="what-happens-if-a-customer-has-a-preferred-language-for-which-no-translations-are-available"></a>如果客戶的偏好語言沒有可用的翻譯，會發生什麼情況？
如果沒有客戶偏好語言的翻譯，名稱和描述將以您自己公司的全球語言顯示。

## <a name="can-i-manage-translations-for-a-series-of-dimension-values-at-the-same-time"></a>我可以同時管理一系列維度值的翻譯嗎？
維度值是特定於產品的，您可以管理各產品的維度值翻譯。 但是，如果您建立維度值組並為值組中的值建立翻譯，則更容易管理翻譯。   

**範例**  

貴公司生產不同款式的 T 恤，每種款式都有小、中和大的尺寸可供選擇。 尺寸會收集在一維值組中。 新增 T 恤款式時，您可以將其與用於尺寸的維度值組關聯，讓產品的所有尺寸都可用。 您也可以隨時新增或變更維度值組中尺寸的翻譯。  

透過維度種類組與產品關聯的維度值必須從產品種類組進行維護。   
若要建立維度值組，請按照以下步驟：
1.  點擊 **產品資訊管理** &gt; **設定**&gt;**種類組**。
2.  選擇 **尺寸組**、**顏色組**，或 **樣式組**。
3.  點擊 **新增**，然後在 **尺寸組**、**顏色組** 或 **樣式組** 欄位。 點擊 **尺寸**、**顏色** 或 **樣式** 為群組建立行。
4.  在 **尺寸組行**、**顏色組行**，或 **樣式組行** 頁面，點擊 **新增**，然後為群組建立大小、顏色和樣式。

若要管理維度值組中值的翻譯，請執行以下步驟：
1.  依照先前建立維度值組的過程中的步驟打開 **尺寸組行**、**顏色組行** 或 **樣式組行** 頁面。
2.  點擊 **文字翻譯**。 在 **文字翻譯** 頁面中，在 **翻譯文字** 群組中，在 **名稱** 和 **描述** 欄位中輸入翻譯。

## <a name="when-can-translations-of-product-related-information-be-managed"></a>何時可以管理產品相關資訊的翻譯？
隨時可以管理產品相關資訊的翻譯。 當為與產品關聯的維度值更新翻譯時，無論產品是否具有交易記錄，產品資訊都會更新。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]