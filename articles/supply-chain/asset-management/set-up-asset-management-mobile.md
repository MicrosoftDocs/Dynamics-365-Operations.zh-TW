---
title: 設定資產管理行動工作區
description: 本主題介紹如何設定 Microsoft Dynamics 365 Supply Chain Management 和財務與營運 (Dynamics 365) 行動應用程式來執行 [資產管理行] 動工作區，工作人員可以使用該工作區來執行資產管理任務。
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5d628f99d4fc6788ddb38590c65decb871d49f93
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448494"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>設定資產管理行動工作區

[!include [banner](../includes/banner.md)]

本主題介紹如何設定 Microsoft Dynamics 365 Supply Chain Management 和財務與營運 (Dynamics 365) 行動應用程式來執行 **資產管理** 行動工作區，工作人員可以使用該工作區來執行資產管理任務。

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>在 Supply Chain Management 中設定維護工作人員使用者

對於需要存取 **資產管理** 行動工作區的各個使用者，請按照以下步驟操作。

1. 在 Supply Chain Management 中，移至 **人力資源 \> 工作人員**，並確保要設定的使用者存在工作人員記錄。 根據需要建立新的工作人員記錄。
1. 去 **資產管理\>設定\>工作人員\>工作人員**，並確保您在上一步中識別（或建立）的工作人員記錄映射到維護工作人員記錄。 根據需要建立新的維修工作人員記錄，並將 **工作人員** 欄位設定為上一步中的工作人員記錄。
1. 去 **資產管理\>設置\>工作人員\>維護工作人員群組**，並確保您在上一步中確定 (或建立) 的維護工人記錄屬於該維護工作人員群組。
1. 移至 **系統管理 \> 使用者**。
1. 在格線中選擇相關使用者。
1. 在 **使用者詳細資料** FastTab 上，將 **人員** 欄位設定為要與目前使用者帳戶關聯的工作人員帳戶。 此工作人員帳戶應該是您在步驟 1 中確定 (或建立)，並在步驟 2 中對應維護工作人員記錄的工作人員記錄。

> [!NOTE]
> 使用者權限和資訊安全角色適用於 **資產管理** 行動工作區，就像它們套用至 Supply Chain Management 使用者介面的功能一樣。 因此，您設定為存取 **資產管理** 行動工作區的每個使用者，必須具有直接在 Supply Chain Management 中執行類似作業所需的資訊安全角色。

## <a name="publish-the-asset-management-mobile-workspace"></a>發佈資產管理行動工作區

若要在財務與營運 (Dynamics 365) 行動應用程式中提供資產管理功能，您必須發佈 **資產管理** 行動工作區。

1. 在 Supply Chain Management 中，選擇 **設定** 按鈕 (右上角的齒輪符號)，然後在功能表上選擇 **行動應用程式**。
1. 在 **管理移動應用程式** 對話方塊，找到 **資產管理** 圖標。 如果它包含文字「在中繼資料中 - 未發佈」，則工作區尚未發佈。 如果它包含文字「在中繼資料中 - 未發佈」，則工作區已發佈，您可以跳過此程序的其餘部分。

    ![管理移動應用程式對話方塊。](media/mobile-workspaces.png "管理行動應用程式對話方塊")

1. 選擇 **資產管理** 圖標，然後在工具列上選擇 **發佈**。 幾秒鐘後，您應該會收到一則通知，說明工作區已成功發佈。 此外，圖標上的文字應變更為「在中繼資料中 - 未發佈」。

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>安裝和設定財務與營運 (Dynamics 365) 移動應用程式

1. 移至以下應用商店之一，在行動裝置上安裝 **Microsoft 財務與營運 (Dynamics 365)** 應用程式：

    - [如果是 Google Android 裝置](https://go.microsoft.com/fwlink/?linkid=850662)
    - [如果是 Apple iOS 裝置](https://go.microsoft.com/fwlink/?linkid=850663)

1. 打開財務與營運 (Dynamics 365) 應用程式。 登入頁面應隨即顯示。 在 **登入** 欄位中，輸入 Supply Chain Management URL，或在 **最近使用的環境** 清單中選取最近使用的 RUL，然後點選 **連線**。

    ![登入頁面。](media/mobile-app-sign-in.png "登入頁面")

1. 如果系統提示您確認連線，請選擇 **我知道** 核取方塊，然後點選 **連線**。
1. 在 **選擇帳戶** 頁面，使用您的 Microsoft 帳戶登入行動應用程式。

    **工作區** 頁面隨即顯示。 其中將列出您的 Supply Chain Management 執行個體已發佈的每個行動工作區。

    ![工作區清單。](media/mobile-app-workspaces.png "工作區清單")

1. 如果您必須變更法人實體 (公司)，請點選左上角的選單鍵 (有時稱為漢堡或漢堡按鈕)，然後點選 **變更公司**。

    ![變更法律實體。](media/mobile-app-change-comp.png "變更法律實體")

1. 在 **工作區** 頁面，選擇要使用的工作區以將其打開。

    ![資產管理行動工作區。](media/mobile-app-asset-workspace.png "資產管理行動工作區")

## <a name="work-with-the-asset-management-mobile-workspace"></a>使用資產管理行動工作區

有關如何使用 **資產管理** 行動工作區，請參閱[使用資產管理行動工作區](asset-management-mobile-workspace.md)。

有關財務與營運 (Dynamics 365) 行動應用程式的更多資訊，請參閱[行動應用程式首頁](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]