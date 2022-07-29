---
title: 埃及電子開票
description: 本主題提供的資訊將幫助您在 Microsoft Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management 中開始使用埃及的電子開票。
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6fe1dd4254db8b390c17558320a6eaff2b0dcd19
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451665"
---
# <a name="electronic-invoicing-for-egypt"></a>埃及電子開票

[!include [banner](../includes/banner.md)]

本主題提供的資訊將幫助您在開始使用埃及的電子開票。 其為指導您完成 Regulatory Configuration Service (RCS) 中與國家/地區相關的設定步驟。 這些步驟補充了[設定電子開票](e-invoicing-set-up-overview.md)中描述的步驟。

## <a name="prerequisites"></a>先決條件

在開始本主題中的程序之前，請完成以下先決條件：

- 熟悉[電子開票概觀](e-invoicing-service-overview.md)中所述的電子開票。
- 註冊 RCS，並設定電子開票。 有關詳細資訊，請參閱下列主題：

    - [註冊並安裝電子開票服務](e-invoicing-sign-up-install.md)
    - [設定電子開票的 Azure 資源](e-invoicing-set-up-azure-resources.md)
    - [在 Lifecycle Services 中安裝微服務增益集](e-invoicing-install-add-in-microservices-lcs.md)
    
- 啟用您的 Microsoft Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 應用程式和電子開票服務之間的整合，如[啟用並設定與電子開票的整合](e-invoicing-activate-setup-integration.md)中所述。
- 在 Azure Key Vault 中建立數位憑證密碼，並按照中所述進行設定[客戶憑證和密碼](e-invoicing-customer-certificates-secrets.md)。 出於測試目的，埃及稅務機關提供了只能在測試和解決方案驗證階段使用的特定測試數位憑證。 有關更多資訊，請使用[埃及電子開票 SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/) 中提供的連結前往埃及稅務機關網站。

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-feature"></a>埃及電子發票 (EG) 功能的特定國家/地區特定設定

**埃及電子發票 (EG)** 電子發票功能的部分參數使用預設值發佈。 在將電子開票功能部署到服務環境之前，請查看預設值並根據需要進行更新，以便它們更好地反映您的業務作業。

1. 匯入最新版本的 **埃及電子發票 (EG)** 全球化功能，如[從全域存放庫匯入功能](e-invoicing-import-feature-global-repository.md)中所述。
2. 建立匯入的全球化功能的複本，並為其選擇設定提供者，如[建立全球化功能](e-invoicing-create-new-globalization-feature.md)中所述。
3. 在 **版本** 索引標籤，驗證是已選擇 **草稿** 版本。
4. 在 **設定** 索引標籤的格線中，選擇 **銷售發票衍生** 功能設定。
5. 選擇 **編輯**。
6. 在 **處理管道** 索引標籤的 **處理管道** 區段，選擇 **對埃及稅務機關的 json 文件簽署**。
7. 在 **參數** 區段，選擇 **憑證名稱**，然後選擇您建立的數位憑證的名稱。
8. 在 **處理管道** 區段，選擇 **與埃及 ETA 服務整合**。 對於兩次發生的此動作，請重複此步驟。
9. 在 **參數** 區段，選擇 **Web 服務 URL** 和 **登入服務 URL**。 然後檢閱 URL 參數。 要取得測試和生產 URL，請使用[埃及電子開票 SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/) 中提供的連結前往埃及稅務機關網站。
10. 選取 **儲存**，然後關閉此頁面。
11. 對 **專案發票衍生** 功能設定重複步驟 4 到 10。

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-application-setup"></a>埃及電子發票 (EG) 應用程式設定的特定國家/地區特定設定

您的 Finance 或 Supply Chain Management 環境中必須設定一些參數。 您可以在以下兩個位置之一完成此設定：

- 直接在您的 Finance 或 Supply Chain Management 環境中。 更多資訊，請參閱[設定墊子開票參數](e-invoicing-set-up-parameters.md)。
- 在 RCS 中。 在電子開票功能設定範圍內，您可以定義所有參數，然後在部署電子開票功能時將它們直接部署到您的 Finance 或 Supply Chain Management 環境中。

對於這兩個選項，參數是相同的。 如果您在電子開票服務中設定您的第一個功能，我們建議您按照以下步驟在 RCS 中設定參數，然後將它們部署到您連接的應用程式。

> [!NOTE]
> 某些電子開票功能版本可能包含一組預定義的 Finance 或 Supply Chain Management 應用程式特定參數。 在這種情況下，您應該驗證資料是否正確。 否則，請手動設定參數。

1. 找到您建立的 **埃及電子發票 (EG)** 全球化功能的複本。
2. 在 **版本** 索引標籤，驗證是已選擇 **草稿** 版本。
3. 在 **設定** 索引標籤，選擇 **應用程式設定**。
4. 在 **已連接的應用程式** 欄位，選擇要部署參數的應用程式。
5. 在 **電子文件類型** 頁面，選擇 **新增** 建立記錄。
6. 在 **表單名稱** 欄位，新增 **CustInvoiceJour**。
7. 在 **內容** 欄位，新增對 **客戶發票內容** 對應名稱的參考。 設定是 **客戶發票內容模型**。
8. 在 **電子文件對應** 欄位，新增對 **客戶發票** 對應名稱的參考。 設定為 **發票模型對應**。
9. 選擇 **儲存**。
10. 在 **回應類型** 頁面，選擇 **新增**。
11. 在 **回應類型** 欄位，輸入 **回覆**。
12. 在 **描述** 字段中，輸入 **處理回應**。
13. 請在 **提交狀態** 欄位，選取 **待處理**。
14. 在 **模型對應** 欄位，選擇 **回應訊息匯入**。 設定為 **埃及回應訊息匯入 (EG)**。
15. 選擇 **儲存**。
16. 選取 **新增**。
17. 在 **回應類型** 欄位，輸入 **ResponseData**。
18. 在 **描述** 字段中，輸入 **處理回應資料**。
19. 請在 **提交狀態** 欄位，選取 **待處理**。
20. 在 **資料實體名稱** 欄位，選擇 **SalesInvoiceHeaderV2Entity**。
21. 在 **模型對應** 欄位，選擇 **回應資料匯入**。 設定為 **埃及回應資料匯入格式 (EG)**。
22. 選取 **儲存**，然後關閉此頁面。
23. 關閉頁面。

要將功能部署到服務環境並將應用程式設定部署到 Finance 或 Supply Chain Management 連接的應用程式，請參閱[完成、發佈和部署全球化功能](e-invoicing-complete-publish-deploy-globalization-feature.md)

## <a name="privacy-notice"></a>隱私權注意事項

啟用 **埃及電子發票 (EG)** 功能可能需要發送有限的資料。 此資料包括組織的稅務登記識別碼。 該資料將傳輸到稅務機關授權的第三方機構，以與政府網路服務整合所需的預先定義格式向該稅務機關發送電子發票。 管理員可以前往 **組織管理** \> **設定** \> **電子文件參數** 啟用和停用該功能。 在 **功能** 索引標籤，選擇包含 **埃及電子發票 (EG)** 功能的行，然後進行適當的選擇。 從外部系統匯入此 Dynamics 365 線上服務的資料受[隱私權聲明](https://go.microsoft.com/fwlink/?LinkId=512132)約束。 有關詳細資訊，請參閱特定國家/地區的功能文件中的「隱私權聲明」區段。

## <a name="additional-resources"></a>其他資源

- [電子發票概觀](e-invoicing-service-overview.md)
- [開始使用電子開票服務管理](e-invoicing-get-started-service-administration.md)
- [開始使用電子開票](e-invoicing-get-started.md)
- [埃及的客戶電子開票](emea-egy-e-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
