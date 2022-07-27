---
title: 行動裝置使用者設定
description: 本主題說明如何管理倉庫工作人員的行動裝置使用者設定。
author: Mirzaab
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppDeviceBrand,WHSMobileAppUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 4ea0fcfa7a165587567968f95549799859edaa60
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450024"
---
# <a name="mobile-device-user-settings"></a>行動裝置使用者設定

[!include [banner](../../includes/banner.md)]

全新的 Warehouse Management 行動裝置應用程式，具有一組特定應用程式的設定，有助於自訂使用者體驗。 由於該應用程式可用於不同螢幕尺寸和配置的裝置 (例如：平板電腦、手機或手持裝置)，因此，從 Microsoft Dynamics 365 Supply Chain Management 集中管理設定將非常實用。

*行動裝置使用者設定* 功能，可讓您自訂所有裝置上使用的全球使用者設定。 您還可以為各個裝置品牌、型號和/或工作人員自訂更精細的使用者設定。 當工作人員登錄 Warehouse Management 行動應用程式時，該應用程式會獲取並套用儲存在 Supply Chain Management 中的具體設定檔，使用配對的品牌、裝置和/或使用者 ID。

此功能可以幫助工作人員在開始使用新裝置時能夠更快上手。 這裡有些範例：

- 管理員可以建立一組標準的偏好選項，這些偏好選項最適合特定製造商的裝置和/或特定型號。 因此，工作人員無需變更設定即可開始使用新裝置。
- 如果您的公司有一組在工作人員之間共用的裝置，則工作人員每次登入時，都會看到他們偏好的設定選項，即使他們在當日以前，從未使用過該特定的實體裝置。
- 在 Supply Chain Management 中，管理員可以檢視和編輯所有儲存的設定，甚至可以針對個別工作人員。 此功能可以幫助他們疑難排解或微調新功能。

> [!IMPORTANT]
> *行動裝置使用者設定* 功能僅適用於新版的 Warehouse Management 行動裝置應用程式。 它不適用於舊版的倉庫應用程式。

## <a name="turn-the-mobile-device-user-settings-feature-on-or-off"></a>開啟或關閉行動裝置使用者設定功能

若要使用此主題中描述的功能，您的系統必須開啟 *新版倉庫應用程式的使用者設定、圖示和步驟標題*。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以前往 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區並搜尋 *新版倉庫應用程式的使用者設定、圖示和步驟標題* 功能，然後開啟或關閉此功能。

## <a name="create-and-manage-user-settings"></a>建立和管理使用者設定

使用 **行動裝置使用者設定** 頁面以建立、檢視和管理所有細微性的設定檔。 工作人員首次在新裝置上編輯使用者設定時，如果新的設定檔尚不存在，則會在此頁面上自動新增該設定檔。 然後，每次工作人員進行變更時都會更新該設定檔。

您還可以定義一個適用於所有裝置品牌、型號和/或工作人員的設定檔。 然後，您可以通過為各個品牌、型號和/或工作人員應用更具體的設定來增加細微性。

按照以下步驟為您的行動裝置建立和管理使用者設定。

1. 前往 **倉庫管理 \> 設定 \> 行動裝置 \> 行動裝置使用者設定**。
1. 在清單窗格中選取現有使用者設定檔以開啟其記錄。 或者，選擇動作窗格上的 **新增**，以建立另一個新的設定檔。

    清單窗格中的每個設定檔都帶有標籤，以指示設定檔適用的品牌、型號和/或使用者 ID。 更一般的設定檔的值為 *全部*，針對部分或全部特徵。

1. 在新的或選定的設定檔的標題部分中，設定下列欄位：

    - **裝置品牌名稱** – 選擇設定檔適用的裝置品牌名稱。 如果設定檔適用於所有品牌，請將此欄位保留空白。 清單中的值包括系統中定義個所有品牌。 如需如何定義品牌清單的詳細資訊，請參閱下一節。
    - **裝置型號 ID** – 選擇設定檔適用的裝置型號。 如果設定檔適用於所選品牌的所有型號，請將此欄位保留空白。 清單的值包括 **裝置品牌名稱** 欄位中所選品牌的所有型號。 如需如何定義每個品牌型號清單的詳細資訊，請參閱下一節。
    - **使用者識別碼** – 選擇設定檔應用套用倉庫工作人員的使用者 ID。 如果設定檔適用於所有工作人員，請將此欄位保留空白。

1. 在 **一般** FastTab 上設定下列欄位：

    - **按鈕位置** – 選擇按鈕在裝置上的位置。 將移動應用程式中的元素，以更完美的適應工作人員的偏好或慣用手。 可用的選項有 *右下角 (預設)*、*左下角*、*右上方* 和 *左上方*。
    - **顯示方向** – 選擇應用程式中預設的應用程式顯示方向。
    - **用相機掃描** – 將此選項設定為 *是*，使用裝置的相機掃描，輸入模式設定偏好為輸入欄位 *掃描*。 如果您的裝置有內建的掃描器，請將此選項設定為 *否*，以改為使用掃描器。
    - **顯示產品照片** – 如果可用於已發布的產品時，選擇是否應顯示產品照片。 如需如何新增產品圖片的詳細資訊，請參閱[將圖片新增至產品](../pim/tasks/add-image-product.md)。
    - **顯示主題顏色** – 選擇裝置的顏色主題。
    - **音量等級** – 選擇裝置的音量。 選擇介於 0 (零) 和 10 之間的值。 值 *0* 表示沒有聲音，而值 *10* 代表最大音量。 預設值為 *4*。
    - **震動等級** – 選擇裝置的震動等級。 選擇介於 0 (零) 和 5 之間的值。 值 *0* 表示沒有震動，而值 *5* 代表最大震動強度。 預設值為 *1*。
    - **文字縮放百分比** – 將文本大小指定為標準大小的百分比。 輸入介於 70 到 400 之間的值。 值 *70* 表示最小的文字縮放，值 *400* 代表最大的文字縮放。 預設值為 *100*。
    - **按鈕縮放百分比** – 將按鈕大小指定為標準大小的百分比。 輸入介於 50 到 200 之間的值。 值 *50* 表示最小的按鈕縮放，值 *200* 代表最大的按鈕縮放。 預設值為 *100*。

## <a name="create-and-manage-mobile-device-brands"></a>建立和管理行動裝置品牌

使用 **行動裝置品牌** 頁面以檢視、建立和管理可與您的設定檔一起使用的裝置品牌和型號。 當工作人員首次在使用設備上編輯其設定時，行動裝置應用程式會自動取得並提交本機品牌名稱和型號 ID。 因此，多數記錄都會自動產生。 但是，您也可以管理此頁面上的所有記錄。 例如，您可以為每個品牌和型號提供更有用的描述，以幫助區分類似或神秘的型號 ID。

按照以下步驟為建立和管理行動裝置品牌和型號。

1. 前往 **倉庫管理 \> 設定 \> 行動裝置 \> 行動裝置品牌**。
1. 在清單窗格中，選取行動裝置品牌以開啟其記錄。 或者，選擇動作窗格上的 **新增**，以建立另一個新的品牌。
1. 在新的或選定的裝置品牌的標題部分中，設定下列欄位：

    - **裝置品牌名稱** – 裝置的品牌名稱，例如：*Microsoft Corporation*。
    - **描述** – 您可以輸入描述有助於區分品牌的名稱。

1. **行動裝置型號** FastTab 顯示所選裝置品牌的所有型號。 使用工具列的按鈕將列新增到網格中，或從網格中移除列。 對於每一列，您可以設定下列欄位：

    - **裝置型號 ID** – 裝置型號 ID，例如：*Surface Book 2*。
    - **描述** – 您可以輸入描述有助於區分型號 ID 的名稱。

## <a name="additional-resources"></a>其他資源

- [安裝並連線 Warehouse Management 行動應用程式](install-configure-warehouse-management-app.md)
- [指派 Warehouse Management 行動應用程式的步驟圖示和標題](step-icons-titles.md)