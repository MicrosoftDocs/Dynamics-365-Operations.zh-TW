---
title: 建立範本 BOM
description: 您有多種方法來建立範本 BOM。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c10bf5e758a1752e1c50c602db85e0c53ee3e662
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448419"
---
# <a name="create-a-template-bom"></a>建立範本 BOM   

[!include [banner](../includes/banner.md)]


您可使用下列任一方法來建立範本 BOM。 在所有方法中，**開始日期** 和 **結束日期** 欄位皆為選填，僅供參考。

## <a name="create-a-template-bom-manually"></a>手動建立範本 BOM

1.  移至 **服務管理** \> **設定** \> **服務物件** \> **範本 BOM**。

2.  選擇 **新增** 以開啟 **建立範本 BOM** 表單。

3.  在 **從參考複製 BOM 明細** 底下，選擇 **手動** 選項。

4.  在 **項目編號** 欄位中，輸入該類型 **BOM** 的項目。

5.  在 **名稱** 欄位中，輸入範本的名稱。

6.  在 **開始日期** 和 **結束日期** 欄位中，輸入範本 BOM 處於使用中的日期範圍。

7.  選擇 **確定**。

將建立新的空白範本 BOM。

## <a name="create-a-template-bom-based-on-another-template-bom"></a>以另一範本 BOM 為基礎來建立範本 BOM

1.  選擇 **服務管理** \> **設定** \> **服務物件** \> **範本 BOM**。

2.  選擇 **新增** 以開啟 **建立範本 BOM** 表單。

3.  在 **從參考複製 BOM 明細** 底下，選擇 **範本 BOM** 選項。

4.  在 **參考編號** 欄位中，選擇現有範本 BOM，將之複製到新的範本 BOM。

5.  在 **名稱** 欄位中，輸入範本的名稱。

6.  在 **開始日期** 和 **結束日期** 欄位中，輸入範本 BOM 處於使用中的日期範圍。

7.  選擇 **確定**。

將建立新的範本 BOM，其中的明細會與原始範本 BOM 明細一致。

## <a name="create-a-template-bom-based-on-an-item-bom"></a>以項目 BOM 為基礎來建立範本 BOM

1.  選擇 **服務管理** \> **設定** \> **服務物件** \> **範本 BOM**。

2.  選擇 **新增** 以開啟 **建立範本 BOM** 表單。

3.  在 **從參考複製 BOM 明細** 底下，選擇 **BOM**。

4.  在 **參考編號** 欄位中，選擇 BOM 版本。 該類型 BOM 的項目會複製到 **項目編號**。

5.  在 **名稱** 欄位中，輸入範本的名稱。

6.  在 **開始日期** 和 **結束日期** 欄位中，輸入範本 BOM 處於使用中的日期範圍。

7.  選擇 **確定**。

將建立新的範本 BOM，其中的明細會與 **物料清單** 列出的 BOM 明細一致。

## <a name="create-a-template-bom-based-on-a-production-bom"></a>以生產 BOM 為基礎來建立範本 BOM

1.  選擇 **服務管理** \> **設定** \> **服務物件** \> **範本 BOM**。

2.  選擇 **新增** 以開啟 **建立範本 BOM** 表單。

3.  在 **從參考複製 BOM 明細** 底下，選擇 **生產**。

4.  在 **參考編號** 欄位中，選擇生產 BOM。

5.  在 **名稱** 欄位中，輸入範本的名稱。

6.  在 **開始日期** 和 **結束日期** 欄位中，輸入範本 BOM 處於使用中的日期範圍。

7.  選擇 **確定**。

將建立新的範本 BOM，其中的明細會與 **BOM** 列出的 BOM 明細一致。

## <a name="see-also"></a>另請參閱

[範本 BOM](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]