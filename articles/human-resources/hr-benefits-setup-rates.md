---
title: 配置費率
description: Microsoft Dynamics 365 Human Resources 費用負責定義雇主和員工在福利的撥付佔比。
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2822f6e339323ca6731ef042ffef3c400ae077d4
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452436"
---
# <a name="configure-rates"></a>配置費率


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

費率負責定義雇主和員工在福利的撥付金額佔比。 數值可以根據您的配置為金額或彈性點數。

根據幾項因素，使用費率判定員工和雇主為每項福利支付的金額。 覆寫率以有效日期為準，因此您可以保存費率的歷史記錄。 

## <a name="set-up-rates"></a>設定費率

1. 請在 **設定** 下方的 **福利管理** 工作區選取 **費率**。

2. 選取 **新增**。

3. 請指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **費率** | 辨別福利費率的唯一名稱。 |
   | **描述** | 福利費率說明。 |
   | **生效** | 費率生效的日期。 預設值為目前的系統日期。 此日期應在您的福利期當天或之前。 完善的做法是將此日期設定為福利計劃的日期。 |
   | **到期** | 費率結束日期。 預設值為 12/31/2154 (代表從未發生)。 |
   | **使用層** |  如果您有必須用來判定費率的邏輯，請使用此欄位。 例如，如果費率必須根據年齡增加，請在這裡選取一值。 單層福利費率則選取 **單層** 或兩層福利費率則選取 **兩層**。 雙層範例是根據性別和年齡的分層。 選擇一值後，選取 **動作**，然後選取 **分層費率**。 如果您的統一費率一向維持不變，請將此欄位留空白。 |
   | **付款頻率** | 指明應支付福利提供商福利費率的間隔時間。 您在本主題稍候說明的頁面上輸入的費率將以您在這裡指定的付款頻率為主。 例如，如果您在本欄位輸入 **按月**，並且輸入 **$100** 的員工費率，可以假設每個月福利將花費員工 $100。 不過，根據員工記錄設定的福利付款頻率，員工可能每個月收到兩筆款項。 此時當員工登入 **員工自助服務** 時，他們支付的金額將是 $50，因為 **員工自助服務** 顯示的費率以員工的付款頻率為主。 |
   | **支付頻率費率四捨五入** | 費率四捨五入的方法包括：標準、截斷、正常、向下和向上四捨五入。 </br></br><ul><li>**標準** – 總是四捨五入。 例如，10.611 四捨五入後將是 10.62。 -10.231 四捨五入後將是 -10.23。 </li><li>**截斷** – 總是向下四捨五入。 例如，10.619 四捨五入後將是 10.61。 -10.231 四捨五入後將是 -10.24。 </li><li>**正常** – 5 結尾或大於 5 結尾的十進位值將從零四捨五入。 4 結尾或小於 4 結尾的十進位值將向零四捨五入。 例如，10.615 四捨五入後將是 10.62。 -10.235 四捨五入後將是 -10.24。 10.614 四捨五入後將是 10.61。 -10.234 四捨五入後將是 -10.23。 </li><li>**向下** – 向零四捨五入。 例如，10.619 四捨五入後將是 10.61。 -10.231 四捨五入後將是 -10.23。 </li><li>**向上進位** – 從零四捨五入。 例如，10.619 四捨五入後將是 10.62。 -10.231 四捨五入後將是 -10.24。 |
   | **非吸煙員工金額** | 福利提供商支付給不吸煙員工的金額。 這是雇主支付給福利提供者的金額，應以費率設定的付款頻率為主。 |
   | **非吸煙雇主金額** | 福利提供商支付給不吸煙員工的金額。 這是雇主支付給福利提供者的金額，應以費率設定的付款頻率為主。 |
   | **吸煙員工金額** | 福利提供商向吸煙員工收費的金額。 這是雇主支付給福利提供者的金額，應以費率設定的付款頻率為主。 |
   | **吸煙雇主金額** | 福利提供商向吸煙員工收費的金額。 這是雇主支付給福利提供者的金額，應以費率設定的付款頻率為主。 |
   | **行政管理金額** | 第三方系統管理員收取的行政管理費金額。 這是雇主支付第三方行政管理人的金額，應以費率設定的付款頻率為主。 |
   | **彈性點數費率** | 計入福利成本的彈性點數。 這只適用與彈性點數專項計劃相關聯的福利計劃費率。 如果您使用分層費率，則在動作 > 分層費率中定義彈性點數費率。 |
   | **變更生效日期** | 福利費率變更生效的日期。 系統將自動更改福利費率並更新與此費率關聯的所有福利計劃，前提是您執行費率更改更新處理。 請勿設定此日期，除非您希望系統根據此費率自動更新員工福利計劃。 這一般會預留給未來自動費率更改處理的時候。 **更改生效日期** 必須在福利費率的生效日期和到期日期內。 |
   | **費率更改完成** | 一旦福利費率變更動作經由費率更改更新處理完成，將自動選取 **費率變更完成** 勾選方塊。 |

4. 若要追蹤和維護對福利費率設定的變更，請選取 **動作** 和 **維護版本**。

5. 選取 **儲存**。 

## <a name="set-up-tier-rates"></a>設定分層費率

如果費率因各種因素而異，您可以在費率設定中使用分層費率。 例如，您可以將分層費率配置為如果您的年齡達到 34.99，則非吸煙者數額為 2。 如果您的年齡達到 39.99，則非吸煙數額為 3。

您也可以使用雙層。 如果您在 **費率設定** 表單上針對 **使用層** 值選取 **雙層**，您就能根據兩個維度定義費率。 例如，您可以將雙層制度配置為如果您是男性，而且年齡達到 34.99，則非吸煙者數額為 2。 如果您是男性，而且年齡達到 39.99，則非吸煙數額為 3。 如果您是女性，而且年齡達到 34.99，則非吸煙數額為 1.8。 如果您是女性，而且年齡達到 39.99，則非吸煙數額為 2.8。

> [!IMPORTANT]
> **個人資訊** 下方的背景工作角色記錄有一個用來指出員工是否吸煙的選項。 如果員工被記錄為吸煙者，將使用吸煙者費率。 (吸煙者指示絕不向員工顯示。)
   
1. 請在 **設定** 下方的 **福利管理** 工作區選取 **費率**。

2. 從清單選取一個或多個費率，選取 **動作**，然後選取 **分層費率**。

3. 選取 **新增**。

3. 請指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- | 
   | **描述** | **說明** 欄位值從費率設定記錄中的說明套用。 這有助於您辨別分層費率連結的費率設定。 |
   | **分層代碼** | 選取分層代碼。 分層代碼在 **分層代碼** 頁定義。 系統會自動在左側格線顯示分層代碼說明。 |
   | **分層類型** | 指明應當成分層費率計算流程選取標準的欄位。 例如： </br></br><ul><li>如果使用 **年齡**，系統將在福利費率計算流程使用員工的出生日期。</li><li>如果使用 **薪資**，系統將在福利費率計算流程使用員工的年度福利薪資。</li><li>如果使用 **工作類型**，則員工的有效現職記錄會用來按照連結該職位的工作記錄，判定工作類型。</li></ul></br></br>分層類型是 **年齡**、**薪資**、**身體健康**、**性別**、**全職 (等效)**、**工作類型**、**薪酬區域** 和 **等級**。 | 
   | **等級** | 福利費率計算流程期間搭配分層類型使用的值。 例如： </br></br><ul><li>如果分層類型是 **年齡**，就會是年齡值。</li><li>如果分層類型是 **薪資**，就會是薪資金額。</li><li> 如果分層類型是 **工作類型**，就會是工作類型。</li></ul></br></br>分層類型 **年齡** 或 **薪資** 方面，**等級** 欄位值代表分層上限。 分層類型 **工作類型** 方面，分層費率選取期間使用精確比對方法。 |
   | **計算類型** | 指明如何使用計算金額欄位中的金額以及必要時執行的數學計算。 如果計算類型是固定金額，則按原樣使用金額欄位。 如果計算類型是按 $ 工資或承保金額，則會在數學計算式使用計算金額和計算方向。</br></br>如果計算類型是按 $ 的薪資金額，則使用的數學公式如下：</br></br>年度福利薪資除以計算金額 (向上或向下四捨五入) 乘以員工或雇主的吸煙者或非吸煙者數額。</br></br>如果計算類型是按 $ 的承保金額，則使用的數學公式如下：</br></br>承保金額除以計算金額 (向上或向下四捨五入) 乘以員工或雇主的吸煙者或非吸煙者數額。)</br></br>在這兩種計算公式中，計算方向用來判定年度福利薪資或承保金額除以計算金額後的數字是向上或向下四捨五入。 |
   | **計算金額** | 福利費率計算流程期間使用的金額。 此金額將是分層費率數學計算期間的除數。 |
   | **計算方向** | 計算結果金額應該四捨五入的方向。 系統支援三種計算方向：空白 (精確方法)、**增加** 和 **減少**。</br></br><ul><li>如果空白，系統將使用薪資/承保金額除以計算金額的精確計算法。 如果此值有分數，那麼將用在它的計算。</li><li>如果 **增加**，數學計算公式將增加薪資/承保金額除以計算金額到下一個整數，意味著 12.25 將增加到 13。</li><li>如果 **減少**，數學計算公式將減少薪資/承保金額除以計算金額到目前的整數，意味著 12.25 將減少為 12。</li></ul> |
   | **非吸煙員工金額** | 福利提供商支付不吸煙員工的金額。 這是雇主支付給福利提供者的金額，應以費率設定的付款頻率為主。 |
   | **非吸煙雇主金額** | 福利提供商支付不吸煙員工的金額。 這是雇主支付給福利提供者的金額，應以費率設定的付款頻率為主。 |
   | **吸煙員工金額** | 福利提供商支付不吸煙員工的金額。 這是雇主支付給福利提供者的金額，應以費率設定的付款頻率為主。 |
   | **吸煙雇主金額** | 福利提供商支付不吸煙員工的金額。 這是雇主支付給福利提供者的金額，應以費率設定的付款頻率為主。 |
   | **行政管理金額** | 第三方系統管理員收取的行政管理費金額。 這是雇主支付第三方行政管理人的金額，應以費率設定的付款頻率為主。 |
   | **彈性點數非吸煙者費率** | 根據非吸煙者分層等級定義的計算公式，計入福利成本的彈性點數。 例如，如果計算類型是 **按 $ 元的承保金額**，計算金額為 10,000，彈性點數非吸煙者費率為 6，意味著如果非吸煙員工選擇 $10,000 的承保金額，將花費 6 個彈性點數。 如果他們選擇 $20,000 的承保金額，它將花費 12 個彈性點數，依此類推。 |
   | **彈性點數吸煙者費率** | 根據吸煙者分層等級定義的計算公式，計入福利成本的彈性點數。 |

5. 選取 **儲存**。 



[!INCLUDE[footer-include](../includes/footer-banner.md)]