---
title: 買賣請假
description: 本主題說明如何在 Dynamics 365 Human Resources 提交買賣請假要求。
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2ddc50540ba0686f18b6e8875e40f11c378c448f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452358"
---
# <a name="buy-and-sell-leave"></a>買賣請假


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以在 Dynamics 365 Human Resources 根據貴公司設定的買賣請假政策提交買賣請假要求。  

## <a name="request-to-buy-leave"></a>購買請假要求

1. 請在 **Employee 自助服務** 工作區中選取 **下班時間餘額** 圖格中的 **購買請假要求**。 

2. 新增 **請假類型** 並輸入您希望購買請假量的 **數額**。 

3. 當您準備好提交要求時，選取 **提交**。 

您的餘額將自動更新或更新前歷經核准流程。 這取決於購買政策的配置方式。

## <a name="request-to-sell-leave"></a>銷售請假要求

1. 請在 **Employee 自助服務** 工作區中選取 **下班時間餘額** 圖格中的 **銷售請假要求**。 

2. 新增 **請假類型** 並輸入您希望銷售請假量的 **數額**。 

3. 當您準備好提交要求時，選取 **提交**。

您的餘額將自動更新或更新前歷經核准流程。 這取決於購買政策的配置方式。


## <a name="troubleshooting"></a>排除障礙 

如果購買或銷售請假要求工作流程失敗，具備 **EssLeaveBuySellRequestApprover** 權限的使用者可以審查所有請假買賣要求的訊息日誌。 為此，請前往 **請假和缺勤 > 連結 > 買賣請假要求 > 訊息日誌** (左上角)。 **訊息日誌** 顯示使用者交易的處理方式以及相關的工作流程歷史。


## <a name="see-also"></a>也請參閱

[請假和缺勤概觀](hr-leave-and-absence-overview.md)</br>
[管理買賣請假政策](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
