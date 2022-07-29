---
title: 新增位置與合作對象關係類型
description: 本主題說明如何新增位置與合作對象關係類型。
author: ShivamPandey-msft
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: a69ace892c55948305419a089cb91ac5b1e3c066177f8ce2ca441f1dd01c2af0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450294"
---
# <a name="add-location-and-party-relationship-types"></a>新增位置與合作對象關係類型 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a>新增位置角色

新增地址和聯絡資訊的位置角色有下列兩種方：

-  透過 **地址和聯絡資訊用途** 頁新增。 新角色將以類型 = 0 儲存到 **LogisticsLocationRole** 資料表，表示此角色並非在 **LogisticsLocationRoleType** 列舉及其擴充項目定義的系統角色。 使用者建立地址或聯絡資訊時將可以使用此角色。

    ![地址和內容資訊用途。](media/Address-Contact.PNG)

-  新增到 **LogisticsLocationRoleType** 列舉擴充項目，讓它經由資料庫同步流程填滿。

    1.  建立擴充項目到 **LogisticsLocationRoleType** 列舉並在擴充裡新增角色。 
  
        ![LogisticsLocationRoleType 列舉的擴充。](media/Logistics.PNG)

    2. 為新角色建立新資源檔案，接著為其屬性指派一值。
     
     ![新資源檔案。](media/Resource.PNG)
        
    3.  建立資料填滿類並提供處理常式填滿新角色。 

        ![資料填寫。](media/Dirdata.PNG)

    4.  若要測試填寫新位置角色情況，您可以建立可執行類，並且呼叫 Main() 裡的 DirDataPopulation::insertLogisticsLocationRoles()。 此道流程完成後，您應該會看到類型 \>0，的 **LogisticsLocationRole** 資料表所填滿的新角色。 新角色將在 **地址和聯絡資訊用途** 頁上顯示。

        ![插入新位置。](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a>新增合作對象關係類型 

新增關係類型有兩種方法：

-   透過 **關係類型** 頁新增。 新關係將儲存到 systemtype = 0 的 **DirRelationshipTypeTable**。

    ![關係類型。](media/Relationship.PNG)

-  新增到 **DirSystemRelationshipType** 列舉擴充，讓它經由資料庫同步流程填滿。

    1.  建立 **DirSystemRelationshipType** 列舉擴充並新增關係類型。

    2. 針對此新類型建立初始工具。 您可以在核心代碼找到幾個範例，其中一個是 **DirRelationshipTypeChildInitialize**。 這是合作對象關係類型 "子系" 的初始化工具類。 您可以藉由複製和貼上此代碼開始初始化程序，然後更新重點標示的區域。
    
    ![DirRelationshipChild 初始化工具。](media/DirRelationship.PNG)

    3.  若要測試填寫新關係類型，您可以建立可執行類，並且呼叫 Main() 裡的 ::insertDirRelationshipTypes()。 您應該看到 **DirRelationshipTypeTable** 的新關係類型，而新關係類型將在 **關係類型** 頁開放使用。

        ![可執行類。](media/Runnable.PNG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]