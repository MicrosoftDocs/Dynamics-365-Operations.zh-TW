---
title: 使用電子發票開立服務匯入廠商發票
description: 本主題概述如何使用電子開票服務匯入廠商發票。
author: gionoder
ms.date: 09/03/2021
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
ms.openlocfilehash: c28adbfe532e77a52cab7625b9539d1e8e528bea
ms.sourcegitcommit: 19f0e69a131e9e4ff680eac13efa51b04ad55a38
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/22/2022
ms.locfileid: "8451404"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>使用電子發票開立服務匯入廠商發票

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

本主題提供的資訊將協助您開始使用電子開票服務匯入廠商發票。 引導您完成 Regulatory Configuration Services (RCS)、Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management 中的設定步驟，您必須遵循才能從廠商處接收電子廠商發票。

## <a name="set-up-vendor-invoice-import-in-rcs"></a>在 RCS 中設定廠商發票匯入
要在 RCS 中設定廠商發票匯入，請執行以下步驟：

1. 查閱[公開發佈的電子開票功能](e-invoicing-configuration-rcs.md#generally-available-features)清單。
2. 選擇並匯入電子開票功能。 有關詳細信息，請參閱從 [Microsoft 設定提供者匯入電子開票功能](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider)。
3. 為您的組織建立電子開票功能。 有關詳細資訊，請參閱[在您的組織提供者下建立電子開票功能](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider)。

## <a name="configure-an-email-account-channel"></a>設定電子郵件帳戶通道

如果您建立的電子開票功能從透過電子郵件接收的附件文件中匯入電子廠商發票，請設定電子郵件帳戶通道。

1. 在 RCS 中，選擇您建立的電子開票功能。 確保選擇狀態為 **草稿** 的版本。
2. 在 **設定** 索引標籤的格線中，選擇功能設定，然後選擇 **編輯**。
3. 在 **資料通道** 索引標籤中的 **參數** 欄位群組，在 **資料通道** 欄位，輸入通道的名稱。 通道名稱不應超過十個字元。
4. 在 **伺服器位址** 欄位中，輸入電子郵件帳戶提供者。 例如，**https://outlook.live.com/** 的伺服器位址為 **imap-mail.outlook.com**。
5. 在 **伺服器連接埠** 欄位中，輸入電子郵件帳戶提供者使用的連接埠。 例如，**https://outlook.live.com/** 的伺服器連接埠為 **993**。
6. 在 **使用者名稱密碼** 欄位中輸入包含電子郵件使用者帳戶識別碼的金鑰存放庫密碼的名稱。 此密碼必須在 Azure Key Vault 中建立並在您的服務環境中設定。 
7. 在 **使用者密碼** 欄位中輸入包含電子郵件使用者帳戶密碼的金鑰存放庫密碼的名稱。
8. 選用 - 在 **寄件者篩選**、**主題篩選** 和 **日期篩選** 欄位中輸入值。
9. 輸入用於儲存郵件的信箱資料夾的名稱：

    - 匯入來源：**主資料夾**
    - 處理成功後儲存：**封存資料夾**
    - 處理失敗後儲存：**錯誤資料夾** 無須在信箱中建立這些資料夾。 首次匯入和處理電子發票時，將自動建立這些資料夾。 
   
10. 在 **附件篩選** 欄位群組，新增檔案篩選資訊。 只有滿足定義篩選的附件才會進行處理。 例如，您可以為副檔名為 xml 的附件設定 "\*.xml"。 設定期間 Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 中將使用附件名稱。 
11. 在 **適用性規則** 索引標籤，根據需要查看和更新條件。 **通道** 欄位必須等於之前提供的 **資料通道**。 更多資訊，請參閱[適用性規則](e-invoicing-configuration-rcs.md#applicability-rules)。
12. 選取 **儲存**，然後關閉此頁面。

### <a name="configure-a-microsoft-sharepoint-channel"></a>設定 Microsoft SharePoint 通道

如果電子開票功能從放置在SharePoint 資料夾中的文件匯入電子廠商發票，則設定 Microsoft SharePoint。

1. 在 RCS 中，選擇您建立的電子開票功能。 確定您選擇了狀態為 **草稿** 的 **版本**。
2. 在 **設定** 索引標籤的格線中，選擇功能設定，然後選擇 **編輯**。
3. 在 **資料通道** 索引標籤，在 **參數** 欄位群組，選擇 **SharePoint 地址** 並輸入 SharePoint URL。
4. 選擇 **伺服器連接埠** 並輸入電子郵件帳戶提供者使用的連接埠。
5. 選擇 **應用程式識別碼** 並輸入包含電子 SharePoint 用戶端識別碼的金鑰存放庫密碼的名稱。
6. 選擇 **應用程式密碼** 並輸入包含電子 SharePoint 用戶端密碼的金鑰存放庫密碼的名稱。
7. 選取 **檔案篩選**。 查看並更新遮罩以篩選包含要匯入的電子廠商發票的文件。
8. 在 **適用性規則** 索引標籤，根據需要查看和更新條件。 更多資訊，請參閱[適用性規則](e-invoicing-configuration-rcs.md#applicability-rules)。
9. 選取 **儲存**，然後關閉此頁面

### <a name="deploy-an-electronic-invoicing-feature"></a>部屬電子開票功能

若要部署電子開票功能，請參閱[將電子開票功能部署到服務環境](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment)。

## <a name="set-up-vendor-invoice-import-in-finance-or-supply-chain-management"></a>在 Finance 或 Supply Chain Management 中設定廠商發票匯入
完成以下兩個部分中的步驟以設定不同類型的廠商發票匯入。

### <a name="import-brazilian-nf-e-from-email"></a>匯入巴西 NF-e from 電子郵件

1. 登入 Finance 或 Supply Chain Management 環境，確認您位於正確的法律實體中。
2. 前往 **組織管理** > **設定** > **電子文件參數**。
3. 在 **功能** 索引標籤，確定已選取 **NF-e Federal - 巴西電子發票**。
4. 在 **外部通道** 索引標籤的 **通道** 欄位群組，選擇 **新增**。
5. 在 **通道** 欄位，輸入 **NFe** (在 RCS 中電子開票功能的資料通道設定中指定的通道名稱)。
6. 在 **描述** 欄位中，輸入描述。 在 **公司** 欄位中，選擇法律實體。
7. 在 **文件內容** 欄位，選擇 **會計文件內容 - 客戶發票內容模型**。
8. 在 **匯入來源** 欄位群組，選擇 **新增**。
9. 在 **名稱** 欄位中，輸入 **XmlFile** (在 RCS 中電子開票功能的資料通道設定中指定的 **附件篩選**)。
10. 在 **描述** 欄位中輸入描述，然後在 **資料實體名稱** 欄位，選擇 **已接收的 NF-e XML 文件**。
11. 在 **模型對應** 欄位，選擇 **NF-電子郵件匯入 - NF-電子郵件匯入 (BR)**，然後選擇 **儲存**。
12. 在 **電子文件** 索引標籤的 **電子報表** 欄位群組中，選擇 **新增**，並在 **資料表名稱** 欄位，選擇 **已接收的 NF-e XML 文件**。
13. 在 **文件內容** 欄位中，選擇 **查詢會計文件內容 - 客戶發票內容模型**。
14. 在 **電子文件模型對應** 欄位，選擇 **查詢對應 - 會計文件對應**。
15. 選擇 **回應類型**，然後選擇 **新增**。
16. 在 **回應類型** 欄位，輸入 **回覆**。 請在 **提交狀態** 欄位，輸入 **已排程**。
17. 在 **模型對應** 欄位中，選擇 **來自回應訊息的模型對應 - 回應訊息匯入格式**。
18. 請選取 **儲存**，然後關閉此頁。

### <a name="import-peppol-electronic-vendor-invoices"></a>匯入 PEPPOL 電子廠商發票

1. 前往 **電子報表** 工作區中，選擇 **報表設定**。
2. 選擇 **客戶發票內容模型**，然後選擇 **建立設定** > **從名稱衍生：客戶發票內容模型，Microsoft** 以建立衍生設定。
3. 在 **草稿** 版本中選擇 **設計工具**，然後在 **資料模型** 樹狀結構中選擇 **將模型對應到資料來源**。
4. 在 **定義** 樹狀結構中選擇 **資料通道**，然後選擇 **設計工具**。
5. 在 **資料來源** 樹狀結構，展開 **$Context\_Channel** 容器。 在 **值** 欄位選擇 **編輯**，然後輸入資料通道名稱。 這是在 RCS 中電子發票功能的資料通道設定中指定的通道名稱。 
7. 選取 **儲存**，然後關閉此頁面。
8. 關閉頁面。
9. 在 **客戶發票內容模型** 中選擇剛剛建立的衍生設定，然後在 **版本** FastTab 中選擇 **變更狀態** > **已完成**。
10. 前往 **組織管理** > **設定** > **電子文件參數**，然後在 **功能** 索引標籤，確定已選取 **PEPPOL 全域電子發票**。 
11. 在 **外部通道** 索引標籤的 **通道** 欄位群組中，選擇 **新增**。
12. 在 **通道** 欄位中輸入資料通道名稱，然後在 **描述** 欄位中輸入描述。
13. 在 **公司** 欄位中，選擇法律實體。 
14. 在 **文件內容** 欄位，從 **客戶發票內容模型** 中選擇新的衍生設定。 對應描述應為 **資料通道內容**。
15. 在 **匯入來源** 欄位群組，選擇 **新增**。
16. 在 **名稱** 欄位輸入 **附件篩選名稱**，然後在 **資料實體名稱** 欄位中選擇 **廠商發票標題**。
17. 在 **模型對應** 欄位，選擇 **廠商發票匯入 - 匯入廠商發票**。
18. 按一下 **儲存**，然後關閉此頁。


## <a name="receive-electronic-invoices"></a>接收電子發票

電子開票服務在從資料通道匯入發票期間執行兩個步驟：

1. 存取信箱並讀取電子郵件。
2. 處理電子郵件。 
    
要執行這兩個步驟，用戶端應為每個步驟手動呼叫該服務。 但是，建議您設定批次來接收電子文件。

要接收電子發票，請執行以下步驟：

1. 前往 **組織管理** > **定期** > **電子文件** > **接收電子文件**。
2. 選取 **確定**，然後關閉此頁。


## <a name="view-receive-logs-for-electronic-invoices"></a>查看電子發票的接收記錄

要查看電子發票的接收記錄，請前往 **組織管理** > **定期** > **電子文件** > **電子文件接收記錄**。
如果沒看到已成功處理的發票，請刪除資料表篩選。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
