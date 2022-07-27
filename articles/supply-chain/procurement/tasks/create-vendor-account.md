---
title: 建立廠商帳戶
description: 此程序說明如何建立廠商帳戶並新增地址和連絡資訊。
author: Henrikan
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16abc34b881fffdb9f278fd097efbcdc693b235f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448299"
---
# <a name="create-a-vendor-account"></a>建立廠商帳戶

[!include [banner](../../includes/banner.md)]

此程序說明如何建立廠商帳戶並新增地址和連絡資訊。 此程序並未說明如何填入採購和財務相關的所有欄位。 若要進一步了解這些欄位，請閱讀欄位的說明。 您可用示範資料公司 USMF 或自己的資料來使用此程序。 廠商帳戶通常由採購專業人員或應收帳款相關人員建立。


## <a name="create-a-vendor-account"></a>建立廠商帳戶
1. 移至 **瀏覽窗格 > 模組 > 採購及開源 > 廠商 > 所有廠商**。
2. 按一下 **新增**。
3. 在 **廠商帳戶** 欄位中，輸入一個值。
    - 該值可能會自動填入。 若已自動填入，請跳過此步驟。  
    - 您可為個人或組織建立廠商帳戶。 這會影響所提供的欄位。 在此範例中，我們將為組織建立廠商帳戶。   
4. 在 **名稱** 欄位中，輸入或選擇一個值。 若您的廠商是系統內已註冊的合作對象，則可從此欄位的下拉式功能表中選擇，而新的廠商帳戶將繼承已註冊的地址和連絡資訊。
5. 在 **群組** 欄位中，輸入或選擇一個值。 廠商群組可依據下列參數將廠商分組：付款條件、結算期、庫存過帳的分類帳科目 (含銷售稅群組、預設分類帳科目、產品篩選代碼或供應預測設定)。
6. 在 **員工數目** 欄位中，輸入一個數字。
7. 在 **組織編號** 欄位中，輸入一個值。

## <a name="add-an-address"></a>新增地址
1. 展開 **地址** 區段。
2. 按一下 **新增**。
3. 在 **目的** 欄位中，輸入或選擇一個值。 您可選擇一或多個目的。 這些目的係用於選擇正確的地址。 例如，若目的是「請款」，則您傳送的發票就會使用該地址。
4. 在 **名稱或描述** 欄位中，輸入一個值。
5. 在 **國家/地區** 欄位中，輸入或選擇一個值。 輸入地址詳細資料。 依據您選擇的國家/地區，將顯示與該國家/地區地址格式相符的欄位。 
6. 按一下 **確定**。

## <a name="add-contact-information"></a>新增連絡資訊
1. 展開 **連絡資訊** 區段。
2. 按一下 **新增**。
3. 在 **描述** 欄位中，輸入一個值。
4. 在 **類型** 欄位中，選擇一個選項。
5. 在 **連絡電話/地址** 欄位中，輸入一個值。 若這是主要連絡人，您可選擇主要核取方塊。  
6. 按一下 **儲存**。
7. 關閉頁面。
8. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]