---
title: 設定承運人燃料指數
description: 本指南介紹如何建立燃料指數區域、燃料指數和承運人燃料指數。
author: Henrikan
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b67219a6cb19b393dce25f77febc194c5ea2a16
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448887"
---
# <a name="set-up-a-carrier-fuel-index"></a>設定承運人燃料指數

[!include [banner](../../includes/banner.md)]

本指南介紹如何建立燃料指數區域、燃料指數和承運人燃料指數。 燃料指數區域指定燃料指數應套用至哪個區域，燃料指數指定特定時間期間的燃料價格。 為了反映燃料價格隨時間的變化，可將多個燃料指數與一個承運人相關聯。  這些工作通常由運輸協調員完成。 您可使用示範資料公司 USMF 或自己的資料來執行此程序。


## <a name="create-a-fuel-index-region"></a>建立燃料指數區域
1. 移至運輸管理 > 設定 > 燃料指數 > 燃料指數區域。
    * 首先，您必須建立不同的區域，在這些區域中作業並計算不同的燃料附加費。  
2. 點選 [新增]。
3. 在 [區域] 欄位中，輸入一個值。
4. 在名稱欄位中，輸入一個值。
5. 點選 [儲存]。

## <a name="create-a-fuel-index"></a>建立燃料指數
1. 移至運輸管理 > 設定 > 燃料指數 > 燃料指數。
    * 對於您已設定的區域，需要輸入燃料的目前價格。  
2. 點選 [新增]。
3. 在區域欄位中，按一下下拉式按鈕開啟查詢。
4. 在列表中，按一下所選行中的連結。
5. 在 [每加侖價格] 欄位中，輸入一個數字。
6. 在 [生效開始日期和時間] 欄位中，輸入日期和時間。
7. 點選 [儲存]。

## <a name="create-a-carrier-fuel-index"></a>建立承運人燃料指數
1. 移至運輸管理 > 設定 > 燃料指數 > 承運人燃料指數。
2. 點選 [新增]。
3. 在「承運人燃料指數」欄位中，輸入一個值。
4. 在 [描述] 欄位中輸入一個值。
5. 點選 [新增]。
6. 在 [生效開始日期和時間] 欄位中，輸入日期和時間。
7. 在 [PRG 寄件人] 欄位中輸入一個數字。
    * 在此範例中，您可以將 [PPG 寄件人] 欄位設定為 1.95。  
8. 在 [PRG 收件人] 欄位中輸入一個數字。
    * 在此範例中，您可以將 [PPG 收件人] 欄位設定為 2。  
9. 在 [百分比] 欄位中，輸入一個數字。
    * 在此範例中，您可以將百分比設定為 3。  
10. 在 [貨幣] 欄位中，按一下下拉式按鈕開啟查詢。
11. 在清單中，尋找並選擇所需紀錄。
12. 在列表中，按一下所選行中的連結。
13. 點選 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]