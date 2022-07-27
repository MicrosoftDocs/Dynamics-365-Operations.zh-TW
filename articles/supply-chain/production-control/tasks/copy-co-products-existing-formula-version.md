---
title: 從現有配方版本複製副產品
description: 本程序說明如何將副產品從現有配方版本複製到已發佈產品的不同配方版本。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 527fd94613d53a3f0ae81834d5bdaad30dca2833
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449193"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a>從現有配方版本複製副產品

[!include [banner](../../includes/banner.md)]

本程序說明如何將副產品從現有配方版本複製到已發佈產品的不同配方版本。 前提條件是至少有一個與副產品相關的配方版本。 使用示範資料公司 USP2 建立本程序。


## <a name="find-a-released-product"></a>尋找已發佈的產品
1. 前往已發佈產品。
2. 按一下顯示篩選條件。
    * 您即將在篩選條件對話方塊中加入欄位生產類型。  
3. 按一下加入篩選條件欄位，加入欄位生產類型。
    * 在下一個步驟，您需要先在生產類型欄位中手動輸入配方，才能選擇套用。 這樣會在已發佈產品清單中設定篩選條件。  
4. 在生產類型欄位中手動輸入配方。
5. 按一下套用。

## <a name="select-a-released-product"></a>選擇已發佈產品
1. 在清單中，尋找並選擇所需紀錄。
2. 按一下配方版本。
    * 在工程動作窗格上，按一下配方版本。  

## <a name="copy-co-products"></a>複製副產品
1. 在動作窗格上，按一下配方版本。
2. 按一下副產品。
3. 按一下複製。
4. 在品項編號欄位中，輸入或選擇一個值。
5. 在公式版本欄位中，輸入或選擇一個值。
6. 按一下確定。
7. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]