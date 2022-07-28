---
title: 為最佳化諮詢建立規則
description: 本主題討論如何向最佳化諮詢新增新規則。
author: roxanadiaconu
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a65a71da066d70cafc641aafe21538830a9ebe56b607316570ea2435398cda1c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460327"
---
# <a name="create-rules-for-optimization-advisor"></a>為最佳化諮詢建立規則

[!include [banner](../includes/banner.md)]

本主題說明如何為 **最佳化諮詢** 建立新規則。 例如，您可以建立一個新規則來識別哪些詢價 (RFQ) 案例的標題為空白。 在案例上使用標題使它們易於識別和搜尋。 雖然非常簡單，但此範例顯示了使用最佳化規則可以實現的目標。 

某 *規則* 是對應用程式資料的檢查。 如果滿足規則評估的條件，就會創造最佳化流程或改進資料的商機。 可以對商機採取行動，並且具有選取性，可以衡量行動的影響。 

若要為 **最佳化諮詢** 建立新規則，請新增一個擴展 **SelfHealingRule** 抽像類、實現 **IDiagnosticsRule** 介面並由 **DiagnosticRule** 屬性修飾的新類。 該類還必須有一個用 **DiagnosticsRuleSubscription** 屬性修飾的方法。 按照慣例，這是在 **opportunityTitle** 方法上完成的，這將在後面討論。 這個新類可以新增到相依性於 **SelfHealingRules** 模型的自訂模型中。 在以下範例中，正在實施的規則稱為 **RFQTitleSelfHealingRule**。

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

**SelfHealingRule** 抽像類具有必須在繼承類中實現的抽象方法。 該核心是 **評估** 方法，它回傳由規則識別的商機清單。 商機可以是每個法律實體，也可以適用於整個系統。

```xpp
protected List evaluate() 
{ 
    List results = new List(Types::Record); 
    
    DataArea dataArea; 

    while select id from dataArea 
        where !dataArea.isVirtual 
    { 
        changecompany(dataArea.id) 
        { 
            container result = this.findRFQCasesWithEmptyTitle(); 

            if (conLen(result) > 0) 
            { 
                SelfHealingOpportunity opportunity = this.getOpportunityForCompany(dataArea.Id); 
                opportunity.EvaluationState = SelfHealingEvaluationState::Evaluated; 
                opportunity.Data = result; 
                opportunity.OpportunityDate = DateTimeUtil::utcNow(); 
                
                results.addEnd(opportunity); 
            } 
        } 
    } 
    
    return results; 
} 
```

上面顯示的方法循環遍歷公司並在 **findRFQCasesWithEmptyTitle** 方法中選取標題為空白的 RFQ 案例。 如果找到至少一個此類案例，則使用 **getOpportunityForCompany** 方法建立公司特定的商機。 請注意，**SelfHealingOpportunity** 表中的欄位 **資料** 屬 **容器** 類型，因此可以包含與特定於該規則的邏輯相關的任何資料。 使用現行時間戳設定 **OpportunityDate** 會記錄商機的最新評估時間。  

商機也可以是跨公司的。 在這種情況下，不需要對公司進行循環，並且必須使用 **getOpportunityAcrossCompanies** 方法建立商機。 

以下代碼顯示了 **findRFQCasesWithEmptyTitle** 方法，該方法回傳標題為空白的 RFQ 案例的 ID。

```xpp
private container findRFQCasesWithEmptyTitle() 
{ 
    container result; 

    PurchRFQCaseTable rfqCase; 
    while select RFQCaseId from rfqCase 
        where rfqCase.Name == '' 
    { 
        result += rfqCase.RFQCaseId; 
    } 
    
    return result; 
} 
```

另外兩個必須實施的方法是 **opportunityTitle** 和 **opportunityDetails**。 前者回傳商機的簡短標題，後者回傳商機的詳細描述，其中還可以包含資料。

**opportunityTitle** 回傳的標題出現在 **最佳化諮詢** 工作區的 **最佳化商機** 資料欄下。 它還顯示為側邊窗格的標題，顯示有關商機的更多資訊。 按照慣例，此方法使用 **DiagnosticRuleSubscription** 屬性修飾，該屬性採用以下引數： 

* **診斷區域** – **DiagnosticArea** 類型的列舉，描述規則所屬的應用程式區域，例如 **DiagnosticArea::SCM**。 

* **規則名稱** – 帶有規則名稱的字串。 這將出現在 **診斷驗證規則** 表單 (**DiagnosticsValidationRuleMaintain**) 的 **規則名稱** 資料欄下。 

* **執行頻率** – **DiagnosticRunFrequency** 類型的列舉，描述規則應執行的頻率，例如 **DiagnosticRunFrequency::Daily**。 

* **規則描述** – 具有更詳細的規則描述的字串。 這將出現在 **診斷驗證規則** 表單 (**DiagnosticsValidationRuleMaintain**) 的 **規則描述** 資料欄下。 

> [!NOTE]
> 該規則需要 **DiagnosticRuleSubscription** 屬性才能正常工作。 通常，它用於 **opportunityTitle**，但它可以裝飾類的任何方法。

下面是一個範例實施。 為簡單起見使用原始字串，但正確的實施需要標籤。 

```xpp
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

**opportunityDetails** 回傳的描述顯示在顯示有關商機的更多資訊的側邊窗格中。 這需要 **SelfHealingOpportunity** 引數，它是 **資料** 欄位，可用於提供有關商機的更多詳情。 在範例中，該方法回傳 RFQ 案例的 ID，標題為空白。 

```xpp
public str opportunityDetails(SelfHealingOpportunity _opportunity) 
{ 
    str details = ''; 
    container opportunityData = _opportunity.Data; 
    int affectedRFQCasesCount = conLen(opportunityData); 

    if (affectedRFQCasesCount != 0) 
    { 
        details = 'The following Request for Quotation cases have an empty title:\n'; 
        for (int i = 1; i <= affectedRFQCasesCount ; i++) 
        { 
            PurchRFQCaseId rfqCaseId = conPeek(opportunityData, i); 
            details += rfqCaseId + '\n'; 
        } 
    } 

    return details; 
}
```

剩下的兩個要實施的抽象方法是 **provideHealingAction** 和 **securityMenuItem**。 

如果提供了治療動作，**provideHealingAction** 回傳 True，否則回傳 False。 如果回傳 True，則必須實施方法 **performAction**，否則會引發錯誤。 **performAction** 方法採用 **SelfHealingOpportunity** 引數，其中資料可用於該動作。 在範例中，該動作打開 **PurchRFQCaseTableListPage**，以進行手動更正。 

```xpp
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

根據該規則的具體情況，可能會使用商機資料採取自動操作。 在此範例中，系統可以自動產生 RFQ 案例的標題。 

**securityMenuItem** 回傳操作選單項目的名稱，以便該規則僅對可以存取操作選單項目的使用者顯示。 安全性可能要求特定規則和商機只能由授權使用者存取。 在範例中，只有有權存取 **PurchRFQCaseTitleAction** 的使用者才能查看商機。 請注意，此動作選單項目是為此範例建立的，並被新增為 **PurchRFQCaseTableMaintain** 安全性權限的進入點。 

> [!NOTE]
> 選單項目必須是動作選單項目，安全性才能正常運作。 其他選單項目類型，例如 **顯示選單項目** 將無法正常運作。

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

在編譯規則後，執行以下作業以使其顯示在使用者介面 (UI) 中。

```xpp
class ScanNewRulesJob 
{         
    public static void main(Args _args) 
    {         
        SysExtensionCache::clearAllScopes(); 
        var controller = new DiagnosticsRuleController(); 
        controller.runOperation(); 
    } 
} 
```

該規則將顯示在 **診斷驗證規則** 表單中，可從 **系統管理** > **定期工作** > **維護診斷驗證規則** 獲得。 若要對其進行評估，請存取 **系統管理** > **定期工作** > **安排診斷驗證規則**，選取規則的頻率，如 **每日**。 點選 **確定**。 進入 **系統管理** > **最佳化諮詢** 查看新商機。 

以下範例是包含所有必需方法和屬性的規則架構的代碼片段。 它可以幫助您開始編寫新規則。 範例中使用的標籤和操作菜單項僅用於演示目的。

```xpp
[DiagnosticsRuleAttribute]
public final class SkeletonSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule
{
    [DiagnosticsRuleSubscription(DiagnosticsArea::SCM,
                                 "@SkeletonRuleLabels:SkeletonRuleTitle", // Label with the title of the rule
                                 DiagnosticsRunFrequency::Monthly,
                                 "@SkeletonRuleLabels:SkeletonRuleDescription")] // Label with a description of the rule
    public str opportunityTitle()
    {
        // Return a label with the title of the opportunity
        return "@SkeletonRuleLabels:SkeletonOpportunityTitle";
    }

    public str opportunityDetails(SelfHealingOpportunity _opportunity)
    {
        str details = "";

        // Use _opportunity.data to provide details on the opportunity

        return details;
    }

    protected List evaluate()
    {
        List results = new List(Types::Record);

        // Write here the core logic of the rule

        // When creating an opportunity, use:
        //     * this.getOpportunityForCompany() for company specific opportunities
        //     * this.getOpportunityAcrossCompanies() for cross-company opportunities

        return results;
    }

    public boolean providesHealingAction()
    {
        return true;
    }

    protected void performAction(SelfHealingOpportunity _opportunity)
    {
        // Place here the code that performs the healing action

        // To open a form, use the following:
        // new MenuFunction(menuItemDisplayStr(SkeletonRuleDisplayMenuItem), MenuItemType::Display).run();
    }

    public MenuName securityMenuItem()
    {
        return menuItemActionStr(SkeletonRuleActionMenuItem);
    }

}
```

如需相關資訊，請觀看 YouTube 短片：[Dynamics 365 for Finance and Operations 中的最佳化諮詢](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]