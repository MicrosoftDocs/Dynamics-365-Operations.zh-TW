---
title: 初始化 Commerce Scale Unit (雲端)
description: 本主題說明如何在 Microsoft Dynamics 365 Commerce 中初始化 Commerce Scale Unit (雲端)。
author: AamirAllaq
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2018-4-30
ms.openlocfilehash: 84e70515accde161e7efa36755edec68d26be952
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2022
ms.locfileid: "8460510"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>初始化 Commerce Scale Unit (雲端)

[!include[banner](../includes/banner.md)]

本主題說明如何在 Microsoft Dynamics 365 Commerce 中初始化 Commerce Scale Unit (雲端)。

如果您使用的是具有應用程式版本 8.1.2.x 或更高版本的第 2 層沙箱或生產環境，則必須先初始化 Commerce Scale Unit (雲端)，然後才能將零售通路函數用於銷售點 (POS) 作業或用於在雲端中使用零售伺服器的電子商務作業。 初始化將部署 Commerce Scale Unit (雲端)。

> [!IMPORTANT]
> 對於在雲端中使用零售通路函數的現有客戶，為確保為您的業務提供持續和不間斷的支援，我們要求您更新零售通路以使用 Commerce Scale Unit。 未部署 Commerce Scale Unit 的新環境將不再接收雲端託管零售通路組件的品質和服務更新。 專門使用 Commerce Scale Unit (自行託管) 的客戶無需執行任何動作。 如果您需要擴充功能，請聯絡您的 Microsoft FastTrack Solution Architect。

## <a name="prerequisites"></a>先決條件

1. 部署具有 8.1.2.x 或更高版本的第 2 層沙箱或生產環境。
2. 您可以在每個環境中自行部署最多 2 個 Commerce Scale Unit。 如果每個環境需要 2 個以上的 Commerce Scale Unit，請在 Microsoft Dynamics Lifecycle Services (LCS) 中建立支援要求，然後輸入 **要求額外的 Commerce Scale Unit** 並指明環境識別碼、Commerce Scale Unit 的數量，以及所需的資料中心區域。 該請求將在五個工作日內完成。 如果每個環境不需要超過 2 個 Commerce Scale Unit，則無需建立支援請求。 
3. 您必須在 Lifecycle Services 中擁有項目所有者權限，然後才能初始化 Commerce Scale Unit。
4. 確保在您的環境中啟用了零售許可證設定金鑰。 如需相關資訊，請參閱[許可證代碼和設定金鑰報表](../sysadmin/license-codes-configuration-keys-report.md)。 您必須打開以下鍵才能使用 Commerce Scale Unit。

    - RetailBasic
    - RetaileCommerce - 如果您打算將電子商務用於 Dynamics 365 Commerce。
    - RetailGiftCard - 如果您打算使用禮品卡。
    - RetailInvent - 如果您計劃使用庫存。
    - RetailModernPos - 如果您計劃使用銷售點 (POS)。
    - RetailReplenishment - 如果您計劃使用補貨。
    - RetailScheduler
    - RetailStores - 如果您打算使用 POS。


## <a name="region-availability"></a>區域可用性
Commerce Scale Unit 可在以下區域部署。

| 全球位置 | 區域              | 可用性        |
|-----------------|---------------------|---------------------|
| AMERICAS        | 美國東部             | 正式發行 |
| AMERICAS        | 美國東部 2           | 正式發行 |
| AMERICAS        | 美國中北部    | 正式發行 |
| AMERICAS        | 美國中南部    | 正式發行 |
| AMERICAS        | 美國中部          | 正式發行 |
| AMERICAS        | 美國西部             | 正式發行 |
| AMERICAS        | 美國西部 2           | 正式發行 |
| AMERICAS        | 加拿大中部      | 有限容量    |
| AMERICAS        | 加拿大東部         | 有限容量    |
| AMERICAS        | 美國中西部     | 有限容量    |
| 亞太地區            | 澳洲東部      | 正式發行 |
| 亞太地區            | 東南亞      | 正式發行 |
| 亞太地區            | 日本東部          | 正式發行 |
| 亞太地區            | 日本西部          | 正式發行 |
| 亞太地區            | 澳洲東南部 | 有限容量    |
| 亞太地區            | 東亞           | 有限容量    |
| 亞太地區            | 印度南部         | 有限容量    |
| 亞太地區            | 印度中部       | 有限容量    |
| 歐洲、中東和非洲            | 西歐         | 正式發行 |
| 歐洲、中東和非洲            | 北歐        | 正式發行 |
| 歐洲、中東和非洲            | 英國南部            | 有限容量    |
| 歐洲、中東和非洲            | 英國西部             | 有限容量    |

有限容量區域的部署容量受到極大限制。 部署請求將根據具體情況進行評估。 如果您對在容量有限的區域進行部署有迫切的業務需求，您可以送出支援請求以新增到候補名單中。

![顯示區域可用性的地圖。](media/Commerce-Scale-Unit-Region-Availability.png "顯示區域可用性的地圖")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>初始化 Commerce Scale Unit 作為新環境部署的一部分

請確保總部可用。 這是在初始化過程中向總部註冊縮放單位所必需的。 不建議在總部維修時初始化縮放單位，因為它可能在維修過程中變得不可用。

1. 確保總部環境可用且不在[維護模式](../sysadmin/maintenance-mode.md)。
2. 在 LCS 中，在環境詳情頁面上，選取 **環境功能\>商業**。
3. 在 Commerce 設定部署頁面上，選取 **初始化**。
4. 選取要初始化的 Commerce Scale Unit 版本。
5. 選取要在其中初始化 Commerce Scale Unit 的區域。

## <a name="configure-channels-to-use-commerce-scale-unit"></a>設定通路以使用 Commerce Scale Unit

部署 Commerce Scale Unit 後，您必須確保將您的通路設定為使用資料庫。 

若要設定您的通路以使用 Commerce Scale Unit 資料庫，請執行以下步驟。

1. 在 Commerce 總部，進入 **零售和商業\>總部設定\>商務排程器\>通路資料庫**。
1. 在左窗格中，選取一個通道資料庫。
1. 在 **零售通路** FastTab，選取 **新增**，然後在下拉式清單中選取您的零售通路。
1. 選取 **新增**，然後在下拉式清單中選取您的線上頻道。 

完成後，進入 **零售和商業\>零售和商業 IT\>配送排程**，並執行作業 9999。

> [!NOTE] 
> 作業 9999 將所有新產品和客戶同步到 Commerce Scale Unit。 此過程可能需要很長時間。 如果該通路必須僅可用於電子商務站點構建器設定，則可以執行作業 1070 而不是作業 9999。

### <a name="database-refresh-and-commerce-scale-units"></a>資料庫重新整理和 Commerce Scale Unit

在開始之前，請確保您熟悉[為使用 Commerce 函數的環境重新整理資料庫後要完成的步驟](../database/database-refresh.md)。

作為資料庫重新整理的一部分，無法跨環境移動縮放單元通道資料庫記錄 (在「通道資料庫」表單中)。 這是因為記錄代表環境特定的設定。

資料庫重新整理後，您可以透過在 LCS 中重新部署縮放單元來重新產生縮放單元的通道資料庫記錄。 如果偵測到註冊遺失，則縮放單元中的任何部署或服務動作都將嘗試向總部註冊縮放單元。

您可以透過選取部署與您的縮放單元相同的版本來重新部署縮放單元，而無需更改任何組件。 這可以透過以下步驟在 LCS 中完成：

1. 在 LCS 中，在環境詳情頁面上，選取 **環境功能\>零售**。
2. 在設定部署頁面上，選取要重新部署的縮放單元。
3. 在縮放單位的作業選單上，選取 **更新**。
4. 在滑桿上，在 **選取版本** 的下拉式清單中，選取選項 **指定版本**。
5. 在 **指定版本** 下的文字方塊中，輸入為您的比例單位顯示的版本，顯示在 **目前版本** 標籤旁邊。
6. 點選 **更新** 按鈕。

您不需要選取 **更新擴充功能**，即使您之前已經套用了擴充功能，因為在更新縮放單元時會自動選取最後一個套用於縮放單元的縮放單位。

如果您有多個縮放單位，則需要對每個縮放單位執行上述動作。 如果需要，您可以並行執行這些作業。

## <a name="deploy-additional-commerce-scale-units-optional"></a>部署額外的 Commerce Scale Unit (選取性)

初始化 Commerce Scale Unit 後，如果您的許可證授權您可以自行部署第二個縮放單位。 若要部署兩個以上的縮放單元，您必須建立支援要求。 在支援要求中，說明您需要的 Commerce Scale Unit 數量、環境名稱和所需區域。 如需許可的相關資訊，請參閱[Dynamics 365 許可指南](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409)。 

對於您部署的每個附加 Commerce Scale Unit，我們建議您按照以下步驟建立單獨的通路資料庫組。

1. 在 Commerce 總部辦公室，進入 **零售和商業 > Retail Headquarters > 零售排程器設定 > 通路資料庫組**。
2. 建立新的通道資料庫組。
3. 進入 **零售和商業 > Retail Headquarters > 零售排程器設定 > 通路資料庫**，並選取與新建立的 Commerce Scale Unit 對應的通路資料庫。
4. 選取 **編輯** 並選取新的通路資料庫組。
5. 選取 **儲存**。
6. 對選定的頻道資料庫選取 **執行完整資料同步**。

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>在現有環境中初始化雲端託管 Commerce 通路組件時的其他注意事項

如果您已經在環境中使用雲端託管的 Commerce 通路組件，則 Commerce Scale Unit 的初始化將有助於減少更新這些組件時的停機。 在初始化 Commerce Scale Unit 之前需要額外的計劃。

當您在使用雲端託管的 Commerce 通路組件的環境中初始化您的第一個 Commerce Scale Unit 時，初始化過程會將與雲端託管的通路組件關聯的通路移轉到第一個縮放單元。 與儲存縮放單位關聯的通道不受影響。

移轉過程對通路是透明的。 縮放單位初始化開始後，會自動執行以下動作：

1. 將建立一個新的 Commerce Scale Unit 並將其與環境相關聯。
2. Commerce Scale Unit 將在總部註冊為可用的通路資料庫。
3. 對應到總部 **預設** 通路資料庫的所有通路都將更新以對應到新的 Commerce Scale Unit。
4. Commerce Data Exchange (CDX) 將執行全資料同步以將通道資料帶到新的縮放單位。

**Commerce Scale Unit 初始化的規劃和測試** 作為一般規則，在初始化 Commerce Scale Unit 時，您必須為商店運營以及任何使用零售伺服器或雲端銷售點的電子商務通路營運規劃一個 5 小時的停機視窗。

1. 從生產環境到沙箱 UAT 環境執行資料庫重新整理。 
2. 在沙箱 UAT 環境中初始化 Commerce Scale Unit。 
3. 請注意完成 Commerce Scale Unit 的初始化時間。 這將與此動作在您的生產環境中花費的時間相當，在此期間商店動作和電子商務動作將不可用。

在初始化 Commerce Scale Unit 之前，您必須執行以下附加步驟。

- **關閉所有 POS 班次** - 移轉後，POS 使用者將無法關閉移轉過程中處於活動狀態的任何班次。
- **驗證所有 P-作業是否已成功完成** - 建議在初始化 CSU 之前完成同步待處理交易的 P-作業。
- **登出所有 POS 裝置** - 移轉期間不支援 POS 作業。
- **在 POS 撤回並取消所有暫停的交易** - 暫停的交易不保留作為初始化的一部分。

> [!IMPORTANT]
> 作為 Commerce Scale Unit 初始化的一部分，之前暫停的交易將遺失並且無法撤回。 

以下是初始化期間發生的情況：

- 除非您打開 POS 離線功能，否則雲端託管的 Commerce 通路將不起作用。
- 啟用離線函數的 POS 裝置將減少函數。
- 任何依賴零售伺服器的電子商務用戶端都將中斷。
- 在 Commerce Scale Unit (自行託管) 上託管的頻道不會受到影響。
- 總部辦公室函數不受影響。

以下是初始化完成後發生的情況：

- 保留所有已啟用 POS 裝置的設備啟用狀態，這代表無需重新啟用裝置。
- 獨立硬體站實體將繼續運作。
- POS 通路側報表將被重設，並且不會顯示初始化之前的資料。
- 顯示日記帳作業也將被重設，並且不會顯示初始化之前的資料。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
