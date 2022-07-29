---
title: 固定資產折舊
description: 本主題概述固定資產的折舊。
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2442830766ef1dccc109db5569bfbbbc8182f027
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451287"
---
# <a name="fixed-asset-depreciation"></a>固定資產折舊

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題概述固定資產的折舊。

折舊是定期交易，典型作法是降低資產負債表上的固定資產價值，並以支出計入損益表。 因此，典型作法是使用主帳在資產負債表上記入定期折舊。 抵銷科目是會計科目表損益部分的科目。

從版本 10.0.24 開始，**帳冊** 頁的 **計算正折舊** 資產帳冊組態選項會啟用折舊借記以負帳面價值 (貸方) 取得的固定資產。

## <a name="depreciation-adjustment"></a>折舊調整
通常只有已過帳折舊交易的更正才會以折舊調整項過帳。 因此，主科目和抵銷科目的設定與折舊科目一樣。 折舊調整值可正可負，但主帳 (作為資產負債表科目) 和抵銷科目 (通常作為損益科目) 的功能保持不變。

## <a name="extraordinary-depreciation"></a>特別折舊
特別折舊類似基本折舊。 因此，主帳通常會用來將折舊金額記入資產負債表並減少固定資產價值。 抵銷科目是損益賬戶，其中針對財政期間計算的折舊以支出計入。 

特別折舊與基本折舊的作法會區隔開來。 您可以藉由將特別折舊當作另外區分的交易類型，然後讓特別折舊與基本折舊分開過帳和編列報表。

## <a name="special-depreciation-allowance"></a>特別折舊寬減額
在資產投入使用和折舊的第一年，您可以使用特別折舊寬減額得出額外折舊金額。 計算任何其他折舊之前必須考慮特別折舊寬減額。 因為特別折舊寬減額往往到了固定資產使用壽命後期才會知道，因此搭配不會過帳到總賬的帳冊使用此類型的折舊。 您可以使用刪除未過帳到總帳定期的交易功能刪除這些帳冊的交易歷史。 接著您可以刪除固定資產帳冊的折舊歷史、過帳已知的特別折舊寬減額，然後過帳當年剩餘的折舊交易。 

您可以不限次數地建立特別折舊寬減額記錄。 在您將那些記錄指派到資產組帳冊後，它們會套用在資產帳冊。 

特別折舊寬減額會以百分比格式或固定金額輸入。 當您過帳提議的折舊值時，特別折舊寬減額交易會與折舊交易分開過帳到帳冊。

## <a name="depreciation-calendars"></a>折舊行事曆
每本帳冊都有您在折舊固定資產時使用的行事曆。 預設情況下，如果您未在帳冊指明行事曆，帳冊會使用總帳財政年度行事曆。 當帳冊關聯的折舊配置檔使用財政折舊年度時，您必須為帳冊選取財政年度行事曆。 

您可以使用總帳中的 **財政年度行事曆** 頁共享行事曆。

有關詳細資訊，請參閱[折舊方法和慣例](depreciation-methods-conventions.md)。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
