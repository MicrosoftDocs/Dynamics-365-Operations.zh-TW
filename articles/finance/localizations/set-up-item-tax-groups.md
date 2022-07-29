---
title: 設定分項稅金群組
description: 本主題說明如何在稅款計算服務中設定分項稅金群組。
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
ms.openlocfilehash: 88dd8e2fd9d4d4e5172dcc7b1bd27a70a2f59f03
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451221"
---
# <a name="set-up-item-tax-groups"></a>設定分項稅金群組

[!include [banner](../includes/banner.md)]

本主題說明如何在稅款計算服務中設定分項稅金群組。 另外還說明如何設定分項稅金群組適用性規則矩陣和配置矩陣中的行。

「稅款計算服務」中的分項稅金群組概念類似於 Microsoft Dynamics 365 Finance 中的品項銷售稅群組概念。 它們是稅籍代碼群組。 「稅款計算服務」使用稅金群組和分項稅金群組的交集來決定稅籍代碼。

> [!IMPORTANT]
> 「稅款計算服務」中的分項稅金群組設定與法律實體無關。 您只需要在 Regulatory Configuration Service (RCS) 中完成此設定一次。 當您在 Finance 中啟用稅款計算服務時，所選法律實體的分項稅金群組將自動同步。

## <a name="set-up-an-item-tax-group"></a>設定分項稅金群組 

請按照下列步驟設定分項稅金群組。

1. 登入 [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/)。
2. 前往 **工作區** \> **全球化功能** \> **稅款計算**。
3. 選擇要設定的功能和版本，然後選擇 **編輯**。
4. 在 **一般** 索引標籤中，選擇 **組態版本**。
5. 在 **分項稅金群組** 索引標籤，選擇 **管理列**。 如果您是第一次設定分項稅金群組，**管理列** 對話方塊中的欄位會自動設定。
6. 在左側清單中，展開 **明細** 節點，然後選取 **分項稅金群組** 核取方塊。

    ![在「管理列」對話方塊的「明細」節點中已選的分項稅金群組。](media/select-item-tax-group.png)

7. 選擇向右箭頭按鈕將 **分項稅金群組** 加到右側的 **所選列** 清單。

    ![分項稅金群組加入所選列清單。](media/add-item-tax-group.png)

8. 選取 **確定**。

## <a name="configure-an-item-tax-group"></a>設定分項稅金群組

設定分項稅金群組後，將建立適用性規則矩陣。 可以將明細新增至矩陣，以設定分項稅金群組。

1. 在 **分項稅金群組** 索引標籤，選擇 **新增**。
2. 在 **分項稅金群組** 欄位中，輸入分項稅金群組的名稱。

    > [!IMPORTANT]
    > 我們建議您將分項稅金群組的名稱限制在 10 個字元內。 此名稱會與 Finance 同步，Finance 對品項銷售稅群組的名稱限制為 10 個字元。

3. 在 **稅籍代碼** 欄位中，選取每個要包括在分項稅金群組的稅籍代碼核取方塊。 您可以在一個分項稅金群組中包含多個稅籍代碼。

    ![在稅籍代碼欄位中選擇多個稅籍代碼。](media/multiple-tax-codes-selection.png)

4. 重複步驟 1 到 3 以加入更多分項稅金群組。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
