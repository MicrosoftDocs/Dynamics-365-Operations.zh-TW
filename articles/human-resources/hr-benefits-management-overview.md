---
title: 福利管理概觀
description: 本主題提供在 Dynamics 365 Human Resources 的福利管理功能概觀。
author: twheeloc
ms.date: 12/06/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 696c7632fd8adda71b2b67d59fba7f7d83193f5b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452178"
---
# <a name="benefits-management-overview"></a>福利管理概觀


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

為了保持競爭力，您必須提供豐富的福利吸引和留住最優秀的員工。 除了醫療和牙科保險等標準福利外，您可能也會希望提供範圍更大的服務，如領養補助、娛樂計劃和服裝津貼。 Microsoft Dynamics 365 Human Resources 中的福利管理提供彈性解決方案，支援廣泛的各種福利選項。 人力資源也包括易於使用的員工體驗，展示您的產品方案。

- 強化版的福利計劃讓您建立和管理獨一無二的福利計劃，並支援複雜的福利費率表和蜂巢式層級。 您可以輕鬆建立福利專項計劃、綁定方案和自動註冊規則，獲得更輕鬆的員工體驗。
- 彈性點數計劃讓您按比例分配支援退休和其他生活事件。
- 廣泛的資格規則確保您為正確的員工提供正確的福利。
- 線上福利註冊為您的員工提供輕鬆的體驗。
- 具備資格的生活事件處理支援未來的生活事件。

如果您希望存取示範資料，您需要重新部署沙箱環境。

> [!NOTE]
> 您現在可以客製化福利管理頁面。 與承保範疇相關的自訂欄位可以新增到福利計劃 **承保範疇選項** 頁面。 更多有關搭配自訂欄位的資訊，請參閱[自訂欄位](hr-developer-custom-fields.md)。
>
> ![福利管理自訂欄位](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>啟用福利管理

本主題說明在人力資源開啟功能的方式。 它也解釋人力資源中已被福利管理取代的既有功能，以及在您開啟福利管理後因而停用的功能。

> [!IMPORTANT]
> 在 **實際執行** 環境裡啟用福利管理後，您無法停用。 我們建議在 **實際執行** 環境中啟用福利管理前先在 **沙箱** 環境啟用和測試。 舊版福利功能和新福利管理功能之間有很明顯的差異，需要額外設定並應在放入實際執行之前測試。

更多資訊，請參閱[管理功能](hr-admin-manage-features.md)。

## <a name="process-overview"></a>流程概觀

配置福利流程涉及的任務如下：

1.  設定必要的福利資訊。
2.  設定非必要的福利資訊。
3.  設定福利計劃。
4.  設定彈性點數專項計劃 (非必要)。
5.  配置必要的員工資訊。
6.  配置非必要的員工資訊。
7.  處理員工以判定資格。
8.  員工透過員工自助服務選取計劃 (可選)。
9.  確認員工計劃選取項目。
10. 生活事件處理 (可選)。
11. 費率更新 (可選)。

## <a name="set-up-required-benefit-information"></a>設定必要的福利資訊

員工可以註冊計劃之前必須設定多個組成元素：

- **福利管理參數** – 這些設定是跨公司共用。 您可以設定預設原因代碼，啟用 **福利年薪** 選項，為新進員工設定預設付款頻率，並啟用生活事件。 更多資訊，請參閱[設定福利管理參數](hr-benefits-setup-parameters.md)。
- **個人聯絡人資格選項** – 個人聯絡人是將成為設定計劃的家屬或受益人的個人。 他們典型是孩子、配偶或信託組織。 更多資訊，請參閱[配置個人聯絡資格選項](hr-benefits-setup-contact-eligibility-options.md)。
- **承保範疇選項** – 設定可在計劃開放使用的承保類型。 具體定義應為被保人的身份，或者開放的承保範疇大小。 更多資訊，請參閱[建立承保範疇選項](hr-benefits-setup-coverage-options.md)。
- **計劃類型** – 設定您建立福利計劃時將開放使用的計劃類型。 計劃類型範例包括 **牙科**、**視力** 和 **儲蓄**。 計劃類型上的若干重要設定即可判定福利計劃上開放的設定。 更多資訊，請參閱[建立計劃類型](hr-benefits-setup-plan-types.md)。
- **資格規則** – 資格規則用來判定員工是否具備享有福利計劃的資格。 每項福利計劃至少必須與一條資格規則有關聯。 更多資訊，請參閱[配置資格規則和選項](hr-benefits-setup-eligibility-rules.md)。
- **付款頻率** – 配置福利費率時需要的付款頻率。 費率上使用的付款頻率有助於辨別員工和/或雇主每週、每月或每年欠款的金額。 更多資訊，請參閱[設定付款頻率](hr-benefits-setup-payment-frequencies.md)。
- **費率** – 費率定義員工或雇主的福利成本高低。 如果應該把錢分配給員工 (例如，成為健身房會員的點數)，請輸入負費率。 更多資訊，請參閱[配置費率](hr-benefits-setup-rates.md)。
- **階層費率** – 當費率必須根據若干標準變更時，即使用階層費率。 最常見的層級費率是以年齡為準的單一階層。 然而您也可以設定雙倍階層費率，其中費率可能會根據性別、年齡或其他標準變更。
- **扣除額** – 扣除額基本上是標題資訊/代碼，將傳遞到工資單系統辨別福利扣除額。 您必須設定這些扣除額，因為福利計劃將需要這些扣除額。 更多資訊，請參閱[配置扣除額](hr-benefits-setup-deductions.md)。
- **福利期間** – 福利期間是員工將納入福利涵蓋的期間。 它也稱為計劃年份。 這裡也設定開放註冊期間。

## <a name="set-up-optional-benefit-information"></a>設定非必要的福利資訊

建立福利計劃不必設定下列組成元素：

- **專項計劃** – 專項計劃是一套由相同資格規則主導的福利。 例如，銷售部門的每個人都可能得到一支手機。
- **綁定方案** – 綁定方案是一組福利，其中必須先選取一項計劃，才能選取額外開放的計劃。 例如，高扣除額醫療計劃可能與健康儲蓄帳戶 (HSA) 計劃搭配成綁定方案。
- **生活事件類型** – 生活事件是允許變更員工承保範疇的事件。 生活事件類型與計劃類型連結。 例如，醫療計劃類型可能允許因出生或領養或婚姻狀態變動而變更計劃內容。 然而保險計劃類型可能不允許因為生活事件而進行的任何變更。 更多資訊，請參閱[配置生活事件類型](hr-benefits-setup-life-event-types.md)。
- **等待天數和等待期間** – 可以在福利計劃上設定承保等待期間。 例如，新錄用員工可能只在就業三個月後才能註冊 401(k)。 此時等待期間為三個月。 如果只能在一個月的特定日處理新註冊及提交給提供者，則會在等待期間使用等待天數。 例如，如果 401(k) 註冊只能在每個月的 15 日處理，則就業三個月後，設定的等待期間為三個月，等待日為 15 日。 更多資訊，請參閱[配置等待天數](hr-benefits-setup-waiting-days.md)和[配置等待期間](hr-benefits-setup-waiting-periods.md)。
- **原因代碼** – 原因代碼用來解釋員工福利可能變更的原因。 更多資訊，請參閱[設定原因代碼](hr-benefits-setup-reason-codes.md)。

## <a name="set-up-benefit-plans"></a>設定福利計劃

當您設定福利計劃時，您必須先完成下列步驟才能註冊員工：

- 指派福利期間。
- 附加承保範疇選項。
- 在 **一般** 索引標籤上設定生效日期和失效日期。
- 至少指派一項資格規則。
- 請在 **設定** 索引標籤上設定 **允許/繼續註冊** 欄位。

更多有關設定福利計劃方式的資訊，請參閱[設定福利計劃](hr-benefits-plans-setup.md)。

## <a name="set-up-flex-credit-programs-optional"></a>設定彈性點數專項計劃 (非必要)

您可以根據預定的彈性點數使用彈性點數專項計劃在福利註冊員工。 員工可以選擇分配他們彈性點數的方式。 例如，如果員工已經納入配偶的醫療保健計劃承保範疇，他們就不必將自己的點數用於醫療保健的承保範疇。 因此，他們可能希望將用於其他福利。 更多有關彈性點數專項計劃資訊，請參閱[設定彈性點數專項計劃](hr-benefits-plans-flex-credit-programs.md)。

## <a name="configure-required-employee-information"></a>配置必要的員工資訊

在您為員工註冊福利之前，您必須為他們提供必要的資訊。 

員工必須有指配給它們的 **職位**。 **職位** 可在 **背景工作角色** 或 **職位** 頁面上藉由更新 **背景工作角色指派** 指派給員工。 

下一步，員工必須在他們的開始日期當天註冊到固定薪酬計劃，或者有 **年福利薪資** 金額。 指派 **固定薪酬** 給員工之前必須先指派 **職位**。 

> [!NOTE] 
> **固定薪酬開始日期** 不能在 **職位指派日期** 之前。

或者，如果您的員工收到比方佣金的補充薪酬，您可以新增員工記錄的 **福利年薪** 金額。 人力資源在判定承保範疇金額時將使用 **福利年薪金額**，而不是 **固定年度薪酬** 金額。 **福利年薪** 必須自員工的開始日期起或福利期間開始時有效，以較晚者為準。 然而不需要指派 **福利年薪** 的職位。 若要啟用 **福利年薪** 功能，請前往 **人力資源共用參數** 頁的 **福利管理** 索引標籤。本功能預設情況下是關閉。

> [!IMPORTANT]
> 如果已輸入員工的 **固定薪酬** 和 **福利年薪** 金額，則 **福利年薪** 將用來判定承保範疇的金額。 您必須在 **背景工作角色** 頁的 **就業細節** 區選取 **福利支付頻率** 欄位值。

## <a name="configure-optional-employee-information"></a>配置非必要的員工資訊
當您建立使用性別或年齡基礎費率的福利計劃時，您必須輸入員工的出生日期和性別才能計算福利成本。

## <a name="process-employees-to-determine-eligibility"></a>處理員工以判定資格
員工可以註冊計劃之前會執行資格處理判定他們有資格參加的計劃。 您可以在 **處理結果檢視器** 中檢視資格流程結果。 更多資訊，請參閱[處理註冊資格](hr-benefits-process-enrollment-eligibility.md)。

## <a name="employees-select-plans-using-employee-self-service-optional"></a>員工使用 **員工自助服務** 選取計劃 (可選)

當發生開放註冊、員工為新進員工或生活事件時，員工可以使用 **員工自助服務** 選取或更新他們的福利。 更多資訊，請參閱[配置員工自助服務](hr-benefits-setup-employee-self-service.md)。

## <a name="confirm-employee-plan-selections"></a>確認員工計劃選取項目

員工選取的福利必須在將考慮將他們註冊之前確認。 也可以代表員工選取福利。 若要選取或確認福利，請在 **福利** 索引標籤上的 **員工** 頁選取 **背景工作角色福利計劃**。 若要選取或確認多名員工的福利，請使用 **背景工作角色福利計劃大量更新** 頁面。

## <a name="life-event-processing-optional"></a>生活事件處理 (可選)

員工生命週期期間，每位員工可能會經歷各種生活事件，例如婚姻、就業變動或家屬或受益人變動。 若要使用生活事件，您必須在 **人力資源共用參數** 頁面上啟用。 設定生活事件類型以及針對計劃類型設定生活事件選項。

在您可以處理生活事件之前，您必須在錄用時限內至少執行一次開放註冊。 美國典型的開放註冊是每年發生一次。 美國境外則是錄用時可能發生開放註冊。 生活事件處理不需要背景工作角色選取福利計劃。 然而背景工作角色必須已經納入開放註冊處理範圍。 有關詳細資訊，請參閱下列主題：

- [處理生活事件](hr-benefits-process-life-events.md)
- [處理生命事件變更](hr-benefits-process-life-event-changes.md)
- [處理生命事件資格](hr-benefits-process-life-event-eligibility.md)

## <a name="rate-updates-optional"></a>費率更新 (可選)

偶爾福利費率會在計劃期間變動。 若要更新已經註冊計劃的員工費率，您必須處理費率變更。 更多資訊，請參閱[處理費率變更](hr-benefits-process-rate-changes.md)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
