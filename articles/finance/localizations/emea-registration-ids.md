---
title: 登記識別碼
description: 本主題提供有關設置和使用登記 ID 的資訊。
author: ShylaThompson
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.reviewer: kfend
ms.custom: 264824
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 544e994a18811995afc64c052a3f97e622529162b8a14b17206c370026b78ac4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450888"
---
# <a name="registration-ids"></a>登記識別碼

[!include [banner](../includes/banner.md)]

本主題提供有關設置和使用登記 ID 的資訊。

許多國家和地區對記錄登記號或 ID 有不同的規定和要求。 本主題概述了不同歐洲國家/地區的各方所需的設置和支持的登記類型的處理。 所有國家/地區都有支持與不同州辦事處提供的登記號相關的各種國家特定功能的要求。 登記號的示例包括社會安全號 (SSN)、稅號 (TIN) 和歐洲增值稅標識 (EU VAT ID)。 此功能為所有地區的所有國家/地區提供統一的框架，同時考慮到一些歐洲國家/地區的特定國家/地區要求。 以下部分描述了用於設置和處理登記 ID 的整體資訊流。

## <a name="registration-type-creation"></a>登記類型建立
在輸入登記 ID 之前，您必須為每一方所使用的不同類型的登記號設置登記類型。 前往 **組織管理**&gt;**全球通訊錄**&gt;**登記類型**&gt;**登記類型** 頁面為不同國家/地區的供應商、客戶、工人和法人實體創建和管理登記類型。

|欄位                 |描述      |
|------------------------------|----------------------------|                                                                           
| 姓名                | 登記類型的名稱。 |                                                                           
| 描述         | 登記類型的描述。 |
| 國家/地區      | 國家/地區的唯一識別碼。|
| 稅務機關       | 與登記類型關聯的稅務機關。|
| 限制範圍       | 適用於稅務登記類型的限制類型：無、個人、組織。|
| 格式              | 登記類型的驗證格式。|
| 可更新      | 定義登記類型的登記號在輸入後是否可以更新。|
| 獨特              | 定義登記類型的登記號是否唯一。 |
| 國家/地區的主要項目 | 如果一方與特定國家/地區的一個或多個地址相關聯，並且登記 ID 對所有這些地址都有效，則您必須指定一個地址作為該國家/地區的主要地址。 您只能將一個 ID 登記為主 ID。 定義是否只能為主要國家地址輸入登記號。 |

## <a name="assign-a-registration-type-to-a-registration-category"></a>將登記類型分配給登記類別
登記類別是國家/地區登記標識符，允許在特定國家/地區用於稅收、海關和其他目的。 此類別定義了特定登記 ID (包括校驗位等) 的驗證規則，並在不同的報告中包含登記 ID。 使用頁面 **組織管理**&gt;**全球通訊錄**&gt;**登記類型**&gt;**登記類別** 將特定國家的登記類型分配給支持的登記類別。

| 欄位            | 描述|
|-----------------------|----------------|
| 登記類型     | 特定國家/地區的登記類型。|
| 限制範圍         | 適用於稅務登記類型的限制類型：無、個人、組織。|
| 登記類別 | 批准在該國使用的唯一登記標識符。 支持的類別的完整列表將在本主題後面顯示。 |

## <a name="enter-registration-ids-for-global-address-book-records"></a>輸入全局地址簿記錄的登記 ID

全球地址簿 (GAB) 包含客戶、供應商、聯繫人、業務關係和法人實體的綜合地址資訊。 如需更多資訊，請參閱[全球通訊錄概覽](../../fin-ops-core/fin-ops/organization-administration/overview-global-address-book.md)。 存儲在全局地址簿中的當事人記錄可以包含一個或多個地址記錄。 這些地址用於不同的目的，例如計費或交付。 您可以為客戶、供應商、工人和法人實體的地址資訊設置登記 ID。 找到要為其輸入登記 ID 的當事人 (法人、供應商、客戶、工人) 記錄，然後點擊 **登記 ID** 在與當事人、法人實體、供應商、客戶、工人相關的表格上打開 **管理地址** 頁。 在 **稅務登記** 選項卡，點擊 **新增**，然後輸入有關登記 ID 的以下資訊。


|欄位                |描述                                                |
|---------------------|-----------------------------------------------------------|
| 登記類型   | 所選國家/地區的登記類型。     |
| 登記號碼 | 派對登記 ID。                                |
| 描述         | 登記編號的描述。               |
| 區段             | 登記編號的相關附加資訊。 |
| 核發機構      | 提供登記編號的機關。        |
| 核發日期         | 登記號碼的核發日期。              |
| 生效           | 登記號碼的核發日期。           |
| 到期          | 登記號碼的到期日。          |

> [!NOTE]
> 可以從與增值稅號相關的登記號中選擇法人、供應商、客戶的免稅編號並為該方輸入。

## <a name="search-for-records-by-registration-id"></a>按登記 ID 搜尋記錄
可在與當事人、法人實體、供應商、客戶和工人相關的表單上搜尋基於登記 ID 的當事人記錄。 點擊 **登記 ID 搜尋** 打開 **登記 ID 搜尋條件** 頁。 指定搜尋條件並點擊 **尋找**。 系統將顯示從全局通訊錄中選擇的記錄和相關的當事人記錄類型。

## <a name="supported-registration-categories"></a>支持的登記類別
下表列出了支持的登記類型。 如果你熟悉 Microsoft Dynamics AX 2012 年登記 ID 欄位，此表還將這些欄位映射到 Dynamics 365 Finance 登記類別。

| 財務登記類別         |國家/地區  | 動力學 AX 2012 條款/欄位|
|---------------------------------------------------------------|---------------------|---------------------------------|
| VAT 識別碼                                                        | 歐盟 (EU) 所有國家|  免稅編號 (立法類型 TAX ID 在 AX 2012 R3)|
| 企業識別碼 (COID)                                          | 比利時捷克愛沙尼亞匈牙利拉脫維亞立陶宛波蘭瑞士 | 企業號 (EnterpriseNumber) 登記號 (RegNum\_W) 登記號 (RegNum\_W) 登記號 (RegNum\_W) 登記號 (RegNum\_W) 企業代碼(EnterpriseCode) 登記號(RegNum\_W) UID (立法類型的 UID 在 AX 2012 R3) |
| 分支識別碼                                                     | 比利時            | 分行代號 (BranchNumber)|
| Spisová značka (登記號、發行機構、科目) | 捷克共和國     | 插圖編號 (CommercialRegisterInsetNumber) 保存在商業登記處 (CommercialRegister) 商業登記處 (CommercialRegisterSection)|
| 關稅客戶識別碼                                           | 芬蘭 | 自訂客戶號碼 (CustomsCustomerNumber\_FI)|
| INN                                                           | 俄羅斯聯邦| INN (立法型 INN 在 AX 2012 R3)|
| RRC                                                           | 俄羅斯聯邦| RRC (立法型 RRC 在 AX 2012 R3)|
| OKDP                                                          | 俄羅斯聯邦| OKDP (立法型 OKDP 在 AX 2012 R3)|
| OKPO                                                          | 俄羅斯聯邦| OKPO (立法型 OKPO 在 AX 2012 R3)|
| RCOAD                                                         | 俄羅斯聯邦| RCOAD (立法類型 RCOAD 在 AX 2012 R3)|
| OGRN                                                          | 俄羅斯聯邦| OGRN (立法型 OGRN 在 AX 2012 R3) |
| 尼爾斯                                                         | 俄羅斯聯邦| SNILS (立法類型 SNILS 在 AX 2012 R3)|
| 商品交易會                                                         | 俄羅斯聯邦| CIFTS (立法型 CIFTS 在 AX 2012 R3)|
| 護照                                                      | 西班牙             | 護照|
| 官方識別資訊文件                              | 西班牙             | 官方識別資訊文件|
| 居住地憑證                                         | 西班牙             | 居住地憑證|
| 其他識別資訊文件                                 | 西班牙             | 其他識別資訊文件|
| 未普查                                                  | 西班牙             | AX 2012 R3 無法使用|


有關登記 ID 處理的更多資訊，包括所需的先決條件，請參閱 Lifecycle Services (LCS) 中增值稅 ID 的以下任務記錄：

-   設定加值稅識別碼
-   廠商加值稅識別碼的登記
-   使用加值稅識別碼搜尋當事人






[!INCLUDE[footer-include](../../includes/footer-banner.md)]