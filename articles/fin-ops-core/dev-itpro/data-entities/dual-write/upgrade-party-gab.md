---
title: 升級到合作對象和全球通訊錄模型
description: 本主題介紹如何將雙重寫入資料升級為合作對象和全球通訊錄模型。
author: RamaKrishnamoorthy
ms.date: 03/10/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 95d272d9076f1ab25230e4efa98e321bdd618062
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2022
ms.locfileid: "8460573"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>升級到合作對象和全球通訊錄模型

[!include [banner](../../includes/banner.md)]



[Microsoft Azure Data Factory 範本](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema)幫助您將以下現有資料以雙重寫入方式升級到合作對象和全球通訊錄模型：**客戶**、**聯絡人**，和 **廠商** 資料表，以及郵寄和電子郵件地址。

提供了以下三個 Data Factory 範本。 它們有助於調節來自財務和營運應用程式和客戶業務開發應用程式的資料。

- **[合作對象範本](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json) (將資料升級為雙重寫入 Party-GAB 結構描述/arm_template.json)** – 此範本有助於升級與 **客戶**、**聯絡人**，和 **廠商** 資料相關的 **合作對象** 和 **聯絡人** 資料。
- **[合作對象郵寄地址範本](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json) (將資料升級到雙重寫入 Party-GAB 結構描述/升級到合作對象郵寄地址 - GAB/arm_template.json)** – 此範本有助於升級與 **客戶**、**聯絡人**，和 **廠商** 資料相關聯的郵寄地址。
- **[合作對象電子郵件地址範本](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json) (將資料升級到雙重寫入 Party-GAB 結構描述/升級到合作對象電子郵件地址 - GAB/arm_template.json)** – 此範本有助於升級與 **客戶**、**聯絡人**，和 **廠商** 資料相關聯的電子郵件地址。

在該過程結束時，將產生以下逗號分隔值 (.csv) 檔案。

| 檔案名稱 | 用途 |
|---|---|
| FONewParty.csv | 該檔案有助於建立財務和營運應用程式中新 **合作對象** 記錄。 |
| ImportFONewPostalAddressLocation.csv | 該檔案有助於建立財務和營運應用程式中新 **郵寄地址位置** 記錄。 |
| ImportFONewPartyPostalAddress.csv | 該檔案有助於建立財務和營運應用程式中新 **合作對象郵寄地址** 記錄。 |
| ImportFONewPostalAddress.csv | 該檔案有助於建立財務和營運應用程式中新 **郵寄地址** 記錄。 |
| ImportFONewElectronicAddress.csv | 該檔案有助於建立財務和營運應用程式中新 **電子郵件地址** 記錄。 |

本主題說明如何使用 Data Factory 範本和升級您的資料。 如果您沒有任何自訂，則可以按原樣使用範本。 但是，如果您有自訂 **客戶**、**聯絡人**，和 **廠商** 資料，您必須按照本主題中的說明修改範本。

> [!IMPORTANT]
> 執行合作對象的郵寄地址和合作對象的電子郵件地址範本有特殊說明。 您必須先執行合作對象範本，然後是合作對象郵寄地址範本，然後是合作對象電子郵件地址範本。 每個範本都旨在匯入單獨的資料處理站。

## <a name="prerequisites"></a>先決條件

在升級到合作對象和全球通訊錄模型之前，必須滿足以下先決條件：

+ 您必須有[Azure 訂用客戶](https://portal.azure.com/)。
+ 您必須有權存取[範本](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema)。
+ 您必須是現有的雙重寫入客戶。

## <a name="prepare-for-the-upgrade"></a>準備升級

升級需要以下準備：

+ **完全同步：** 財務和營運環境以及客戶業務開發環境都針對 **客戶 (客戶)**、**聯絡人** 和 **廠商** 資料表處於完全同步的狀態。
+ **整合金鑰：** 客戶業務開發應用程式中的 **客戶 (客戶)**、**聯絡人** 和 **廠商** 資料表正在使用立即可用的整合金鑰。 如果您自訂了整合金鑰，則必須自訂範本。
+ **合作對象編號：** 所有將要升級的 **客戶 (客戶)**、**聯絡人** 和 **廠商** 記錄具有合作對象編號。 沒有合作對象編號的記錄將被忽略。 如果您想升級這些記錄，請在開始升級過程之前為其新增一個合作對象編號。
+ **系統中斷：** 在升級過程中，您必須使財務和營運環境以及客戶業務開發環境都離線。
+ **快照集：** 拍攝財務和營運應用程式和客戶業務開發應用程式的快照。 然後，如果有需要，您可以使用快照還原以前的狀態。

## <a name="deployment"></a>部署

1. 從[Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema)下載範本。
2. 登入 [Azure 入口網站](https://portal.azure.com/)。
3. 建立 [資源群組](/azure/azure-resource-manager/management/manage-resource-groups-portal)。
4. 在您建立的資源組中建立 [儲存體客戶](/azure/storage/common/storage-account-create?tabs=azure-portal)。
5. 在您建立的資源組中建立 [資料處理站](/azure/data-factory/quickstart-create-data-factory-portal)。
6. 開啟資料處理站，選取 **作者和監控者** 圖格。
7. 在 **管理** 索引標籤，選取 **ARM 範本**。
8. 選取 **匯入 ARM 範本** 匯入 **合作對象** 範本。
9. 將範本匯入資料處理站。 輸入以下 **專案詳情** 和 **執行個體詳情** 的值。

    | 欄位 | 值 |
    |---|---|
    | 訂閱 | Azure 訂用客戶 |
    | 資源群組 | 提供與建立儲存體客戶相同的資源。 |
    | 區域 | 該區域 |
    | 處理站名稱 | 處理站名稱 |
    | FO 連結服務主體金鑰 | 應用程式的金鑰 |
    | Azure Blob 儲存體_連線字串 | Azure Blob 儲存體連線字串 |
    | Dynamics Crm 連結服務_密碼 | 您指定為使用者名稱的使用者客戶密碼 |
    | FO 連結服務_屬性_類型 屬性_url | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | FO 連結服務_屬性_類型 屬性_租使用者 | 有關您應用程式所在租使用者的資訊 (網域名稱或租使用者 ID) |
    | FO 連結服務_屬性_類型 屬性_aad 資源識別碼 | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | FO 連結服務_屬性_類型 屬性_服務 主體識別碼 | 應用程式的用戶端識別碼 |
    | Dynamics Crm 連結服務_屬性_類型 屬性_使用者名稱 | 用於連線到 Dynamics 365 的使用者名稱 |

    有關詳細資訊，請參閱下列主題：

    - [為每個環境手動提升資源管理器範本](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [連結服務屬性](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [使用 Azure Data Factory 複製資料](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. 部署後，驗證資料處理站的資料集、資料流程和連結服務。

    ![資料集、資料流程和連結服務。](media/data-factory-validate.png)

11. 進入 **管理**。 在 **連線** 下，選取 **連結服務**。 然後選取 **DynamicsCrmLinkedService**。 在 **編輯連結服務 (Dynamics CRM)** 對話方塊中，輸入以下值。

    | 欄位 | 值 |
    |---|---|
    | 姓名 | DynamicsCrmLinkedService |
    | 描述 | 與 CRM 執行個體連線以擷取實體資料的連結服務 |
    | 透過整合執行階段連線 | AutoResolvelntegrationRuntime |
    | 部署類型 | 線上 |
    | 服務 Uri | `https://<organization-name>.crm[x].dynamics.com` |
    | 驗證類型 | Office365 |
    | 使用者名稱 | |
    | 密碼或 Azure Key Vault | 密碼 |
    | 密碼 | |

## <a name="prepare-to-run-the-data-factory-templates"></a>準備執行 Data Factory 範本

本節介紹在執行合作對象郵寄地址和合作對象電子郵件地址 Data Factory 範本之前所需的設定。

### <a name="setup-to-run-the-party-postal-address-template"></a>設定以執行合作對象郵寄地址範本

1. 登入到客戶業務開發應用程式，然後進入 **設定**\>**個人化設定**。 然後，在 **一般** 索引標籤，為系統管理員客戶設定時區設定。 該時區必須採用國際標準時間 (UTC)，才能從財務和營運應用程式更新郵寄地址的「有效開始日期」和「有效結束日期」。

    ![系統管理員客戶的時區設定。](media/ADF-1.png)

2. 在 Data Factory 中，**管理** 索引標籤，在 **全域參數** 下，建立以下全域參數。

    | 號碼 | 姓名 | 類型 | 值 |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | 字串 | 此參數將序號附加到新建立的郵寄地址作為前綴。 請務必提供與財務和營運應用程式應用和客戶業務開發應用程式中郵寄地址不衝突的字串。 例如，使用 **ADF-PAD-**。 |

    ![在管理索引標籤上建立的 PostalAddressIdPrefix 全域參數。](media/ADF-2.png)

3. 完成後，選取 **發佈全部**。

    ![發佈全部按鈕。](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>設定以執行合作對象電子郵件地址範本

1. 在 Data Factory 中，**管理** 索引標籤，在 **全域參數** 下，建立以下全域參數。

    | 號碼 | 姓名 | 類型 | 值 |
    |---|---|---|---|
    | 1 | IsFOSource | 布林 | 此參數會判斷在發生衝突時應替換哪些主系統地址。 如果值為 **True**，財務和營運應用程式中的主要地址將替換客戶業務開發應用程式中的主要地址。 如果值為 **False**，客戶業務開發應用程式中的主要地址將替換財務和營運應用程式中的主要地址。 |
    | 2 | ElectronicAddressIdPrefix | 字串 | 此參數將序號附加到新建立的電子郵件地址作為前綴。 請務必提供與財務和營運應用程式應用和客戶業務開發應用程式中電子郵件地址不衝突的字串。 例如，使用 **ADF-EAD-**。 |

    ![在管理索引標籤上建立的 IsFOSource 和 ElectronicAddressIdPrefix 全域參數。](media/ADF-4.png)

2. 完成後，選取 **發佈全部**。

## <a name="run-the-templates"></a>執行範本

1. 停止以下使用財務和營運應用程式的 **合作對象**、**客戶**、**聯絡人** 和 **廠商** 雙重寫入地圖：

    + CDS 方 (msdyn_parties) 
    + 客戶 V3 (客戶)
    + 客戶 V3 (聯絡人)
    + CDS 聯絡人 V2 (聯絡人)
    + CDS 聯絡人 V2 (聯絡人)
    + 廠商 V2 (msdyn_vendor)
    + 聯絡人 V2 (msdyn_contactforparties)
    + CDS 方郵寄地址位置 (msdyn_partypostaladdresses)
    + CDS 郵寄地址歷史記錄 V2 (msdyn_postaladdresses)
    + CDS 郵寄地址位置 (msdyn_postaladdresscollections)
    + 合作對象聯絡人 V3 (msdyn_partyelectronicaddresses)

2. 確保地圖已從 Dataverse 中的 **msdy_dualwriterruntimeconfig** 資料表移除。
3. 從 AppSource 安裝[雙重寫入方和全球通訊錄解決方案](https://aka.ms/dual-write-gab)。
4. 在財務和營運應用程式中，針對以下表格 (如果它們包含資料)執行 **初始同步**：

    + 稱謂
    + 個人角色類型
    + 免費結算
    + 聯絡人個人稱謂
    + 決策角色
    + 忠誠度

5. 在客戶業務開發應用中，停用以下外掛程式步驟：

    + 客戶更新

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity：客戶更新
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes：客戶更新

    + 聯絡人更新

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity：聯絡人更新
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact：聯絡人更新

    + msdyn_party 更新

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity：msdyn_party 更新

    + msdyn_vendor 更新

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity：msdyn_vendor 更新

    + Customeraddress

        + 建立

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress：customeraddress 建立

        + 更新

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress：customeraddress 更新

        + 刪除

            + Microsoft.Dynamics.GABExtended.Plugins.DeleteCustomerAddress：customeraddress 刪除

    + msdyn_partypostaladdress

        + 建立

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress：msdyn_partypostaladdress 建立
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress：msdyn_partypostaladdress 建立

        + 更新

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress：msdyn_partypostaladdress 更新
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress：msdyn_partypostaladdress 更新

    + msdyn_postaladdress

        + 建立

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress：msdyn_partypostaladdress 建立
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate：msdyn_partypostaladdress 建立
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress：msdyn_postaladdress 建立

        + 更新

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate：msdyn_partypostaladdress 更新
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress：msdyn_postaladdress 更新

    + msdyn_partyelectronicaddress

        + 建立

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync：msdyn_partyelectronicaddress 建立

        + 更新

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync：msdyn_partyelectronicaddress 更新

        + 刪除

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync：msdyn_partyelectronicaddress 刪除

6. 在客戶業務開發應用中，停用以下工作流程：

    + 在帳戶表中建立廠商
    + 在帳戶表中建立廠商
    + 在聯絡人表中建立人員類型的廠商
    + 在廠商表中建立人員類型的廠商
    + 在帳戶表中更新廠商
    + 在廠商表中更新廠商
    + 在聯絡人表中更新人員類型的廠商
    + 在廠商表中更新人員類型的廠商

7. 在資料處理站中，透過選取如下圖所示的 **立即觸發** 執行範本。 此過程可能需要幾個小時才能完成，具體取決於資料量。

    ![執行範本。](media/data-factory-trigger.png)

    > [!NOTE]
    > 如果您有自訂 **客戶**、**聯絡人** 和 **廠商**，您必須修改範本。

8. 將新的 **合作對象** 記錄匯入到財務和營運應用程式中。

    1. 從 Azure Blob 儲存體下載 **FONewParty.csv** 檔案。 路徑是 **partybootstrapping/output/FONewParty.csv**。
    2. 將 **FONewParty.csv** 檔案轉換為 Excel 檔案，並將 Excel 檔案匯入財務和營運應用程式。 或者，如果 CSV 匯入適合您，您可以直接匯入 .csv 檔案。 此步驟可能需要幾個小時才能完成，具體取決於資料量。 如需相關資訊，請參閱[資料匯入和匯出工作概述](../data-import-export-job.md)。

    ![匯入 Dataverse 合作對象記錄。](media/data-factory-import-party.png)

9. 在資料處理站中，依次執行合作對象的郵寄地址和合作對象的電子郵件地址範本。

    + 合作對象的郵寄地址範本會插入更新客戶業務開發應用程式中的所有郵寄地址記錄，並將它們與相應的 **客戶**、**聯絡人** 和 **廠商** 記錄相關聯。 它還產生三個 .csv 檔案：ImportFONewPostalAddressLocation.csv、ImportFONewPartyPostalAddress.csv 和 ImportFONewPostalAddress.csv。
    + 合作對象的電子郵件地址範本會插入更新客戶業務開發應用程式中的所有電子郵件地址記錄，並將它們與相應的 **客戶**、**聯絡人** 和 **廠商** 記錄相關聯。 它還會產生一個 .csv 檔案：ImportFONewElectronicAddress.csv。

    ![執行合作對象的郵寄地址和合作對象的電子郵件地址範本。](media/ADF-7.png)

10. 若要使用此資料更新財務和營運應用程式，您必須將 .csv 檔案轉換為 Excel 活頁簿並[將其匯入財務和營運應用程式](/data-entities/data-import-export-job)。 或者，如果 CSV 匯入適合您，您可以直接匯入 .csv 檔案。 此步驟可能需要幾個小時才能完成，具體取決於量。

    ![成功匯入。](media/ADF-8.png)

11. 在客戶業務開發應用中，啟用以下外掛程式步驟：

    + 客戶更新

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity：客戶更新
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes：客戶更新

    + 聯絡人更新

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity：聯絡人更新
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact：聯絡人更新

    + msdyn_party 更新

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity：msdyn_party 更新

    + msdyn_vendor 更新

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity：msdyn_vendor 更新

    + msdyn_partypostaladdress

        + 建立

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress：msdyn_partypostaladdress 建立
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress：msdyn_partypostaladdress 建立

        + 更新

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress：msdyn_partypostaladdress 更新
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress：msdyn_partypostaladdress 更新

    + msdyn_postaladdress

        + 建立

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress：msdyn_partypostaladdress 建立
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate：msdyn_partypostaladdress 建立
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress：msdyn_postaladdress 建立

        + 更新

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate：msdyn_partypostaladdress 更新
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress：msdyn_postaladdress 更新
 
    + msdyn_partyelectronicaddress

        + 建立

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync：msdyn_partyelectronicaddress 建立

        + 更新

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync：msdyn_partyelectronicaddress 更新

        + 刪除

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync：msdyn_partyelectronicaddress 刪除

12. 如果您之前停用了以下工作流程，請在客戶業務開發應用中啟用它們：

    + 在帳戶表中建立廠商
    + 在帳戶表中建立廠商
    + 在聯絡人表中建立人員類型的廠商
    + 在廠商表中建立人員類型的廠商
    + 在帳戶表中更新廠商
    + 在廠商表中更新廠商
    + 在聯絡人表中更新人員類型的廠商
    + 在廠商表中更新人員類型的廠商

13. 執行 **合作對象** 記錄相關的地圖，如[合作對象和全球通訊錄](party-gab.md)。

## <a name="explanation-of-the-data-factory-templates"></a>Data Factory 範本說明

本節將引導您完成每個 Data Factory 範本中的步驟。

### <a name="steps-in-the-party-template"></a>合作對象範本中的步驟

1. 步驟 1 到 6 可確定啟用雙重寫入的公司並為它們構建篩選子句。
2. 步驟 7-1 到 7-9 從財務和營運應用程式和客戶業務開發應用程式取出資料，並將該資料暫存以進行升級。
3. 步驟 8 到 9 比較財務和營運應用程式和客戶業務開發應用程式之間 **客戶**、**聯絡人** 和 **廠商** 記錄的合作對象編號。 任何沒有合作對象編號的記錄都將被跳過。
4. 步驟 10 為必須在客戶業務開發應用程式和財務和營運應用程式中建立的合作對象記錄產生兩個 .csv 檔案。

    - **FOCDParty.csv** – 此檔案包含兩個系統的所有合作對象記錄，無論公司是否啟用雙重寫入。
    - **FONewParty.csv** – 此檔案包含 Dataverse 知道的合作對象記錄的子集 (例如，**潛在客戶** 類型的客戶)。

5. 步驟 11 在客戶業務開發應用程式中建立各合作對象。
6. 第 12 步從客戶業務開發應用程式中取出各合作對象的全球唯一識別碼 (GUID) 並將它們暫存起來，以便它們可以與後續步驟中的 **客戶**、**聯絡人** 和 **廠商** 記錄相關聯。
7. 步驟 13 將 **客戶**、**聯絡人** 和 **廠商** 記錄與合作對象 GUID 相關聯。
8. 步驟 14-1 到 14-3 使用合作對象 GUID 更新客戶業務開發應用程式中的 **客戶**、**聯絡人** 和 **廠商** 記錄。
9. 步驟 15-1 到 15-3 為 **客戶**、**聯絡人** 和 **廠商** 記錄準備 **合作對象聯絡人** 記錄。
10. 步驟 16-1 到 16-7 取出參考資料，例如稱呼和個人字元類型，並將其與 **合作對象聯絡人** 記錄關聯。
11. 步驟 17 合併 **客戶**、**聯絡人** 和 **廠商** 記錄的 **合作對象聯絡人** 記錄。
12. 步驟 18 將 **合作對象聯絡人** 記錄匯入到客戶業務開發應用程式中。

### <a name="steps-in-the-party-postal-address-template"></a>合作對象郵寄地址範本中的步驟

1. 步驟 1-1 到 1-10 從財務和營運應用程式和客戶業務開發應用程式取出資料，並將該資料暫存以進行升級。
2. 第 2 步透過連結郵寄地址和相關合作對象郵寄地址，對財務和營運應用程式中的郵寄地址資料進行非規範化處理。
3. 第 3 步從客戶業務開發應用程式中刪除和合併客戶、聯絡人和廠商地址資料。
4. 第 4 步為財務和營運應用程式建立 .csv 檔案，以建立基於客戶、聯絡人和廠商地址的新地址資料。
5. 步驟 5-1 為客戶業務開發應用建立 .csv 檔案，以基於財務和營運應用程式和客戶業務開發應用程式建立所有地址資料。
6. 步驟 5-2 將 .csv 檔案轉換為財務和營運應用程式匯入格式以供手動匯入。

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. 步驟 6 將郵寄地址收集資料匯入客戶業務開發應用程式。
8. 步驟 7 從客戶業務開發應用程式中取出郵寄地址收集資料。
9. 步驟 8 建立客戶地址資料並建立與郵寄地址集合 ID 的關聯。
10. 步驟 9-1 到 9-2 將合作對象和郵寄地址收集 ID 與郵寄地址和合作對象郵寄地址建立關聯。
11. 步驟 10-1 到 10-3 將客戶地址、郵寄地址和合作對象郵寄地址匯入客戶業務開發應用程式。

### <a name="steps-in-the-party-electronic-address-template"></a>合作對象電子郵件地址範本中的步驟

1. 步驟 1-1 到 1-5 從財務和營運應用程式和客戶業務開發應用程式取出資料，並將該資料暫存以進行升級。
2. 第 2 步在客戶業務開發應用程式中整合來自客戶、聯絡人和廠商實體的電子郵件地址。
3. 步驟 3 合併來自客戶業務開發應用程式和財務和營運應用程式的主要電子郵件地址資料。
4. 第 4 步為建立 .csv 檔案。

    - 根據客戶、聯絡人和廠商地址，為財務和營運應用程式建立新的電子郵件地址資料。
    - 根據財務和營運應用程式中的電子郵件地址、客戶、聯絡人和廠商地址，為客戶業務開發應用程式建立新的電子郵件地址資料。

5. 步驟 5-1 將電子郵件地址匯入客戶業務開發應用程式。
6. 步驟 5-2 建立 .csv 檔案以更新客戶業務開發應用程式中客戶和聯絡人的主要地址。
7. 步驟 6-1 到 6-2 將客戶和聯絡人主要地址匯入客戶業務開發應用程式。

## <a name="troubleshooting"></a>疑難排解

1. 如果該過程失敗，請重新執行資料處理站。 從失敗的活動開始。
2. 資料處理站產生的一些檔案可用於資料驗證。
3. 資料處理站根據 .csv 檔案執行。 因此，如果逗號包含在任何欄位值中，它可能會干擾結果。 您必須從欄位值中刪除所有逗號。
4. **監控** 索引標籤提供有關已處理的所有步驟和資料的資訊。 選取一個特定的步驟來偵錯它。

    ![監控索引標籤。](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>深入了解範本

如需範本的相關資訊，請參閱[Azure Data Factory 範本說明檔案的註解](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md)。
