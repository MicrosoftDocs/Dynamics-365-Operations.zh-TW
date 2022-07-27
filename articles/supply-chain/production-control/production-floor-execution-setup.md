---
title: 設定裝置以執行生產現場執行介面
description: 為生產現場的每項裝置設定生產現場執行介面。 公司通常會根據裝置服務的目的，以不同的方式設定每項裝置。 例如，一家公司可能在接待區有一個裝置，工人在這裡打卡上班和打卡下班，而另一個裝置在工廠，工人在那裡管理他們的工作。
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution, HcmWorker, JmgProductionFloorExecutionDeviceConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f0be79b54a279893f93d41981342e42c8880f059
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "8449412"
---
# <a name="set-up-a-device-to-run-the-production-floor-execution-interface"></a>設定裝置以執行生產現場執行介面

[!include [banner](../includes/banner.md)]

為生產現場的每項裝置設定生產現場執行介面。 公司通常會根據裝置服務的目的，以不同的方式設定每項裝置。 例如，一家公司可能在接待區有一個裝置，工人在這裡打卡上班和打卡下班，而另一個裝置在工廠，工人在那裡管理他們的工作。

## <a name="set-the-configuration-and-filters-for-a-specific-device"></a>為特定裝置設置設定和篩選器

要為裝置設置設定和作業篩選器，請使用具有資訊安全角色的帳戶登錄 **生產現場執行** 頁面，該資訊安全角色包括 *維護時間監督* 職責。 （在開箱即用的資訊安全角色中，只有 *工廠主管* 有這個職責。）然後按照這些步驟。

1. 前往您要設定的裝置，然後作為工廠主管登錄 Microsoft Dynamics 365 Supply Chain Management。 （使用包含 *維護時間監督* 職責的帳戶。）
1. 確保設定可用於您正在設定的裝置。 如果尚不存在設定，則提供預設設定。 有關如何設置設定的更多資訊，請參閱 [設定生產現場執行介面](production-floor-execution-configure.md)。
1. 前往 **產品控制 \> 製造執行 \> 生產現場執行**。

    如果當前裝置上已經至少設定過一次生產現場執行介面，則會出現登入頁面。 否則，將出現歡迎頁面。

1. 在登入頁面或歡迎頁面上，選擇 **設定**。
1. 在清單中選取設定。
1. 選取 **下一步**。
1. 選擇一個或多個篩選器以應用於當前裝置。 這些篩選器將有助於確保在該裝置上僅顯示相關作業。 要設定篩選器，請選擇篩選器類型以打開值清單，然後選擇要篩選的值。 可以使用以下篩選器：

    - **生產單位** –此篩選器是最高層級的篩選器。 它通常是指具有多個資源群組和個別資源的大型工作區。
    - **資源群組** –此篩選器是中級篩選器。 它通常是指工作區有限區域中相關資源的集合。 如果您先選擇一個 **生產單位** 篩選器，則資源群組清單僅顯示來自該單元的群組。 否則，它會顯示所有可用的資源群組。
    - **資源** –此篩選器是最具體的篩選器。 它通常是指特定的機器或其他單一資源。 如果您先選擇一個 **資源群組** 和/或 **生產單位** 篩選器，則資源清單僅顯示來自該群組和/或單位的資源。 否則，它會顯示所有可用的資源。

1. 選取 **確定**。
1. 登入頁面出現，您的裝置準備好可供使用。

## <a name="allow-a-worker-to-override-the-default-filters"></a>允許工作人員覆寫預設篩選器

您可以授予特定工作人員在他們使用的任何裝置上更改篩選器設定的權限。 對於擁有此權限的工人，生產現場執行介面提供了一個位在 **所有作業** 和 **使用中工作** 頁面上的 **篩選** 按鈕。

> [!NOTE]
> 如果工作人員更改了篩選器，則新篩選器從那時起便適用於所有登入到該裝置的使用者。

要允許工作人員覆寫已為裝置設定的預設作業篩選器，請依照以下步驟操作。

1. 前往 **時間及出勤 \> 設定 \> 時間登記員工**。
1. 在清單中選擇一個工作人員以打開該工作人員的 **時間登記員工** 頁面。
1. 在 **時間登記** 索引標籤上，將 **設定篩選器** 選項設為 *是*。

## <a name="run-the-interface-in-full-screen-mode"></a>以全螢幕模式執行介面

通常，您將在專門用於該目的的裝置上執行生產現場執行介面。 因此，以全螢幕模式執行介面而不顯示任何導覽和/或 chrome 瀏覽器或許是有意義的。

- 要隱藏 Supply Chain Management 中顯示的瀏覽窗格，請將以下文字新增到瀏覽器網址列中 URL 的結尾：`\&limitednav=true`。
- 要同時隱藏瀏覽器的網址列，請使用瀏覽器的本機全螢幕模式。 （如需說明，請參閱您的瀏覽器的文件。）

下圖的上半部分顯示了依預設的介面外觀。 下半部分顯示了隱藏瀏覽窗格時，它在全螢幕模式下的外觀。

![標準與全螢幕介面。](media/pfei-full-screen.png "標準與全螢幕介面")

## <a name="extend-the-session-past-12-hours"></a>延長工作階段超過 12 小時

依預設，若 12 小時無人使用該生產現場執行介面，它就會自動登出。 那麼，Supply Chain Management 使用者就必須重新登入。 但是，您可以將逾時限制延長至最多 90 天。

要延長逾時限制，請登入 Supply Chain Management，然後前往 **系統管理 \>使用者 \>工作階段擴展**。 指定用於登入裝置的 Supply Chain Management 使用者帳戶，以及工作階段應保持活動狀態的小時數。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
