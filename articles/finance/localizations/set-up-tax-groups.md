---
title: 設定稅金群組
description: 本主題說明如何在稅款計算服務中設定稅金群組。
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 50abafb958edfb8476434ff5842cd84cb186962f
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451227"
---
# <a name="set-up-tax-groups"></a>設定稅金群組

[!include [banner](../includes/banner.md)]

本主題說明如何在稅款計算服務中設定稅金群組。 另外還說明如何設定稅金群組適用性規則矩陣和配置矩陣中的行。

「稅款計算服務」中的稅金群組概念類似於 Microsoft Dynamics 365 Finance 中的銷售稅群組概念。 它們是稅籍代碼群組。 「稅款計算服務」使用稅金群組和分項稅金群組的交集來決定稅籍代碼。

但是，「稅款計算服務」中的稅金群組因為沒有其他參數，例如 **使用稅** 與 **免稅**，所以不同於 Finance 中銷售稅金群組，。 相反地，這些參數可用於稅代碼層級。

> [!IMPORTANT]
> 「稅款計算服務」中的稅金群組設定與法律實體無關。 您只需要在 Regulatory Configuration Service (RCS) 中完成此設定一次。 當您在 Finance 中啟用稅款計算服務時，所選法律實體的稅金群組將自動同步。

## <a name="set-up-a-tax-group"></a>設定稅金群組

請按照以下步驟設定稅金群組。

1. 登入 [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/)。
2. 前往 **工作區** \> **全球化功能** \> **稅款計算**。
3. 選擇要設定的功能和版本，然後選擇 **編輯**。
4. 在 **一般** 索引標籤中，選擇 **組態版本**。
5. 在 **稅金群組** 索引標籤，選擇 **管理欄**。 如果您是第一次設定稅金群組，則系統會自動設定 **管理欄** 對話方塊中的欄位。
6. 在左側清單中，展開 **明細行** 節點，然後選取 **稅金群組** 核取方塊。

    ![在「管理欄」對話方塊的「明細行節點」下方選取的稅金群組。](media/select-tax-group.png)

7. 選擇向右箭頭按鈕將 **稅金群組** 加到右側的 **所選欄** 清單。

    ![新增至所選欄清單的稅金群組。](media/add-tax-group.png)

8. 選取 **確定**。

## <a name="configure-a-tax-group"></a>設定稅金群組

設定稅金群組後，將建立稅金群組適用性規則矩陣。 可以將明細新增至矩陣，以設定稅金群組。

1. 在 **稅金群組** 索引標籤上選取 **新增**。
2. 在 **稅金群組** 欄位中，輸入稅金群組的名稱。

    > [!IMPORTANT]
    > 我們建議您將稅金群組的名稱限制在 10 個字符內。 此名稱會與 Finance 同步，Finance 對銷售稅金群組的名稱限制為 10 個字元。

3. 在 **稅代碼** 欄位中，選取每個要包括在稅金群組的稅代碼核取方塊。 您可以在一個稅金群組中包含多個稅代碼。

    ![在稅籍代碼欄位中選擇多個稅籍代碼。](media/multiple-tax-codes-selection.png)

4. 重複步驟 1 到 3，以新增更多稅金群組。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
