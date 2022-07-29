---
title: 配置與 Dayforce 的整合
description: 本主題說明 Microsoft Dynamics 365 Human Resources 與 Ceridian Dayforce 之間整合所需的組態步驟。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7e2043e75aa647e21f3e0816247dcf651be64730
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452304"
---
# <a name="configure-integration-with-dayforce"></a>配置與 Dayforce 的整合


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources 與 Ceridian Dayforce 之間的整合仰賴本主題說明的幾道組態步驟。 您必須先在人力資與 Dayforce 中配置整合才能處理付款執行動作。

當您使用如 Dayforce 的服務完成支付執行動作時，您必須在人力資源中啟用整合功能。 整合需要人力資源的特定資料。 因此，您必須查核對應到 Dayforce 的資料是否在人力資源中以支援整合的方式配置。 整合使用下列廣泛的資料類別：

- 人力資源資料
- 薪酬資料
- 工資單資料，例如付款週期、付款期間和收入代碼
- 背景工作角色資料

本主題說明啟用整合必須遵照的步驟並且說明整合需要的資料類型和組態細節。

## <a name="enable-the-integration"></a>啟用整合功能

您必須在人力資源中開啟整合功能，並且輸入組態資源才能連接 Dayforce。 如果您希望將產生的總帳交易匯入 Microsoft Dynamics 365 Finance，您也必須設定 Microsoft Azure 儲存設備帳戶並在 Finance 輸入 Azure 儲存設備連接字串。

若要在人力資源中開啟整合，請遵照這些步驟。

1. 請在 **系統管理** 頁選取 **整合配置**。
2. 請輸入安全檔案傳輸通訊協定 (FTP) 端點和安全 FTP 資料夾路徑。
3. 請輸入將存取安全 FTP 端點和資料夾路徑的用戶的使用者名稱和密碼。
4. 請根據要求測試連線情況，並設定 **啟用工資單整合** 選項為 **是**。

開啟整合後會建立資料匯出包和檔案，並設定頻率。 您可以根據要求更改此頻率。

更多有關 Azure 儲存設備帳戶和 Azure 儲存設備連接字串的資訊，請參閱下列 Azure 主題：

- [關於 Azure 儲存設備帳戶](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [配置 Azure 儲存設備連線字串](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a>啟用工資單整合時的技術細節

開啟工資單整合會產生兩個主要影響：

- 建立名為 “工資單整合匯出” 的資料匯出專案。 本專案包含工資單整合所需的實體和欄位。 若要詳細檢查專案，請前往 **系統管理**、選取 **資料管理** 圖格，然後從專案清單打開資料專案。
- 這項批次工作執行資料匯出專案、加密資料結果包，並將資料包檔案傳輸到在 **整合組態** 畫面上配置的 SFTP 端點。

> [!NOTE]
> 傳輸到 SFTP 端點的資料包會使用獨一無二的封包金鑰加密。 金鑰在只由 Ceridian 存取的 Azure 金鑰保存庫。 無法解密和詳細檢查資料包內容。 如果您需要詳細檢查看資料包的內容，您必須手動匯出 “工資單整合匯出” 資料專案下載並且打開它。 手動匯出將不適用加密或傳輸包。

## <a name="configure-your-data"></a>配置您的資料 

若要處理工資單，您必須在人力資源中配置人力資源資料。 您必須設定組織資料，例如工作和職位，以及福利和薪酬資訊。 本資訊提供產生員工工資所需的就業、工資和扣減資訊。

### <a name="human-resource-data"></a>人力資源資料

#### <a name="benefits"></a>福利 

人力資源提供工具設定與維護組織針對背景工作角色提供或處理的福利、扣減與背景工作角色薪酬計劃。

當您建立福利時，請記住 Dayforce 使用的下列資料和組態。

##### <a name="benefit-plans"></a>福利計劃

- 計劃 (必填項目)
- 類型 (必填項目)
- 工資影響面 (必填項目)
- 追回欠款
- 扣減方法
- 扣減優先順序
- 限期
- 限額

##### <a name="benefits"></a>福利

- 計劃 (必填項目)
- 類型 (必填項目)
- 選項 (必填項目)
- 福利識別碼 (必填項目)
- 頻率
- 依據
- 金額或費率
- 薪資代碼

##### <a name="supported-frequencies"></a>支援頻率 

- 每週
- 雙週
- 半個月
- 每月

##### <a name="supported-bases"></a>支援依據 

- 固定金額
- 收入百分比
- 生產力時數

Dayforce 根據福利計劃定義的工資影響面建立扣除額如下。

| 人力資源選取        | Dayforce 結果                            |
|----------------------------|-----------------------------------------------|
| 無                       | 不會建立任何扣除額。                      |
| 僅扣除             | 已建立員工扣除額。             |
| 僅分攤          | 已建立雇主扣除額。             |
| 扣除和分攤 | 已建立員工和雇主扣除額。 |

更多有關如何定義和管理福利計劃的資訊，請參閱下列主題：

- [提供員工福利計劃](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [建立新福利](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [定義福利資格規則和政策](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [註冊和移除背景工作角色福利](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a>薪酬 

薪酬管理用來控制基本工資和獎勵的發放。 員工的固定基本工資和績效增加透過固定薪酬計劃控制。 激勵獎金的支付，例如紅利、績效獎勵、股票選擇權和贈款，也包括一次性獎勵，皆透過變動薪酬計劃控制。

Dayforce 使用薪酬資訊計算員工的時薪或年薪。 需要固定薪酬計劃和工資率轉換。 員工必須與固定薪酬計劃產生關聯。

更多有關薪酬計畫資訊，請參閱主題如下：

- [建立固定薪酬計劃](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [建立變動薪酬計劃](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [擬訂工資/薪酬結構和計劃](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [處理薪酬](/dynamics365/unified-operations/talent/process-compensation)
- [定義薪酬流程和計算結果](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [在固定薪酬計劃中註冊員工](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [在變動薪酬計劃中註冊員工](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a>工作 

工作是工作執行者所需的任務和責任集合。 有關詳細資訊，請參閱下列主題：

- [設定工作的組成要素](/dynamics365/unified-operations/talent/create-job)
- [定義新工作](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a>職位

職位是工作的個別執行個體。 例如，“銷售經理 (東部)” 職位是與 “銷售經理” 工作有關聯的職位之一。 職位存在於部門中。 每個職位只能與一名背景工作角色有關聯。

當您設定職位時，請記住下列資料和組態：

- 職位 (必填項目)
- 說明 (必填項目)
- 工作 (必填項目)
- 部門 (必填項目)
- 職位類型 (必填項目)
- 全職等效項目
- 每年平日工作時間 (必填項目)
- 由法人支付 (必填項目)
- 支付週期 (必填項目)
- 預設財務維度 - 成本中心 (必填項目)
- 背景工作角色指派 - 背景工作角色、指派開始、指派結束、原因代碼

如果同部門的多個職位與同一個職位有關聯，它們將合併為 Dayforce 的一個職位。

有關詳細資訊，請參閱下列主題：

- [使用部門、工作和職位來組織您的人力陣容](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [設定職位](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a>部門

部門是代表組織的類別或職能領域的營運單位。 部門負責組織的特定領域，例如銷售、會計或人力資源。 您可以使用部門回報職能領域。 部門可能有損益責任。

有關詳細資訊，請參閱下列主題：

- [建立部門並與部門階層產生關聯](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [定義新部門](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a>支付週期和支付期間

工資週期判定工資單的執行頻率和背景工作角色獲得工資的具體日期。 例如，支付週期可能是月結，而員工可能在當月的最後一天收到款項。 或者，支付週期可能是週結，而員工可能會在支付期間結束後的星期二收到款。 支付週期按指派的職位控制任職的背景工作角色收到款項的時間點。

支付週期建立後，您可以為每個週期產生支付期間。 每個支付期包括以您提供的資訊為主的預設付款日期。 然而，您可以修改支付期間的預設支付日期以允許例外狀況，例如當支付日期是例假日時。

Dayforce 使用的資訊如下：

- 支付週期 (必填項目)
- 支付週期頻率 (必填項目)
- 期間開始日期 (需要第一個支付期間)
- 預設付款日期 (需要第一個支付期間)

本資訊與 Dayforce 整合成付款群組，並按每個國家或地區的支付週期分開。 整合之前至少必須產生一個支付期間。 Dayforce 會根據第一個支付期間的開始日期和人力資源設定的預設支付日期產生付款群組行事曆和付款日期。

#### <a name="earning-codes"></a>所得代碼

所得代碼專門辨別背景工作角色收到每種唯一的所得類型。 這些代碼的各種參數皆與所得相關，例如會計規則、稅法、報表要求和彙總能力。

Dayforce 使用的資訊如下：

- 所得代碼 (必填項目)
- 描述
- 測量單位
- 生產力

### <a name="worker-data"></a>背景工作角色資料

您現有的各類型背景工作角色記錄對您的人力資源和工資撥付系統很重要。 您輸入的資訊可用來追蹤背景工作角色和個人資訊。

您可以維護背景工作角色資訊如下：

- **基本** – 維護有關背景工作角色的基本資訊，例如聯絡資訊、人口統計資訊、身份資訊、家庭資訊、兵役狀態、外派資訊以及個人和緊急聯絡人。
- **就業** – 維護有關背景工作角色的資訊，例如公司或組織隸屬關係、職位指派、開始和結束日期、工作資格、就業條款、退休金、假期和搬家資訊。
- **休假和缺勤** – 維護有關背景工作角色缺勤的資訊，例如工作行事曆、缺勤交易和設定。
- **薪酬和工資單** – 維護有關背景工作角色薪酬計劃資訊和工資資訊，例如計劃註冊、獎勵、績效、佣金、納稅資訊、退休和薪資扣除額。

當您輸入背景工作角色資訊時，請記住 Dayforce 使用的下列資料和組態。

#### <a name="general-information"></a>一般資訊

- 人員編號 (必填項目)
- 名字 (必填項目)
- 姓氏 (必填項目)
- 中間名
- 年資日期
- 別名

#### <a name="personal-information"></a>個人資訊

- 婚姻狀況 (必填項目)
- 生日 (必填項目)
- 性別 (必填項目)
- 身障人士
- 國籍國家地區 (限墨西哥)

#### <a name="address-information"></a>地址資訊

- 主要 (必填項目)
- 國家/地區 (必填項目)
- 郵遞區號 (必填項目)
- 街道號碼 (必填項目) (僅限墨西哥)
- 建築補充 (僅適用墨西哥)
- 城市 (必填項目)
- 州 (必填項目)
- 縣 (必填項目)

#### <a name="contact-information"></a>連絡資訊 

- 主要 (必填項目)
- 聯絡電話 (必填項目)
- 分機

#### <a name="payroll-information-and-earning-codes"></a>工資單資訊和所得代碼

員工可按預訂的付款頻率指派特定所得，並且有首選的付款方式。 Dayforce 使用下列欄位協助保證使用這些偏好和設定。

##### <a name="earning-codes"></a>所得代碼

- 職位 (必填項目)
- 所得代碼 (必填項目)
- 頻率 (必填項目)
- 金額 (必填項目)

##### <a name="payroll-information"></a>工資單資訊

- 付款方式
- 經濟區 (必填項目)
- 員工福利識別碼
- 國民身份證號碼 (必填項目)
- 兵役編號
- 班別識別碼 (必填項目)
- 稅號 (必填項目)
- 工會識別碼 (必填項目)
- 工作日識別碼 (必填項目)
- 工作證號碼

> [!NOTE]
> 付款方式方面，墨西哥支援 **現金**、**支票** (公司實際檢查) 和 **電子支付**。 如果指明 np 付款方式，預設會使用 **支票**。

#### <a name="employment-details"></a>就業詳細資料

就業詳細歷史記錄會當成衍生員工在 Dayforce 錄用、終止和重新錄用狀態的關鍵資訊。 Dayforce 支援一次一筆有效的就業記錄。

- 就業開始日期 (必填項目)
- 雇用結束日期
- 開始日期
- 調整後開始日期
- 終止日期 (終止時為必填項目)
- 終止原因 (終止時為必填項目)

員工的關鍵日期藉由下列資訊衍生而得。

| Human Resources                | Dayforce                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| 最近的錄用日期 | 目前未終止就業歷史記錄的就業開始日期                                 |
| 終止日期      | 目前未終止就業歷史記錄的終止日期                                 |
| 開始日期            | 目前非有效就業歷史記錄的調整開始日期、開始日期或就業開始日期 |
| 原始雇用日期    | 最早就業歷史記錄的就業開始日期                                               |

#### <a name="compensation"></a>薪酬

固定薪酬計劃必須與每位員工在整個就業期間的主要職位產生關聯。 本期間從員工被雇用的日期 (或就業開始日期) 開始，持續到終止為止。

- 生效日期 (必填項目)
- 到期日期
- 工資率 (必填項目)
- 工資率轉換 (必填項目)
- 折合年值 (必填項目)
- 折合小時值 (必填項目)

如果時薪員工任職多個職位，主要職位的固定薪酬會以員工級基本工資/薪資匯入 Dayforce。 非主要職位方面，時薪費率將儲存到 Dayforce 的對應職位。

如果受薪員工任職多個職位，則所有在職職位的累計時薪費率和年薪將以員工級基本費率/薪資衍生和使用。

#### <a name="identification-numbers"></a>身份證號碼

##### <a name="social-security-identifier"></a>社會安全識別碼 

每位員工必須有一個主要識別碼。 此識別碼必須是 **SSN** 識別類型。 在 Dayforce 中，它會自動衍生為錄用所需的員工社會安全識別碼。

- 主要 (必填項目)
- 識別碼類型 = "SSN"
- 核發日期
- 到期日

員工可以申報多個 **SSN** 識別類型的身份證號碼。 然而，只有標示為 **主要** 的記錄才會整合到 Dayforce，不論號碼是否有效或已到期。

#### <a name="bank-accounts-and-disbursements"></a>銀行帳戶和請款

必須為選擇透過銀行帳戶轉帳付款的任何員工輸入有效的銀行帳戶資訊。

| Human Resources                         | Dayforce                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| 銀行帳號 (必填項目) |                                                                                                             |
| SWIFT 代碼 (必填項目)          | **銀行識別碼** 欄位用於墨西哥處理工資單時。                                                             |
| 分行編號 (必填項目)       |                                                                                                             |
| 銀行帳號類型 (必填項目)   | **帳戶類型** 欄位用在墨西哥處理工資單時。 支援值包括 **檢查** 和 **工資單**。 |

> [!NOTE]
> 選擇透過銀行帳戶轉帳獲得薪酬的員工必須提供在法人實體之下，墨西哥擁有主要地址並與墨西哥銀行的有效銀行帳號產生關聯的剩餘帳戶連結。 所有其他非剩餘帳戶一概不予理會。

#### <a name="address-information"></a>地址資訊

每位員工必須有一個主要位置。 在 Dayforce 中，此位置用來判定員工的主要課稅居住地。

- 主要 (必填項目)
- 國家/地區 (必填項目)
- 郵遞區號 (必填項目)
- 街道 (必填項目)
- 街道號碼 (必填項目)
- 建築補體
- 城市 (必填項目)
- 州 (必填項目)
- 縣 (必填項目)

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a>配置您的資料以便在美國和加拿大產生工資單

如果您正在為美國和加拿大的員工產生工資，務必配置下列元素：

- 職位需要部門。
- 成本中心必須設定為財務維度，並且必須是預設財務維度字串中的第一個元素。

> [!NOTE] 
> 您可以將人力資源配置為要求職位指明部門。 為此，請前往 **人力資源共享職位 > 職位 > 要求職位所屬部門**。 我們建議對整合強制執行這個設定。

### <a name="job-types"></a>工作類型

工作類型用來將類似工作分組到各個類別。 在美國和加拿大處理工資單需要工作類型。 工作類型範例包括全職和兼職，或薪資和時薪工資。 工作類型會對應到 Dayforce，作為指出員工按小時計薪或按薪資計薪的工資類型。

需要的工作類型和說明如下。

| 工作類型   | 描述 |
|------------|-------------|
| 每小時     | 每小時      |
| 領薪   | 領薪    |

### <a name="position-types"></a>職位類型 

您使用職位類型來說明此職位是全職、兼職或其他。 職位類型會對應到 Dayforce，作為指出員工是全職或兼職的工資類級。

需要的職位類型和說明如下。

| 職位類型   | 描述        |
|-----------------|--------------------|
| 全職       | 全職員工 |
| 兼職       | 兼職員工 |

### <a name="reason-codes"></a>原因代碼

原因代碼提供有關員工狀態的資訊。 原因代碼會以狀態原因對應到 Dayforce，指出員工職位或就業狀態更改的原因。

需要的原因代碼和說明如下。

| 原因代碼    | 描述      | 適用場合 |
|----------------|------------------|----------------------|
| 辭職    | 辭職      | 終止背景工作角色     |
| 終止    | 終止      | 終止背景工作角色     |
| 退休     | 退休       | 終止背景工作角色     |
| 其他          | 其他原因    | 終止背景工作角色     |
| 死亡          | 死亡            | 終止背景工作角色     |
| LEAVEOFABSENCE | 請假 | 終止背景工作角色     |
| CONTRACTEND    | 契約結束  | 終止背景工作角色     |
| SALARYCHANGE   | 薪水變動 | 薪酬         |

### <a name="marital-status"></a>婚姻狀態

婚姻狀態值對應到 Dayforce，並在整合時酌情轉換為可接受值。

下表顯示婚姻狀態值如何對應到 Dayforce。

| Human Resources                 | Dayforce             |
|------------------------|----------------------|
| 已婚                | 已婚              |
| 單身                 | 單身               |
| 喪偶                | 喪偶              |
| 離婚               | 離婚             |
| 已登記伴侶關係 | 國內合作夥伴關係 |
| 無                   | 無                 |
| 同居             | 同居           |

### <a name="gender"></a>性別

性別說明會對應到 Dayforce，並在整合時酌情轉換為可接受值。

下表顯示性別指標值如何對應到 Dayforce。

| Human Resources       | Dayforce        |
|--------------|-----------------|
| 男性         | 男性            |
| 女性       | 女性          |
| 非特定 | *不支援* |

### <a name="earning-codes"></a>所得代碼

所得代碼專門辨別背景工作角色收到每種唯一的所得類型。 這些代碼涵蓋幾個參數與所得有關，例如會計規則、稅法、報表要求和彙總能力。 如果使用不支援的頻率，則計算時預設會使用 **每次支付** 頻率。

#### <a name="supported-frequencies"></a>支援頻率

- 全部
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>地址

特定國家或地區、州和縣 (直轄市) 代碼的辨別需要 Dayforce 和國家/地區內提供者可以識別的特定格式。 儘管城市的格式有彈性，但每座城市都必須與州有關聯。

| Human Resources          | Dayforce              |
|-----------------|-----------------------|
| 國家/地區  | 國家/地區代碼          |
| 郵遞區號 | 郵遞區號           |
| 狀態           | 州代碼            |
| 城市            | 城市                  |
| 縣市          | 縣 (直轄市) |
| 街道          | 地址行 1        |

### <a name="tax-regions"></a>課稅地區

課稅地區用來判定工資單產生期間應套用的適當稅金。 課稅地區以位置地址對應到 Dayforce。 預設課稅地區必須與背景工作角色的有效職位有關聯。 

- 課稅地區 (必填項目)
- 國家/地區 (必填項目)
- 州 (必填項目)
- 縣市 
- 城市 (必填項目)

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a>配置您的資料以便在墨西哥產生工資單

如果您正在為墨西哥的員工產生工資，務必配置下列元素：

- 職位需要部門。
- 成本中心必須設定為財務維度，並且必須是預設財務維度字串中的第一個元素。

### <a name="job-types"></a>工作類型

工作類型用來將類似工作分組到各個類別。 在墨西哥處理工資單需要工作類型。 工作類型範例包括全職和兼職，或薪資和時薪工資。 工作類型會對應到 Dayforce，作為指出員工按小時計薪或按薪資計薪的工資類型。

需要的工作類型和說明如下。

| 工作類型   | 描述 |
|------------|-------------|
| 每小時     | MX 時薪   |
| 領薪   | MX 領薪 |

### <a name="position-types"></a>職位類型 

您使用職位類型來說明此職位是全職、兼職或其他。 職位類型會對應到 Dayforce，作為指出員工是全職或兼職的工資類級。

需要的職位類型和說明如下。

| 職位類型   | 描述        |
|-----------------|--------------------|
| 全職       | 全職員工 |
| 兼職       | 兼職員工 |

### <a name="reason-codes"></a>原因代碼

原因代碼提供有關員工狀態的資訊。 原因代碼會以狀態原因對應到 Dayforce，指出員工職位或就業狀態更改的原因。

需要的原因代碼和說明如下。

| 原因代碼            | 描述                    | 適用場合 |
|------------------------|--------------------------------|----------------------|
| DEPARTUREBEFOREPAYMENT | 領取第一份工資單之前離開 | 終止背景工作角色     |
| 辭職            | 辭職                    | 終止背景工作角色     |
| 退休金                | 退休金                        | 終止背景工作角色     |
| 終止            | 終止                    | 終止背景工作角色     |
| 退休             | 退休                     | 終止背景工作角色     |
| 缺勤者               | 缺勤者                       | 終止背景工作角色     |
| 其他                  | 其他原因                  | 終止背景工作角色     |
| 結束                | 結束營業               | 終止背景工作角色     |
| 死亡                  | 死亡                          | 終止背景工作角色     |
| LEAVEOFABSENCE         | 請假               | 終止背景工作角色     |
| CONTRACTEND            | 契約結束                | 終止背景工作角色     |
| SALARYCHANGE           | 薪水變動               | 薪酬         |

### <a name="terms-of-employment"></a>就業條款

就業條款用來建立就業條款的類別。 這些術語以就業指標值對應到 Dayforce。

需要下列就業條款和說明。

| 就業條款   | 描述 |
|-----------------------|-------------|
| 常規               | 常規     |
| 直接                | 直接      |
| 實習            | 實習  |
| 永久             | 永久   |

### <a name="marital-status"></a>婚姻狀態

婚姻狀態值對應到 Dayforce，並在整合時酌情轉換為可接受值。

下表顯示婚姻狀態值如何對應到 Dayforce。

| Human Resources                 | Dayforce                  |
|------------------------|---------------------------|
| 已婚                | 已婚                   |
| 單身                 | 單身                    |
| 喪偶                | 喪偶                   |
| 離婚               | 離婚                  |
| 已登記伴侶關係 | 國內合作夥伴關係      |
| 無                   | *墨西哥不支援* |
| 同居             | *墨西哥不支援* |

### <a name="gender"></a>性別

性別說明會對應到 Dayforce，並在整合時酌情轉換為可接受值。

下表顯示性別指標值如何對應到 Dayforce。

| Human Resources       | Dayforce                  |
|--------------|---------------------------|
| 男性         | 男性                      |
| 女性       | 女性                    |
| 非特定 | *墨西哥不支援* |

### <a name="payment-method"></a>付款方式

付款方式提供員工和公司方式說明員工獲得報酬的方法。 付款方式會對應到 Dayforce，並在整合時酌情轉換為可接受值。

下表顯示付款方式如何對應到 Dayforce。

| Human Resources             | Dayforce                  |
|--------------------|---------------------------|
| 現金               | 現金                      |
| 電子支付 | 轉帳                  |
| 支票              | 支票                    |
| 銀行匯票         | *墨西哥不支援* |
| 其他              | *墨西哥不支援* |

### <a name="bank-account-type"></a>銀行帳戶類型

銀行帳戶類型用於員工電子支付。 銀行帳戶類型以轉帳帳戶資訊對應到 Dayforce。 銀行帳戶類型在整合時酌情轉換為可接受值。

| Human Resources            | Dayforce                  |
|-------------------|---------------------------|
| 正在檢查帳戶  | CheckingAccount           |
| 工資帳戶   | PayrollAccount            |
| 活儲帳戶   | *墨西哥不支援* |
| BankGirot 帳戶 | *墨西哥不支援* |
| PlusGirot 帳戶 | *墨西哥不支援* |

### <a name="earning-codes"></a>所得代碼

所得代碼專門辨別背景工作角色收到每種唯一的所得類型。 這些代碼涵蓋幾個參數與所得有關，例如會計規則、稅法、報表要求和彙總能力。 如果使用不支援的頻率，則計算時預設會使用 **每次支付** 頻率。

#### <a name="supported-frequencies"></a>支援頻率

- 全部
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>地址

特定國家或地區、州和縣 (直轄市) 代碼的辨別需要 Dayforce 和國家/地區內提供者可以識別的特定格式。 儘管城市的格式有彈性，但每座城市都必須與州有關聯。

| Human Resources              | Dayforce              |
|---------------------|-----------------------|
| 國家/地區      | 國家/地區代碼          |
| 郵遞區號     | 郵遞區號           |
| 狀態               | 州代碼            |
| 城市                | 城市                  |
| 縣市              | 縣 (直轄市) |
| 街道              | 地址行 1        |
| 街道號碼       | 地址行 2        |
| 建築補體 | 地址行 5        |

### <a name="passport-number"></a>護照號碼

員工可以申報護照資訊。 此項資訊屬於 **護照** 身份識別類型，會以員工的墨西哥特定資訊部分整合到 Dayforce。

- 身份識別類型 = “護照”
- 核發日期
- 到期日

員工可以申報多個 **護照** 識別類型的身份證號碼。 然而，唯有目前有效的護照輸入項目才會整合到 Dayforce。 如果所有護照輸入項目均已到期，則最近核發的護照會整合到 Dayforce。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
