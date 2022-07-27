---
title: 建立服務物件關係
description: 本主題說明如何在服務合約和服務訂單中建立服務物件關係。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a558d513ba97d7df72ee785704b84dd38a5929b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448182"
---
# <a name="create-service-object-relations"></a>建立服務物件關係 

[!include [banner](../includes/banner.md)]


本主題說明如何在服務合約和服務訂單中建立服務物件關係。 建立服務物件關係時，該服務物件會與服務合約或服務訂單建立關聯。 客戶要求服務的項目若是服務物件，您可從服務物件關係清單中選擇該服務物件。

## <a name="create-a-service-object-relation-for-a-service-agreement"></a>在服務合約建立服務物件關係

請以下列步驟在服務合約中建立服務物件關係：

1.  按一下 **服務管理** \> **常用** \> **服務合約** \> **服務合約**。

2.  在 **服務合約** 清單中，選擇現有服務合約，或按一下 **新增** 來建立新的服務合約。

3.  在 **服務合約** 索引標籤 **動作窗格** 的 **服務合約** 表單中，於 **關係** 群組按一下 **服務物件**。

4.  在 **服務物件** 表單中，按一下 **新增**，然後為此服務合約選擇服務物件。

5.  若要將範本物料清單 (BOM) 指派給服務合約，按一下 **功能**，然後選擇 **附加範本 BOM**。 在 **選擇範本 BOM** 表單中，於 **範本 BOM** 欄位選擇範本。 

## <a name="create-a-service-object-relation-for-a-service-order"></a>在服務訂單建立服務物件關係

請以下列步驟在服務訂單中建立服務物件關係：

1.  點選 **服務管理** \> **常用** \> **服務訂單** \> **服務訂單**。

2.  在 **服務訂單** 清單中，選擇現有服務訂單，或建立新的服務訂單。

3.  在 **服務訂單** 索引標籤 **動作窗格** 的 **服務訂單** 表單中，於 **關係** 群組按一下 **服務物件**。

4.  在 **服務物件** 表單中，按一下 **新增**，然後為此服務訂單選擇服務物件。

5.  若要將範本 BOM 指派給服務合約，按一下 **功能**，然後選擇 **附加範本 BOM**。 在 **選擇範本 BOM** 表單中，於 **範本 BOM** 欄位選擇範本。 


## <a name="see-also"></a>另請參閱

[服務物件概述](service-objects.md)

[服務物件關係](service-object-relations.md)

[範本 BOM](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]