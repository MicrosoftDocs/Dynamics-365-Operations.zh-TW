---
title: 在服務訂單新增地址
description: 本主題介紹如何將客戶地址新增到服務訂單。
author: kamaybac
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 055903628b2d72f420415bae5c72d0c7d9d57cba
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448608"
---
# <a name="add-an-address-to-a-service-order"></a>在服務訂單新增地址    

[!include [banner](../includes/banner.md)]


本主題介紹如何將客戶地址新增到服務訂單。 建立服務訂單時，從服務訂單附加到的專案中地址資訊會傳輸出來。 但是，您可以從已輸入到 Microsoft Dynamics AX 的地址中，選擇客戶、供應商、站點、倉庫、服務訂單和專案的替代位置。

您也可以建立一個新地址。 預設情況下，新地址會傳輸到專案中。 但是，您可以指定新地址僅與此服務實例相關。 如果這樣做，新地址不會傳輸到專案中。

## <a name="create-a-customer-address-for-a-service-order"></a>為服務訂單建立客戶地址

若要將地址新增到服務訂單，請執行以下步驟：

1.  點選 **服務管理** \> **常用** \> **服務訂單** \> **服務訂單**。

2.  打開要建立地址的服務訂單。

3.  在 **動作窗格**，按一下 **編輯**，然後按一下 **標頭檢視表**。

4.  在 **地址** 快速索引標籤，按一下 **新增地址**。

5.  在 **新地址** 表單，輸入地址的唯一名稱並填寫其他欄位。 
    

    > [!WARNING]
    > <P>如果您輸入的名稱與現有地址相同，您在其他欄位中輸入的資訊將覆蓋該現有地址的資訊。</P>


6.  按一下 **確定** 將新地址複製到您的服務訂單中。

## <a name="specify-an-alternative-address-on-a-service-order"></a>在服務訂單上指定替代地址

若要將替代地址新增到服務訂單，請執行以下步驟：

1.  點選 **服務管理** \> **常用** \> **服務訂單** \> **服務訂單**。

2.  打開要輸入替代地址的服務訂單。

3.  在 **動作窗格**，按一下 **編輯**，然後按一下 **標頭檢視表**。

4.  在 **地址** 快速索引標籤，按一下 **其他地址**。

5.  在 **地址選擇** 表單，在 **記錄類型** 欄位，選取 **服務訂單**。

6.  選取地址，然後按一下 **確定** 將其複製到您的服務訂單中。


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]