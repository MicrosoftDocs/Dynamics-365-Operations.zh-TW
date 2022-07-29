---
title: 複製執行個體
description: 您可以使用 Microsoft Dynamics Lifecycle Services (LCS) 複製 Microsoft Dynamics 365 Human Resources 資料庫到沙箱環境。
author: andreabichsel
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 22aa33135535d543eb8fe437821cab7a4865d6df
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451995"
---
# <a name="copy-an-instance"></a>複製執行個體

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



您可以使用 Microsoft Dynamics Lifecycle Services (LCS) 複製 Microsoft Dynamics 365 Human Resources 資料庫到沙箱環境。 如果您有另一個沙箱環境，您也可以將資料庫從那個環境複製到確定目標沙箱環境。

若要複製執行個體，請記住下列秘訣：

- 您要覆寫的人力資源執行個體必須是沙箱環境。

- 您往返複製的環境必須在相同區域。 您不能跨區域複製。

- 您必須是確定目標環境的管理員才能在複製執行個體後登入。

- 當您複製人力資源資料庫時，不會複製 Microsoft Power Apps 環境包含的元素 (App 或資料)。 有關複製 Power Apps 環境元素方法的資訊，請參閱[複製環境](/power-platform/admin/copy-environment)。 您要覆寫的 Power Apps 環境必須是沙箱環境。 您必須是全域租使用者管理員才能將 Power Apps 實際執行環境變更為沙箱環境。 更多有關變更 Power Apps 環境的資訊，請參閱[切換執行個體](/dynamics365/admin/switch-instance)。

- 如果您將執行個體複製到沙箱環境並且希望整合沙箱環境和 Dataverse，您必須重新套用自訂欄位到 Dataverse 資料表。 請參閱[將自訂欄位套用到 Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service)。

## <a name="effects-of-copying-a-human-resources-database"></a>複製人力資源資料庫的影響

複製人力資源資料庫時會發生的事件如下：

- 複製過程會抹除確定目標環境中既有的資料庫。 複製過程完成後，您無法復原既有的資料庫。

- 複製過程完成前，確定目標環境將不開放使用。

- Microsoft Azure Blob 儲存體的文件不會從一個環境複製到另一個環境。 所以任何附加的文件和範本都不會複製，並將保留在來源環境。

- 除了身為 “系統管理員” 資訊安全角色的使用者以外，不開放給其餘使用者和內部服務使用者帳戶的使用者使用。 管理員使用者可以在其他使用者獲准返回系統之前刪除或混用資料。

- 任何有 “系統管理員” 資訊安全角色的使用者都必須進行必要的組態變更，例如重新連結整合端點到特定服務或 URL。

## <a name="copy-the-human-resources-database"></a>複製人力資源資料庫

為了完成這項任務，您先複製執行個體，然後登入 Microsoft Power Platform 管理中心複製您的 Power Apps 環境。

> [!WARNING]
> 複製執行個體時，資料庫會在確定目標執行個體內抹除。 這段過程確定目標執行個體不開放使用。

1. 登入 LCS，並且選取包含您希望複製執行個體的 LCS 專案。

2. 請在您的 LCS 專案選取 **人力資源 App 管理** 圖格。

3. 請選取要複製的執行個體，然後選取 **複製**。

4. 請在 **複製執行個體** 任務窗格內選取要覆寫的執行個體，然後選取 **複製**。 請等到 **複製狀態** 欄位值更新到 **已完全** 為止。

   ![[選取要覆寫的執行個體。](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. 請選取 **Power Platform** 並登入 Microsoft Power Platform 系統管理中心。

   ![[請選取 Power Platform。](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. 請選取要複製的 Power Apps 環境，然後選取 **複製**。

7. 複製流程完成後，登入確定目標執行個體並啟用 Dataverse 整合功能。 更多資訊和說明，請參閱[配置 Dataverse 整合](./hr-admin-integration-common-data-service.md)。

## <a name="data-elements-and-statuses"></a>資料元素和狀態

當您複製人力資源執行個體時不會複製下列資料元素：

- **LogisticsElectronicAddress** 資料表裡的電子郵件信箱地址

- **BatchJobHistory**、**BatchHistory** 和 **BatchConstraintHistory** 資料表裡的批次工作歷史記錄

- **SysEmailSMTPPassword** 資料表裡的簡易郵件傳輸通訊協定 (SMTP) 密碼

- **SysEmailParameters** 資料表裡的 SMTP 繼電伺服器

- **PrintMgmtSettings** 和 **PrintMgmtDocInstance** 資料表裡的列印管理設定

- **SysServerConfig**、**SysServerSessions**、**SysCorpNetPrinters**、**SysClientSessions**、**BatchServerConfig** 和 **BatchServerGroup** 資料表裡的環境特定記錄

- DocuValue 資料表裡的文件附檔。 這些附檔包括在來源環境覆寫的任何 Microsoft Office 範本

- **PersonnelIntegrationConfiguration** 資料表裡的連接字串

其中一些元素因為是環境特定元素，因為不會複製。 範例包括 **BatchServerConfig** 和 **SysCorpNetPrinters** 記錄。 由於支援票證量緣故，不複製其他元素。 例如： 

- 由於使用者驗收測試 (沙箱) 環境仍然啟用 SMTP，因此可能傳送重覆的電子郵件。

- 可能因為仍然啟用批次工作而傳送無效的整合訊息。

- 管理員可以執行重新整理後的清理動作之前可能會啟用使用者。

而且當您複製執行個體時會改變下列狀態：

- 除了本身是 “系統管理員” 資訊安全角色的使用者以外，其他使用者都設定為 **已停用**。

- 除了一些系統工作以外，其他批次工作皆設定為 **預留**。

## <a name="environment-admin"></a>環境管理員

確定目標沙箱環境裡的所有使用者 (包括管理員) 都更換為來源環境的使用者。 在您複製執行個體之前，請確定您在來源環境是管理員身份。 如果不是，您無法在複製完成後登入確定目標沙箱環境。

確定目標沙箱環境中的所有非管理員使用者皆已停禁用，預防沙箱環境的不必要登入。 必要時管理員可以重新啟用使用者。

## <a name="apply-custom-fields-to-dataverse"></a>將自訂欄位套用到 Dataverse

如果您將執行個體複製到沙箱環境並且希望整合沙箱環境和 Dataverse，您必須重新套用自訂欄位到 Dataverse 資料表。

Dataverse 資料表上揭露的每個自訂欄位方面，請執行步驟如下：

1. 前往自訂欄位並選取 **編輯**。

2. 取消選取已啟用自訂欄位的每個 cdm_* 實體 **啟用** 欄位。

3. 請選取 **套用變更**。

4. 請再選取一次 **編輯**。

5. 請選取已啟用自訂欄位的每個 cdm_* 實體 **啟用** 欄位。

6. 請再選取一次 **套用變更**。

取消選取、套用變更、重新選取和重新套用變更的流程會提示在 Dataverse 預計更新的結構描述，包括自訂欄位。

更多有關自訂欄位的資訊，請參閱[建立和搭配自訂欄位](../fin-ops-core/fin-ops/get-started/user-defined-fields.md)。

## <a name="see-also"></a>也請參閱

[佈建人力資源](hr-admin-setup-provision.md)</br>
[移除執行個體](hr-admin-setup-remove-instance.md)</br>
[更新流程](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
