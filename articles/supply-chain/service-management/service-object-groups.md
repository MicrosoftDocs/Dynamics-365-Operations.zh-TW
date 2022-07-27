---
title: 服務物件群組
description: 物件群組可用於排序和篩選報告和統計物件的資料。
author: kamaybac
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bfee8bacbf9c62950ff45b90d19258516ec20b20
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448164"
---
# <a name="service-object-groups"></a>服務物件群組

[!include [banner](../includes/banner.md)]

物件群組可用於排序和篩選報告和統計物件的資料。 例如，您可以按地理位置或按類型對物件進行分組。

## <a name="group-by-geographical-location"></a>按地理位置分組

您可以使用此分組方法來顯示您公司服務的各種不同物件的位置。 例如，如果您必須確定公司已在特定國家/地區為其提供服務的物件，則按地理位置對物件進行分組也很實用。

## <a name="example-of-grouping-by-geographical-location"></a>按地理位置分組的範例

來自比利時的客戶致電您的服務中心，並希望為物件 ABC 建立服務合約。 將地理位置為比利時的物件群組附加到比利時中服務的所有物件。 使用此群組當作篩選，您可以快速搜尋以查看計劃中是否已經有 ABC 的記錄，或者是否必須設定新物件。

## <a name="group-by-type"></a>按類型分組

您可以使用此分組方法來顯示您公司服務物件的類型。 例如，如果您想根據計劃中已經存在的類似物件建立一個新物件，則按類型對物件進行分組也很有用。

## <a name="example-of-grouping-by-type"></a>按類型分組的範例

一位客戶致電並希望為空調機 HIJ 建立服務合約。 您還沒有這台機器的記錄。 但是，您已經設定了一個名為「空調」的物件群組，並且您已將該組附加到所有空調物件。 因此，您可以快速搜尋和識別所有其他空調機，並使用來自這些物件的範本資訊為 HIJ 建立服務合約行。 透過以這種方式使用物件群組，您可以快速設定新物件並確定必須對其執行的服務任務。

## <a name="create-service-object-groups"></a>建立服務物件群組

建立您可以將服務物件指派到的群組。 服務物件是對其執行服務的庫存品項和其他產品。 透過對服務物件進行分組，您可以為相似和相關的服務物件建立報表。 例如，一個服務物件群組可能包含兩個服務物件：一個服務物件是套件，第二個服務物件是安裝套件的服務。

若要建立服務物件群組，請執行以下步驟：

1. 點選 **服務管理 > 設定 > 服務物件 > 服務物件群組**。

2. 點選 **新增** 來建立新的服務物件群組。

3. 輸入服務物件群組的唯一名稱，也可選擇輸入描述。

使用 **服務物件** 表單，您可以將服務物件指派給群組。 

## <a name="see-also"></a>另請參閱

[建立服務物件](create-service-objects.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]