---
title: 對發包電子採購使用外部目錄
description: 本主題說明如何使用外部目錄來建立和提交申請。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b236a17a7f93bfeb60d64fa25745bd1b4cb1b34b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449067"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a>對發包電子採購使用外部目錄

[!include [banner](../includes/banner.md)]

透過對發包電子採購使用外部目錄，您不必在自己的主資料中維護有關廠商產品的資訊。 相反，廠商網站上的購物車將轉換為具有正確產品資訊的申請行。 

您應該避免在自己的產品主資料中維護廠商產品的描述和價格。 相反，應對發包電子採購使用外部目錄。 然後，當員工建立申請時，他們可以「發包」到廠商的外部目錄網站 (換句話說，他們會離開您的系統並前往廠商的網站)。 然後可以將新增到廠商網站上購物車的產品轉換為申請行。 因此，您將獲得正確的產品資訊：產品識別碼、名稱、價格等。

若要使用外部目錄，員工必須在 **我的採購申請** 頁面見利申請。

建立申請的員工稱為申請準備者。 作為準備者，您可以完成以下工作。

使用 **外部目錄** 行動作打開頁面，該頁面包含可用於指定申請者、採購法律實體和接收營運單位的所有外部目錄。

根據您的權限，變更申請者、購買法律實體和接收營運單位。 變更這些值可能會變更申請者可用的外部目錄清單。 可用的外部目錄取決於採購法律實體或接收營運單位的目前有效採購原則。 這些原則可以允許或阻止存取特定採購類別。 因此，對應到這些採購類別的外部目錄清單可能會受到影響。

有關原則的更多資訊，請參閱[採購原則概觀](../procurement/purchase-policies.md)。

- 若要尋找特定採購類別的外部目錄，請在目錄搜尋欄位中輸入文字。
- 若要從廠商網站上的廠商外部目錄新增產品，請點選外部目錄。 然後將產品新增到購物車，然後結帳。購物車行將轉移到 Microsoft Dynamics 365。

如果有多個採購類別選項，請在將行新增到申請之前，選擇正確的採購類別。
將行新增到申請後，不使用外部目錄也可以新增更多行。 或者，您可以繼續使用外部目錄來新增行。

申請準備就緒後，使用 **工作流程** > **提交** 動作提交以供核准。

### <a name="additional-resources"></a>其他資源

- [設定 PunchOut 電子採購的外部目錄](set-up-external-catalog-for-punchout.md)
- [採購 cXML 增強功能](purchasing-cxml-enhancements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]