---
title: 為維度式基準產品建立物料清單
description: 在本程序中，您應該已經完成了此八個記錄序列中的前 4 個指南。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f86625821f8a01a6d4949f9dca538a279f52ce9c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447837"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>為維度式基準產品建立物料清單

[!include [banner](../../includes/banner.md)]

在本程序中，您應該已經完成了此八個記錄序列中的前 4 個指南。 前 4 個記錄設定資料是完成此過程所需的必要項目。 建立此程序的示範資料公司為 USMF。 此工作通常由產品設計師處理。

## <a name="select-the-product"></a>選擇產品

1. 請前往 **產品資訊管理 \> 產品 \> 已發佈的產品**。
1. 在清單中，標記所選資料列。
    * 按此順序查找您在第一個工作指南中建立，透過具有維度式設定技術的已發佈基準產品。  
1. 在動作窗格上，選擇 **工程師**。
1. 選擇 **BOM 版本**。

## <a name="create-new-bom-and-bom-version"></a>建立新的 BOM 和 BOM 版本

1. 選擇 **新增**。
1. 選擇 **BOM 和 BOM 版本**。
1. 在 **名稱** 欄位中，輸入一個值。
    * 設定站點  
    * 在此程序中，我們不會為 BOM 設定特定站點。  
1. 選擇 **確定**。
1. 選擇 **新增**。
    * 在此過程中，我們將向 BOM 中新增四個行。 兩個行代表纜線選項，兩個行代表機櫃選項。  
1. 在清單中，標記所選資料列。
1. 在 **項目號碼** 欄位中，輸入或選擇一個值。
    * 選擇品項編號 A0001，HDMI 6' 電纜。  
1. 在 **設定群組** 欄位中，輸入或選擇一個值。
    * 按此順序選擇指南 4 中建立的纜線配置群組。  
1. 選擇 **新增**。
    * 選擇品項編號 A0002，HDMI 12' 電纜。  
1. 在清單中，標記所選資料列。
1. 在 **項目號碼** 欄位中，輸入或選擇一個值。
1. 在 **設定群組** 欄位中，輸入或選擇一個值。
    * 再次選擇纜線設定群組。  
1. 選擇 **新增**。
1. 在清單中，標記所選資料列。
1. 在 **項目號碼** 欄位中，輸入或選擇一個值。
    * 選擇品項編號 D0002 機櫃。  
1. 在 **設定群組** 欄位中，輸入或選擇一個值。
    * 為此 BOM 行選擇機櫃設定群組。  
1. 選擇 **新增**。
1. 在清單中，標記所選資料列。
1. 在 **項目號碼** 欄位中，輸入或選擇一個值。
    * 為最後一個 BOM 行選擇品項編號 M0007 StandardCabinet。  
1. 在 **設定群組** 欄位中，輸入或選擇一個值。
    * 為最後一個 BOM 行選擇機櫃設定群組。  

## <a name="approve-and-activate"></a>核准並啟用

1. 關閉頁面。
1. 選擇 **核准**。
1. 在 **核准者** 欄位中，輸入或選擇一個值。
1. 在 **您也想核准物料清單嗎？** 欄位中，選擇 *是*。
1. 選擇 **確定**。
1. 選擇 **啟用**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]