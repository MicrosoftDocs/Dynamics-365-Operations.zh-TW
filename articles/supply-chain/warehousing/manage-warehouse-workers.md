---
title: 管理倉庫工作人員
description: 本文說明如何使用 Warehouse Management mobile app 來協助控制和監控倉庫中員工執行的工作。
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, InventLocation, WHSLaborStandards, WHSWorker, WHSWorkTable, WHSWorkTableListPage, WHSResetUserPassword
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72891
ms.assetid: feaa6f15-49d2-41f5-9b87-453463c52e4e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a3261571f7ba43a79ee42afd8cdfe9b69cb83c01de3e4b2b89d2b0aae668ea2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447087"
---
# <a name="manage-warehouse-workers"></a>管理倉庫工作人員

[!include [banner](../includes/banner.md)]

本文說明如何使用 Warehouse Management mobile app 來協助控制和監控倉庫中員工執行的工作。

若您正使用倉庫管理的此功能，則所有倉庫工作人員的作業皆稱為 *工作*。 揀料、移動和盤點現有庫存的工作，都會以行動裝置加以記錄。 倉庫工作人員可執行工作前，工作必須與人力資源中的工作人員建立關聯。 每個 **工作人員** 帳戶可有多個相關聯的倉庫工作使用者。 這些工作使用者可在不同的倉庫工作，對行動裝置功能表的存取級別可能也不一樣。 您可將倉庫工作使用者視為所選工作人員多次登入。 每個工作使用者都有預設倉庫，而該工作使用者能取得的功能表項目會提供特定工作流程。 

若要建立新的工作使用者，在 **倉庫** 區段 **一般** 索引標籤的 **工作人員** 頁面中，按一下 **工作人員**。 您必須指定使用者識別碼、使用者名稱、預設倉庫和功能表名稱。 使用者登入倉庫行動裝置入口網站時會載入此功能表，而您可定義使用者能存取的功能表項目。 

為每個工作使用者的設定過程中，您也可定義特定的處理工作流程。 例如，您可使用 **是否為週期盤點主管** 欄位，指定該使用者在盤點作業期間能否處理週期盤點差異的調整，或指定這類調整是否必須先經過另一名人員審核。

## <a name="defining-labor-standards"></a>定義勞動標準
**勞動標準** 頁面可讓您定義系統估算特定工作類型所需時間的計算方法。 可針對通用層級或特定層級設定此定義。 例如，您可針對特定揀貨流程，定義特定單位每個重量單位的銷售訂單揀料所需的處理時間。 同時，您也可採用另一種計算方法，記錄所揀的現有庫存放置作業的時間。 

若要啟用您定義的勞動標準，您必須選取勞動標準適用的每個倉庫的 **允許勞動標準** 選項。

## <a name="monitoring-and-controlling-warehouse-work"></a>監控與控制倉庫工作
**所有工作** 頁面可讓您監控並維護所有已計劃、正在進行和已完成的工作。 在此頁面中，您可更新各種流程，例如倉庫工作使用者指派和工作優先順序。 您亦可深入瞭解工作標題和工作明細的相關詳細資料，進一步掌握預期或已完成的工作流程。 

若您啟用 **勞動標準** 選項，則可檢視估算出來的工作時間。 然後，處理工作時，也會顯示每個工作實際的作業時間。 如此一來，您可比較估算時間和實際時間。 

此外，建立工作時，自動分割工作的規則也能套用估算時間。 如此一來，即可依據任務完成的預期時間來載入其餘工作。 

工作項目處理的時間分析有助於改善倉庫工作人員的效率。 以下報告可用於輔助此分析：

-   **使用者的勞動** – 此報告會依據實際時間與預期時間的比較，呈現工作人員生產力。
-   **工作交易類型的勞動** – 您可使用此報告來調查特定倉庫流程效率低落問題。 例如，您發現轉移訂單揀貨作業本週花費的時間較前幾週長。 此時即可使用此資訊來進一步調查。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]