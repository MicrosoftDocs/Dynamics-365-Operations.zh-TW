---
title: 配置生活事件類型
description: Microsoft Dynamics 365 Human Resources 使用生活事件類型來定義事件以更新員工福利註冊。
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aab35d40af43caff7010998ddce51350584228a1
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452511"
---
# <a name="configure-life-event-types"></a>配置生活事件類型


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources 使用 **生活事件類型** 定義更新員工福利註冊有效事件，例如結婚或生子。 每個生活事件類型識別碼只能與一個生活事件類型產生關聯。 例如，如果您建立與 **員工地址變更** 生活事件類型有關聯的 **生活事件識別碼**，稱為 **地址變更**，而您無法建立另一個標記為 **員工地址變更** 的識別碼與 **員工地址變更** 生活事件類型產生關聯。 如果生活事件類型未與計劃類型產生關聯，則生活事件類型將不會觸發生活事件。 更多資訊，請參閱[建立計劃類型](hr-benefits-setup-plan-types.md)。

## <a name="create-a-life-event-type"></a>建立生活事件類型

1. 請在 **設定** 下方的 **福利管理** 工作區選取 **生活事件類型**。

2. 選取 **新增**。

3. 請指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **生活事件類型識別碼** | 生活事件類型唯一的識別碼。 |
   | **描述** | 生活事件類型說明。 |
   | **生活事件類型** | 更新員工福利註冊的催化劑。 有關生活事件清單，請參閱下方的[生活事件](hr-benefits-setup-payment-frequencies.md?life-events)。 |

4. 選取 **儲存**。

## <a name="view-attached-plans"></a>檢視附加計劃

您可以看到附加到選取的 **生活事件類型** 的計劃清單。 生活事件附加到計劃類型，並且計劃類型與計劃有關聯。

1. 請在 **設定** 下方的 **福利管理** 工作區選取 **生活事件類型**。

2. 選取 **動作**。

3. 選取 **附加計劃**。

## <a name="life-events"></a>生活事件

建立生活事件類型時，您可以從下列生活事件選擇：

| 生活事件 | 位置 | 觸發程序 |
| --- | --- | --- |
| **婚姻狀況變更** | **背景工作角色>設定檔>個人資訊>婚姻狀況**| 婚姻狀況變更 |
| **就業狀況變更** |**背景工作角色>就業>就業歷程頁面** | 已有既有就業細節的背景工作角色，建立就業狀況不同的新就業細節將觸發生活事件。  使用不同的就業狀況更新既有的就業細節也將觸發生活事件。  |
| **員工地址變更** |**背景工作角色>設定檔>地址**</li><li>**背景工作角色>個人資訊>個人聯絡人>地址**</li></ul> | 地址變更。 地址必須是觸發生活事件的 **主要** 元素。 |
| **家屬變更** |<br><ul><li>**背景工作角色>設定檔>個人資訊>個人聯絡人>地址**/li><li>**員工自助服務**</li></ul> | 新增個人聯絡人並將他們指明為家屬和定義 **生效日期**。 更新個人聯絡人的家屬 **失效日期** 資訊。 個人聯絡人的關係必須是孩子、配偶、同居伴侶或前配偶。  |
| **出生或收養 (家屬)** |<br><ul><li>**背景工作角色>設定檔>個人資訊>個人聯絡人**</li><li>**員工自助服務>編輯個人細節>個人聯絡人**</li></ul>| 新增或更新 **出生日期** 或 **收養日期**。 孩子的 **出生日期** 是必要資訊。 |
| **承保範疇失效 (配偶/同居伴侶)** | 背景工作角色>設定檔>個人資訊>個人聯絡人>家屬細節>承保範疇失效 | **承保範疇失效** 個人聯絡人選取項目和 **生效日期** |
| 同居伴侶就業變更 | **背景工作角色>設定檔>個人資訊>個人聯絡人>家屬細節>在職** | 建立個人聯絡人和設定 **在職** 為 **是**。 更新個人聯絡人並變更 **在職**。  |
| **請假 (配偶/同居伴侶)** | **背景工作角色>設定檔>個人資訊>個人聯絡人>家屬細節>請假** | 已建立個人聯絡人和定義 **請假生效日期**。 已更新個人聯絡人 **請假**。 已更新個人聯絡人 **請假生效日期**。  |
| **承保範疇變更 (職位)** |<br><ul><li>**背景工作角色>職位指派>背景工作角色指派**</li><li>**職位>職位**</li></ul>| 背景工作角色職位指派記錄中的職位變更。 背景工作角色的職位變更。 |
| **承保範疇變更 (薪資)** |<br><ul><li>**背景工作者>薪酬>固定計劃**</li><li>**背景工作角色>個人資訊>福利年薪**</li></ul>| 如果並未啟用 **福利管理>人力資源共用參數>福利>福利年薪**，則更新 **背景工作角色>薪酬>固定計劃** 將建立生活事件。 如果啟用 **福利管理>人力資源共用參數>福利>福利年薪**，則更新 **背景工作角色>個人資訊>福利年薪** 將建立生活事件。 |
| **醫療保險 (員工/家屬)** | **背景工作角色>設定檔>個人資訊>個人聯絡人>家屬細節>醫療生效日期** | 新增或更新個人聯絡人的 **醫療生效** 日期會建立此生活事件。 |
| **法院下令支援** | **背景工作角色>設定檔>個人資訊>個人聯絡人>家屬>法院下令支援** (QMSCO/QDRO) 和生效日期 | 建立個人聯絡人時，如果 **法院下令支援** 為 **是**，將一併建立生活事件。 更新 **法院下令支援** 或 **法院下令的到期日期** 也將會觸發生活事件。 |
| **逝世** | **背景工作角色>設定檔>個人資訊>逝世日期** | 輸入或更新 **逝世日期**。 |
| **保險證據** | **背景工作角色>背景工作角色>版本>就業歷程>日期管理員>福利詳情** | **投保證據** 設定為 **是**。 已定義 **投保證據的驗證日期**。 |
| **受益人** | **背景工作角色>設定檔>個人資訊>個人聯絡人** | 已新增個人聯絡人，並已填滿 **受益人** 和 **生效日期** 欄位。 個人聯絡人必須屬於 **孩子**、**配偶**、**DomesticPartner**、**手足**、**FamilyContact**、**OtherContact** 或 **家長** 類型。 |
| **員工醫療保險** | **背景工作角色>背景工作角色>版本>就業歷程>日期管理員>福利詳情** | **符合醫療保險資格** 設定為 **是**。 已變更 **醫療保險具備資格日期**。 |
| **生日** | **福利管理>生活事件變更處理** | 這些生活事件是由 **生活事件變更處理** 建立。 這段流程分析選擇期間和法人實體並尋找關聯背景工作角色。 它計算他們上一次的生日，如果生日生活事件尚未建立，則逕自建立。 |
| **背景工作角色資格變更 (非美國特定)** |<br><ul><li>**背景工作角色>就業**</li><li>**背景工作角色>背景工作角色>版本>就業歷程**</li></ul>| 發生下列情況時建立生活事件：<br><ul><li>建立新就業，已有之前的就業，而背景工作角色類型有變更。</li><li>建立新就業細節，並且已有之前的就業細節，而就業類型或就業類別變更。</li><li>更新就業記錄並定義不同的背景工作角色類型。</li><li>更新就業詳細記錄並指明不同的就業類型或類別。</li></ul> |
| **新資格覆寫 (非美國特定)** | **人力資源進階>福利>計劃>福利>資格規則覆寫** | 使用生活事件處理<br>為背景工作角色建立新福利計劃資格覆寫會觸發此生活事件。<br>BenefitEligibilityRuleOverride.ValidFrom. |
| **資格規則覆寫變更 (非美國特定)** | **人力資源進階>福利>計劃>福利>資格規則覆寫** | 更新福利計劃資格覆寫 **生效** 或 **失效** 會觸發此生活事件。 |
| **資格規則覆寫到 (非美國特定)** | 福利管理>生活事件變更處理  | 這些生活事件是由 **生活事件變更處理** 建立。 這段流程分析選擇期間和法人實體並尋找關聯福利計劃資格覆寫。 如果覆寫已到期，會建立生活事件。 |
| **新福利計劃 (非美國特定)** | **人力資源進階>福利>計劃>新建** | 資格選項已新增到目前計劃。 已新增附加資格選項的新計劃。</br></br>在本執行個體中，人力資源人事應執行生活事件資格處理。 |
| **資格規則變更 (非美國特定)** | **福利管理>資格規則** | 使用生活事件資格處理。 記錄 **BenefitEligibilityRule** 記錄變更下列值：**UseEmplCategory**、**UseEmplStatus**，或 **UseEmplType** 的時間。 只更新規則或資格標準已經變更的生活事件交易。 |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
