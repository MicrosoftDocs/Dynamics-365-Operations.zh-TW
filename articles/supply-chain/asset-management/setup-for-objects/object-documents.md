---
title: 資產文件
description: 本主題介紹資產管理中的資產文件。
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectDocument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77b7265b1ba56dbd1cd955f5d90afea02f589ce2eebdd05a2fef3a7ddebc0ee1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446715"
---
# <a name="asset-documents"></a>資產文件

[!include [banner](../../includes/banner.md)]

 

本主題介紹資產管理中的資產文件。

在資產管理中您可以設定文件，例如讓文件自動與作業類型、資產製造商、資產類型或資產相關聯。 此功能在發佈已更新文件版本時很有用。 在這種情況下，您只需將更新後的文件放在您用於 Supply Chain Management 文件的標準位置，並將文件附加到您已建立的資產文件記錄。 之後便可以從 **所有資產**、**使用中資產**、**我的使用中資產**、**所有工單** 和 **使用中工單作業** 功能表項目存取更新後的文件。 將文件附加到資產文件記錄的過程使用標準文件處理系統。

**範例 1：** 與作業類型相關的文件可描述該作業類型的程序。

**範例 2：** 與資產類型、製造商和模型組合相關的文件可能是所選資產製造商模型的標準手冊。

## <a name="create-asset-document-relation"></a>建立資產文件關係

1. 選取 **資產管理** \> **設定** \> **資產文件**。
2. 選取 **新增** 建立資產文件記錄。
3. 根據您想要的文件關係具體程度，在以下的一或多個欄位中進行相關選擇：**資產類型**、**製造商**、**模型**、**資產**、**作業類型類別**、**作業類型**、**作業類型變體** 和 **作業需求**。 **作業類型變體** 與 **作業需求** 欄位中的可用選項取決於您在 **作業類型** 欄位中的選擇。

    > [!NOTE]
    > 當系統搜尋應該與資產或工單相關的文件時，資產管理會檢查所有資產文件記錄以檢查可能的符合項目。 一律先檢查最具體的組合。 換句話說，資產管理會先檢查 **作業需求** 欄位的符合項目。 如果沒有找到符合項目，它會檢查 **作業類型變體** 欄位的符合項目。 如果沒有找到符合項目，它會檢查 **作業類型** 欄位的符合項目，依此類推。 正如您在 **資產管理** 頁面的配置中所見，此行為意味著為了找到最具體的組合，資產管理會從右到左檢查每條記錄以找出符合項目。 多個文件可能與資產或工單相關。 您可以根據需要編輯維護要求或工單的服務層級。

4. 選取 **附件**。 標準 **文件處理** 頁面隨即出現。
5. 設定應附加到資產文件記錄的文件或註解。 附加文件後，**附件** 欄位會顯示與記錄相關的文件數目。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]