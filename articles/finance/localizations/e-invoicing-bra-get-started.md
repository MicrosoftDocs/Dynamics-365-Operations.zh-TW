---
title: 開始使用巴西的電子發票
description: 本主題提供的資訊，將幫助您在 Finance and Supply Chain Management 中開始使用巴西的電子發票。
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 82bbf806d207af0b15406e4bec516420db7f2c06
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451437"
---
# <a name="get-started-with-electronic-invoicing-for-brazil"></a>開始使用巴西的電子發票 

[!include [banner](../includes/banner.md)]

本主題提供的資訊將幫助您在開始使用巴西的電子發票。 本主題將引導您完成 Regulatory Configuration Services (RCS) 中與國家/地區有關的設定步驟，並補充[開始使用電子發票](e-invoicing-get-started.md)主題中描述的步驟。

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>巴西 NF-e (BR) 電子發票功能的特定國家/地區特定設定

**巴西 NF-e (BR) 電子發票功能** 的部分參數使用預設值發佈。 在將電子發票功能部署到服務環境之前，請查看這些值，並在必要時更新這些值以更好地反映您的商業營運。

本節補充了 [開始使用電子發票](e-invoicing-get-started.md)主題中的 **電子發票功能的國家/地區特定設定** 章節。

1. 在 RCS 中 **全球化功能** 工作區的 **功能** 區段中，選擇 **電子發票** 圖格。
2. 在 **電子發票功能** 頁面，驗證是否選擇了您建立的 **巴西 NF-e (BR)** 電子發票功能。
3. 在 **版本** 索引標籤，驗證是已選擇 **草稿** 版本。
4. 在 **設定** 索引標籤的格線中，選擇 **提交**，然後選擇 **編輯。**
5. 在 **動作** 索引標籤的 **動作** 欄位群組，選擇 **(預覽) 簽署 xml 文件** 動作。
6. 在 **參數** 欄位群組，選擇 **憑證名稱**，並在 **值** 欄位中，輸入與您的 Key Vault 參數關聯的憑證名稱。
7. 在 **動作** 索引標籤的 **動作** 欄位群組，選擇 **(預覽) 呼叫巴西 SEFAZ 服務** 動作。
8. 在 **參數** 欄位群組，選擇 **URL 地址** 參數。
9. 在 **值** 欄位，如有必要，請查看並更新您所在州的 SEFAZ 文件所發布的 Web 服務的 URL，然後選擇 **儲存。**
10. 在 **適用性規則** 索引標籤的 **適用性規則設定** 欄位群組，查看 **州** 欄位，並根據需要針對與 Web 服務 URL 所參考的相同州對其進行更新。
11. 選取 **儲存**，然後關閉此頁面。
12. 要將電子發票功能部署到服務環境，請參閱[開始使用電子發票](e-invoicing-get-started.md)。

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>巴西 NF-e (BR) 電子發票功能應用程式設定的特定國家/地區特定設定

在將應用程式設定部署到 Finance 或 Supply Chain Management 連接的應用程式之前，請完成以下步驟。

本節補充了 [開始使用電子發票](e-invoicing-get-started.md)主題中的 **應用程式設定的國家/地區特定設定** 章節。

1. 在 RCS 中 **全球化功能** 工作區的 **功能** 區段中，選擇 **電子發票** 圖格。
2. 在 **電子發票功能** 頁面，驗證是否選擇了 **巴西 NF-e (BR)** 電子發票功能。
3. 在 **版本** 索引標籤，驗證是已選擇 **草稿** 版本。
4. 在 **設定** 索引標籤，選擇 **應用程式設定**，並且在 **已連接的應用程式** 欄位中，選擇要部署到的應用程式。
5. 在 **資料表名稱** 欄位，驗證是否選擇了 **會計單據標題**。
6. 選擇 **回應類型**，然後選擇 **新增**。
7. 在 **回應類型** 欄位中，輸入「回應」作為固定值，然後在 **描述** 欄位中，輸入「描述」。
8. 請在 **提交狀態** 欄位，選取 **待處理**。
9. 在 **模型對應** 欄位，選擇 **(預覽) 回應訊息匯入格式** 的 **來自回應訊息的模型對應**，然後選擇 **儲存**。
10. 選取 **新增**，在 **回應類型** 欄位中，輸入「ResponseData」作為固定值，然後在描述欄位中，輸入 **描述**。
11. 請在 **提交狀態** 欄位，選取 **待處理**。
12. 在 **模型對應** 欄位，選擇具有 **(預覽) NF-e 回應資料匯入格式 (BR)** 的 **回應資料匯入**，然後選擇 **儲存**。
13. 要將應用程式設定部署到 Finance 或 Supply Chain 連接的應用程式，請參閱[開始使用電子發票](e-invoicing-get-started.md)。

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>巴西 NFS-e ABRASF 庫里奇巴 (BR) 電子發票功能的特定國家/地區特定設定

**巴西 NFS-e ABRASF 庫里奇巴 (BR) 電子發票功能** 的部分參數使用預設值發佈。 在將電子發票功能部署到服務環境之前，請查看這些值，並在必要時更新這些值以更好地滿足您的商業營運需求。

本節補充了 [開始使用電子發票](e-invoicing-get-started.md)主題中的 **電子發票功能的國家/地區特定設定** 章節。

1. 在 RCS 中 **全球化功能** 工作區的 **功能** 區段中，選擇 **電子發票** 圖格。
2. 在 **電子發票功能** 頁面，驗證是否選擇了您建立的 **巴西 NFS-e ABRASF 庫里奇巴 (BR)** 電子發票功能。
3. 在 **版本** 索引標籤，驗證是否選擇了 **草稿** 版本，然後在 **設定** 索引標籤的格線中，選擇 **提交**。
4. 選擇 **編輯**，並在 **動作** 索引標籤的 **動作** 欄位群組中，選擇第一個出現的 **(預覽) 簽署 xml 文件**。
5. 在 **參數** 欄位群組，選擇 **憑證名稱**。
6. 在 **值** 欄位，輸入與您的 Key Vault 參數關聯的憑證名稱。
7. 在 **動作** 欄位群組，選擇第二個出現 **(預覽) 簽署 xml 文件**。
8. 在 **參數** 欄位群組，選擇 **憑證名稱**。
9. 在 **值** 欄位，輸入與您的 Key Vault 參數關聯的憑證名稱。
10. 在 **動作** 索引標籤的 **動作** 欄位群組，選擇 **(預覽) 呼叫巴西 SEFAZ 服務** 動作。
11. 在 **參數** 欄位群組，選擇 **URL 地址** 參數。
12. 在 **值** 欄位，如有必要，請查看並更新庫里奇巴市稅務部門所發佈的 Web 服務的 URL，然後選擇 **儲存。**
13. 在 **設定** 索引標籤的格線中，選擇 **查詢**，然後選擇 **編輯。**
14. 在 **動作** 索引標籤的 **動作** 欄位群組，選擇 **(預覽) 呼叫巴西 SEFAZ 服務** 動作。
15. 在 **參數** 欄位群組，選擇 **URL 地址** 參數。
16. 在 **值** 欄位，如有必要，請查看並更新庫里奇巴市稅務部門所發佈的 Web 服務的 URL。
17. 請選取 **儲存**，然後關閉此頁。
18. 要將電子發票功能部署到服務環境，請參閱[開始使用電子發票](e-invoicing-get-started.md)。

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>巴西 NFS-e ABRASF 庫里奇巴 (BR) 電子發票功能應用程式設定的特定國家/地區特定設定

在將應用程式設定部署到 Finance 或 Supply Chain Management 連接的應用程式之前，請完成以下步驟。

本節補充了 [開始使用電子發票](e-invoicing-get-started.md)主題中的 **應用程式設定的國家/地區特定設定** 章節。

1. 在 RCS 中 **全球化功能** 工作區的 **功能** 區段中，選擇 **電子發票** 圖格。
2. 在 **電子發票功能** 頁面，驗證是否選擇了 **巴西 NFS-e ABRASF 庫里奇巴 (BR)** 電子發票功能。
3. 在 **版本** 索引標籤，驗證是否選擇了 **草稿** 版本，然後在 **設定** 索引標籤中，選擇 **應用程式設定**。
4. 在 **已連接的應用程式** 欄位，選擇要部署的應用程式。
5. 在 **資料表名稱** 欄位，驗證是否選擇了會計單據標題。
6. 選擇 **回應類型**，然後選擇 **新增**。
7. 在 **回應類型** 欄位中，輸入「ABRASFCuritibaSubmitResponse」作為固定值，然後在 **描述** 欄位中，輸入「描述」。
8. 請在 **提交狀態** 欄位，選取 **待處理**。
9. 在 **模型對應** 欄位，選擇具有 **(預覽) NFS-e ABRASF 庫里奇巴回應資料匯入 (BR)** 的 **回應資料匯入**，然後選擇 **儲存。**
10. 選取 **新增**，在 **回應類型** 欄位中，輸入「ABRASFCuritibaSubmitResponseData」，然後在 **描述** 欄位中，輸入「描述」。
11. 請在 **提交狀態** 欄位，選取 **待處理**。
12. 在 **模型對應** 欄位，選擇具有 **(預覽) NFS-e ABRASF 回應資料匯入格式 (BR)** 的 **回應資料匯入**，然後選擇 **儲存**。
13. 選取 **新增**，在 **回應類型** 欄位中，輸入「ABRASFCuritibaInquireResponse」，然後在描述欄位中，輸入 **描述**。
14. 請在 **提交狀態** 欄位，選取 **待處理**。
15. 在 **模型對應** 欄位，選擇具有 **(預覽) NFS-e ABRASF 庫里奇巴回應資料匯入 (BR)** 的 **回應資料匯入。**
16. 選取 **儲存**，然後關閉此頁面。
17. 要將應用程式設定部署到 Finance 或 Supply Chain 連接的應用程式，請參閱[開始使用電子發票](e-invoicing-get-started.md)。

## <a name="privacy-notice"></a>隱私權注意事項
啟用 **NF-e Federal - 巴西電子發票 (BR)** 和 **NFS-e - 巴西服務 (城市) 電子發票** 功能可能需要發送有限的資料，包括組織稅務登記識別碼。 該資料被傳輸到稅務機關授權的第三方機構，以便以與政府網路服務整合所需的預定義格式向該稅務機關發送電子發票。 作為管理員，您可以啟用或關閉 **NF-e 聯邦 - 巴西電子發票 (BR)** 和 **NFS-e - 巴西服務 (城市) 電子發票** 功能。 以下步驟說明如何執行此操作： 

1. 前往 **組織管理** > **設定** > **電子文件參數**。 
2. 在 **功能** 索引標籤，選擇包含 **NF-e 聯邦 - 巴西電子發票 (BR)** 或 **NFS-e - 巴西服務 (城市) 電子發票** 功能的行，然後選擇相應的功能。 從這些外部系統匯入此 Dynamics 365 線上服務的資料受[隱私權聲明](https://go.microsoft.com/fwlink/?LinkId=512132)約束。 有關詳細資訊，請查閱特定國家/地區特定功能文件中的「隱私權聲明」區段。

## <a name="additional-resources"></a>其他資源

- [電子發票概觀](e-invoicing-service-overview.md)
- [開始使用電子開票服務管理](e-invoicing-get-started-service-administration.md)
- [開始使用電子開票](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
