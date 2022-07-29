---
title: 定義和管理福利專項計劃
description: 人力資源提供一套工具，可用來設定與維護組織為背景工作角色提供或處理的福利、扣除額與背景工作角色薪酬計劃。 本主題提供有關如何設定和管理福利的資訊。
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 1f2bfa901aa299a091194978ee95ff0e69f2cdbf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452121"
---
# <a name="define-and-manage-a-benefits-program"></a>定義和管理福利專項計劃


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

人力資源提供一套工具，可用來設定與維護組織為背景工作角色提供或處理的福利、扣除額與背景工作角色薪酬計劃。 本主題提供有關如何設定和管理福利的資訊。

## <a name="benefit-setup"></a>福利設定

在背景工作角色可以在福利註冊之前，您必須建立每個福利的元素。 這些元素結合類似福利計劃並定義預設設定，例如扣除費率和會計細節。 當背景工作角色日後在福利註冊時，可以調整其中許多設定。 組織可以針對每項福利計劃提供幾個註冊選項，或者背景工作角色可以放棄此計劃的註冊。 

[![福利流程。](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>福利要素

在您開始建立福利並從中註冊員工之前，您必須定義組成福利的元素：類型、計劃和選項。

-   **類型** – 針對特定福利的計劃集合物件，例如醫療或停車。
-   **計劃** – 提供者簽約的特定福利。
-   **選項** – 承保範疇等級，例如僅限員工，或員工和配偶/同居伴侶。

各種類型的福利，例如視力或牙科，組織可為其背景工作角色提供一項或多項計劃。 各項計劃方面，組織可以提供不同的選項。 例如，背景工作角色可以按照年薪的一倍、兩倍或三倍投保額外的定期人壽保險。 計劃和選項的每種組合都成為背景工作角色可以註冊的福利。 

[![福利圖片。](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>資格
許多因素可判定背景工作角色是否有資格獲得雇主提供的各種福利。 當您在 Dynamics 365 Human Resources 建立福利時，您可以設定適用該項福利的資格類型。 

您可以開放全體員工享有福利。 例如，若干公司向全體員工提供停車證作為附加福利。 建立此項福利時，您將資格設定為 **所有背景工作角色都有資格**。 

其他福利方面，例如扣押債務人財產通知和稅捐稽徵，資格並不適用。 當您建立這些類型的福利時，您將資格設定為 **繞過資格流程**。 

最後，福利資格可以規則為基礎。 例如，公司為員工提供兩種類型的人壽保險福利。 行政高層員工有資格享有一項人壽保險計劃，而其他所有全職員工則有資格享有另一項人壽保險計劃。 您可以在人力資源建立福利資格規則來尋找所有行政高層員工，及另一項規則尋找其他所有全職員工，然後將這些規則套用在適當的福利。

## <a name="enrollment"></a>註冊
待您已經建立貴組織提供的福利並判定資格後，您可以在福利註冊您的背景工作角色。 您可以在福利中註冊一名背景工作角色，或者單一流程期間將多名背景工作角色註冊一項或多項福利。 

偶爾組織會停止提供特定福利。 此時您必須更新福利和註冊的背景工作角色。 集體福利到期讓您同時變更福利和背景工作角色註冊的到期日期。 您也可以選取在福利註冊的多名背景工作角色並且變更他們承保範疇的結束日期。 

同樣地，如果您決定提供比原先計劃更久的福利，大規模福利延期可讓您延長福利和該福利的背景工作角色註冊的到期日期。




[!INCLUDE[footer-include](../includes/footer-banner.md)]
