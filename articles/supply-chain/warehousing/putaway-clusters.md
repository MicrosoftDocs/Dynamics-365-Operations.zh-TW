---
title: 存放叢集
description: 存放叢集提供了一種方法，可以同時挑選多個牌照，然後將它們存放在不同的位置。 這對於零售企業非常有用，對於這類企業，牌照通常不是完整的庫存棧板。
author: Mirzaab
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d5aa579394a0e3bd4c27cd44c9ff98951b3bfe1c
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450018"
---
# <a name="putaway-clusters"></a>存放叢集

[!include [banner](../includes/banner.md)]

存放叢集提供了一種方法，可以同時挑選多個牌照，然後將它們存放在不同的位置。 這個流程通常稱為 *迴圈取貨*。 存放叢集對於零售企業非常有用，對於這類企業，牌照通常不是完整的庫存棧板。 

## <a name="turn-the-cluster-putaway-feature-on-or-off"></a>開啟或關閉叢集存放功能

若要使用本主題中說明的功能，必須為您的系統開啟 *叢集存放* 功能。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以前往 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 工作區並搜尋 *叢集存放* 功能，然後開啟或關閉此功能。

## <a name="setup-for-the-example-scenario"></a>設定案例範例

### <a name="cluster-profiles"></a>叢集設定檔

存放叢集設定檔視根據收貨時指派給品項的位置決定品項的去向。 如果需要不同的叢集，則應為每個行動裝置功能表項目建立一個不同的叢集存放。

1. 移至 **倉庫管理 \> 設定 \> 行動裝置 \> 叢集設定檔**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **標題** 檢視表中，設定以下值：

    - **存放叢集設定檔識別碼：** *叢集存放*
    - **存放叢集設定檔識別碼名稱：** *叢集存放*
    - **集群類型：** *存放*
    - **序號：** 接受預設值。

1. 選擇 **儲存**，使 **一般** FastTab 上的必要欄位可用。
1. 在 **一般** FastTab 上，設定以下值：

    - **叢集指派時機：** *收貨時*

        此欄位定義是否應在收到庫存時，立即指派存放叢集，或者是否應稍後進行分揀。

    - **叢集指派規則：** *手動*

        該欄位定義叢集指派是由系統自動決定還是由使用者手動決定。

    - **指令代碼：** 將此欄位保留空白。
    - **存放叢集定位：** *接收*

        以下是可供使用的值：

        - **接收** – 在接收期間立即找到位置。
        - **叢集關閉** – 叢集關閉時找到位置。
        - **使用者導向**– 從叢集中挑選牌照進行存放時，找到一個位置。 在這種情況下，建立存放工作時沒有指定位置。 在存放期間，使用者必須掃描牌照或工作識別碼以啟動存放步驟。 然後系統再次找到存放位置，並告訴使用者要將揀選數量存放在哪裡。

    - **每個使用者的存放叢集：** *否*

        此欄位定義在自動指派叢集時，每個使用者是否應該是不重複的叢集。 只有當 **叢集指派規則** 欄位設定為 *自動* 時才可以使用。

    - **單位限制：** 將此欄位留空。

        此欄位定義為使設定檔有效而必須接收的單位。 如果留空，則所有單位都有效。

    - **工作單位中斷：** *個人*

        此欄位定義是否應在叢集關閉時，將所有庫存 (通過使用叢集識別碼和牌照) 合併到一個牌照上，以及是否應將其作為單個牌照存放或單獨存放在已收到的牌照上。 當 **存放叢集定位** 欄位設定為 *接收* 時，此欄位不可用。

    - **叢集作為父系牌照持續存在：** *不*

        如果此選項設定為 *是*，當存放步驟完成時，叢集識別碼將成為父系牌照，叢集識別碼上的所有品項都會連結到該父系牌照。

1. 在 **叢集排序** FastTab，您可以定義存放排序標準。 在工具列上選取 **新增** 以新增明細，然後為其設定以下值：

    - **序號：** 接受預設值。
    - **欄位名稱：** *WMSLocationId*

        此欄位定義個個明細應用作分揀標準的欄位。

    - **分揀：** *遞增*

        此欄位定義排序應該按遞增還是遞減進行。

1. 在 **叢集工作範本** FastTab上，在工具列上選擇 **新增** 以新增一個明細，然後為其設定以下值：

    - **工單類型：** *訂購單*
    - **工作範本：** *61 直接訂購單_。*

1. 在動作窗格上，選擇 **儲存**，然後選擇 **編輯查詢**。
1. 在 **叢集存放** 對話方塊，在 **範圍** 索引標籤，選擇 **新增** 以在查詢中新增第二個明細。 然後更新查詢明細，如下表所示。

    | 表格 | 衍生資料表 | 欄位 | 準則 |
    |---|---|---|---|
    | 工作 | 工作 | 倉庫 | *61* |
    | 工作 | 工作 | 工作識別碼 | 將此欄位保留空白。 |

1. 選取 **確定** 儲存查詢並關閉對話方塊。
1. 在動作窗格中選取 **儲存** 並關閉頁面。

> [!IMPORTANT]
> **產生叢集識別碼** 設定為 *是* 時，叢集設定檔中顯示為灰色的欄位無法使用，且在使用此功能時不會被考慮。

### <a name="mobile-device-menu-items"></a>行動裝置功能表項目

此功能提供了兩個新的行動裝置功能表項目。 **接收和分揀叢集** 功能表項目用於將收到的庫存分類到存放叢集中。 **叢集存放** 功能表項目用於在指派叢集後將叢集收起。

#### <a name="receive-and-sort-cluster"></a>接收和分類叢集

建立一個新的行動裝置功能表項目，用於接收庫存並分類到叢集中。 此功能表項目將在收到庫存後建立入庫工作，這表示接收功能表項目將用於存放叢集。

> [!NOTE]
> **接收和分類叢集** 功能表項目可與以下接收功能表項目一起使用：
>
> - 訂購單明細接收
> - 訂購單品項接收
> - 負載品項接收

1. 移至 **Warehouse Management\>設定\>行動裝置\>行動裝置功能表項目**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **標題** 檢視表中，設定以下值：

    - **功能表項目名稱：** *接收和分類集群*
    - **標題：** *接收和分類叢集*
    - **模式：** *工作*
    - **使用現有工作：** *否*

1. 在 **一般** FastTab 上，設定以下值：

    - **工作建立流程：** *訂購單品項收貨*
    - **產生牌照：** *是*
    - **指派存放叢集：** *是*

        > [!NOTE]
        > **指派存放叢集** 選項僅適用於一步驟 *工作建立流程* 時接收活動。

    接受其他剩餘欄位的預設值。

1. 在動作窗格上，選擇 **儲存**。

#### <a name="cluster-putaway"></a>叢集存放

建立一個新的行動裝置功能表項目，用於在指派叢集後將其存放。

1. 移至 **Warehouse Management\>設定\>行動裝置\>行動裝置功能表項目**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **標題** 檢視表中，設定以下值：

    - **功能表品項名稱：** *叢集存放*
    - **標題：** *叢集存放*
    - **模式：** *工作*
    - **使用現有工作：** *是*

1. 在 **一般** FastTab 上，將 **導向** 欄位設定為 *叢集存放*。 接受其他剩餘欄位的預設值。
1. 在 **工作類別** FastTab 中，為這個行動裝置功能表項目設定有效的工作類別：

    - **工作類別識別碼：** *採購*
    - **工單類型：** *訂購單*

1. 在動作窗格上，選擇 **儲存**。

### <a name="mobile-device-menu"></a>行動裝置功能表

將您剛才建立的功能表項目新增至行動應用程式的入庫功能表。

1. 移至 **倉庫管理 \> 設定 \> 行動裝置 \> 行動裝置功能表項目**。
1. 在動作窗格上，選擇 **編輯**。
1. 在功能表清單中，選取 **入庫**。
1. 在 **可用的功能表和功能表項目** 清單中，尋找並選擇 **接收和分類叢集**。
1. 選擇向右箭頭按鈕以將所選的功能表項目移到 **功能表結構** 清單。
1. 使用向上箭頭或向下箭頭按鈕將功能表項目移至行動裝置結構上所需的位置。
1. 在動作窗格上，選擇 **儲存**。
1. 重複步驟 4 到 7 以新增剩餘的功能表項目：

    - 指派叢集
    - 叢集存放

## <a name="example-scenario"></a>範例案例

此案例模擬入庫叢集處理。

### <a name="create-a-purchase-order"></a>建立採購訂單

1. 請前往 **應付帳款 \>採購單\> 所有採購單**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **建立採購訂單** 對話方塊中，設定以下值：

    - **廠商帳戶：** *1001*
    - **倉庫：** *61*

1. 選取 **確定**。

    隨即顯示 **所有訂購單** 頁面。

1. 在 **所有訂購單** 頁面上，在 **訂購單明細** FastTab，使用 **新增明細** 按鈕來新增以下明細：

    - 訂購單明細 1：

        - **品項編號：** *A0001*
        - **數量：** *10*

    - 訂購單明細 2：

        - **品項編號：** *A0002*
        - **數量：** *20*

    - 訂購單明細 3：

        - **品項編號：** *M9215*
        - **數量：** *30*

1. 在動作窗格上，選擇 **儲存**。
1. 記下訂購單編號。

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a>接收庫存並將其遠離行動裝置存放

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a>接收庫存並將其分類到叢集中

1. 以為倉庫 *61* 設定的使用者身份登入 Warehouse Management 行動裝置應用程式。
1. 在主功能表中，選擇 **入庫**。
1. 在 **入庫** 功能表，選取 **接收和分類叢集**。
1. 在 **Ponum** 欄位中，輸入您的訂購單編號。
1. 選擇 **確定** (複選標記按鈕)。
1. 選擇 **品項** 欄位，輸入品項編號 *A0001*，然後選擇 **確定**。
1. 選擇 **數量** 欄位，使用數字鍵盤輸入 *10*，然後選擇確定(複選標記按鈕)。
1. 在 **數量** 工作頁面，選擇 **確定** (核取符號按鈕) 以確認您輸入的數量。
1. 在 **品項** 工作頁面，選擇 **確定** 以確認已輸入品項 *A0001*。
1. 選擇 **叢集識別碼** 欄位，然後輸入一個值來為正在建立的叢集指派一個識別碼。

    您在此處輸入的識別碼會在收到訂購單上剩餘的兩個項目時使用。

1. 選取 **確定**。

    **Ponum** 工作頁面出現並顯示「工作已完成」訊息。

    品項 *A0001* 現在已獲接收到 *RECV* 位置並指派給您在步驟 10 中輸入的叢集識別碼。

1. 重複步驟 4 到 11，以從訂購單中接收剩餘的兩個品項並將它們指派給叢集識別碼：

    - 品項 *A0002* 的數量 *20*
    - 品項 *M9215* 的數量 *30*

#### <a name="close-the-cluster"></a>關閉叢集

在可以存放叢集中的品項之前，必須關閉叢集。

1. 在 Supply Chain Management 中，移至 **倉庫管理 \> 工作 \> 出庫 \> 工作叢集**。
1. 在 **工作叢集** 頁面，在 **工作叢集** 區段，在 **叢集識別碼** 欄位中搜尋您之前輸入的叢集識別碼。
1. 如果未顯示叢集，該叢集可能已經關閉。 若要確定叢集是否已關閉，請選擇 **顯示已關閉的工作** 核取方塊，然後搜尋您之前輸入的叢集識別碼。 然後請執行以下其中一個步驟：

    - 如果叢集已關閉，請掠過此流程的其餘步驟，並繼續執行下一個流程，[存放叢集](#put-the-cluster-away)。
    - 如果叢集群尚未關閉，請按照此流程的其餘步驟手動關閉叢集。 然後繼續下一個程序。

1. 在 **工作叢集** 區段，選擇您之前輸入的叢集識別碼。
1. 在動作窗格上，選擇 **關閉叢集**。

    叢集關閉後，不會顯示在 **工作叢集** 區段 (除非勾選 **顯示已關閉的工作** 核取方塊)。

#### <a name="put-the-cluster-away"></a>存放叢集

1. 以為倉庫 *61* 設定的使用者身份登入 Warehouse Management 行動裝置應用程式。
1. 在主功能表中，選擇 **入庫**。
1. 在 **入庫** 功能表中，選擇 **叢集存放**。
1. 選擇 **叢集識別碼**，然後輸入您之前為已關閉叢集輸入的叢集識別碼。
1. 選取 **確定**。

    **叢集存放：揀選** 頁面出現。 該頁面顯示叢集識別碼、揀貨位置、品項 (顯示價值 *多個*)，以及從集中必須揀選的總數量。

1. 選取 **確定**。

    **叢集存放：存放** 頁面出現。 **存放** 指令識別叢集識別碼、存放位置、品項、總數量和叢集上已接收品項的牌照識別碼。

    您有標準選項來覆寫或通過此步驟。

    ![叢集存放：存放頁面。](media/Cluster_putaway-Put.png "叢集存放：存放頁面")

1. 選取 **確定** 以確認叢集存放。

    系統會顯示「叢集工作完成」的訊息。

## <a name="notes-and-tips"></a>附註和提示

對於叢集識別碼成為巢狀棧板的父系牌照的情況，在掃描叢集識別碼時會自動提供存放位置。 即使牌照產生設定為手動，也無需掃描進一步的牌照。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]