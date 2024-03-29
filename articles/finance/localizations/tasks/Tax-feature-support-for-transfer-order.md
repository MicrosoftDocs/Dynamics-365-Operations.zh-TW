---
title: 轉移訂單的稅務功能支援
description: 本主題介紹使用稅務計算服務對轉移訂單的新稅務功能支援。
author: Kai-Cloud
ms.date: 10/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f68a3d7ed4384fe5a97f1e59903e3191df6b741
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2021
ms.locfileid: "8451047"
---
# <a name="tax-feature-support-for-transfer-orders"></a>轉移訂單的稅務功能支援

[!include [banner](../../includes/banner.md)]

本主題提供有關稅務計算和轉移訂單中的過帳整合的資訊。 此功能可讓您設定稅務計算並在庫存轉移的轉移訂單中過帳。 根據歐盟 (EU) 增值稅 (VAT) 法規，庫存轉移被視為歐盟境內供應和歐盟境內取得。

要設定和使用此功能，您必須完成三個主要步驟：

1. **RCS 設定：** 在 Regulatory Configuration Service 中，設定轉移訂單中稅碼確定的稅務功能、稅碼和稅碼適用性。
2. **Dynamics 365 Finance 設定：** 在財務中，啟用 **轉移訂單中的稅金** 功能，設定庫存的稅務計算服務參數，接著設定核心稅務參數。
3. **庫存設定：** 為轉移訂單交易設定庫存設定。

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>為稅務和轉移訂單交易設定 RCS

按照以下步驟設定轉移訂單中涉及的稅。 在此處顯示的示例中，轉移訂單是從荷蘭到比利時。

1. 在 **稅務功能** 頁面的 **版本** 索引標籤，選擇草稿功能版本，然後選擇 **編輯**。

2. 在 **稅務功能設定** 頁面的 **稅碼** 索引標籤，選擇 **新增** 以建立新的稅碼。 對於此示例，建立了三個稅碼：**NL-Exempt**，**BE-RC-21**，和 **BE-RC+21**。

    - 當轉移訂單從荷蘭的倉庫出貨時，則會使用荷蘭增值稅免稅代碼 (**NL-Exempt**)。
      
        建立稅碼 **NL-Exempt**。
        1. 選擇 **新增**，在 **稅碼** 欄位內輸入 **NL-豁免**。
        2. 在 **稅收成分** 欄位內選擇 **按淨額**。
        3. 選擇 **儲存**。
        4. 在 **費率** 資料表內選取 **新增**。
        5. 在 **一般** 部分，將 **免稅** 設為 **是**。
        6. 在 **免稅代碼** 欄位內輸入 **EC**。

    - 當比利時倉庫收到轉移訂單時，透過使用 **BE-RC-21** 和 **BE-RC+21** 稅碼應用反向稽徵機制。
        
        建立稅碼 **BE-RC-21**。      
        1. 選擇 **新增**，在 **稅碼** 欄位內輸入 **BE-RC-21**。
        2. 在 **稅收成分** 欄位內選擇 **按淨額**。
        3. 選擇 **儲存**。
        4. 在 **費率** 資料表內選取 **新增**。
        5. 在 **稅率** 欄位內輸入 **-21**。
        6. 在 **一般** 部分，將 **反向稽徵** 設為 **是**。
        7. 選擇 **儲存**。
        
        建立稅碼 **BE-RC+21**。
        1. 選擇 **新增**，在 **稅碼** 欄位內輸入 **BE-RC-21**。
        2. 在 **稅收成分** 欄位內選擇 **按淨額**。
        3. 選擇 **儲存**。
        4. 在 **費率** 資料表內選取 **新增**。
        5. 在 **稅率** 欄位內輸入 **21**。
        6. 選擇 **儲存**。

3. 定義稅組。
    1. 選擇 **管理列**，然後選擇行欄位 **稅組**。
    2. 選擇 **->**，然後選擇 **確定**。
    3. 選擇 **新增** 以新增稅組。
    4. 在 **稅組** 列內輸入 **AR-EU**，然後選擇 **NL-Exempt** 稅碼。
    5. 選擇 **新增** 以新增稅組。
    6. 在 **稅組** 列內輸入 **RC-VAT，** 然後選擇 **BE-RC-21** 和 **BE-RC+21** 稅碼。
4. 定義項目稅組。
    1. 選擇 **管理列**，然後選擇行欄位 **項目稅組**。
    2. 選擇 **->**，然後選擇 **確定**。
    3. 選擇 **新增** 以新增項目稅組。
    4. 在 **項目稅組** 列輸入 **FULL**。 選擇稅碼 **BE-RC-21**、**BE-RC+21**，和 **NL-Exempt**。
5. 定義稅組的適用性。

    1. 選擇 **管理列**，然後選擇應用於建立適用性資料表的列。

        > [!NOTE]
        > 請務必將 **業務程序** 和 **稅務方向** 列新增至資料表中。 這兩列對於轉移訂單中的稅務功能都是必不可少的。

    2. 新增適用性規則。 請勿將 **稅組** 欄位留白。
        
        為轉移訂單裝運新增新規則。
        1. 在 **適用性規則** 資料表內選取 **新增**。
        2. 在 **業務程序** 欄位內選擇 **庫存**，使該規則適用於轉移訂單。
        3. 在 **出貨國家/地區** 欄位內輸入 **NLD**。
        4. 在 **寄送國家/地區** 欄位內輸入 **BEL**。
        5. 在 **稅務方向** 欄位內選擇 **輸出**，使規則適用於轉移訂單裝運。
        6. 在 **稅組** 欄位內選擇 **AR-EU**。
        
        為轉移訂單接收新增另一條規則。
        
        1. 在 **適用性規則** 資料表內選取 **新增**。
        2. 在 **業務程序** 欄位內選擇 **庫存**，使該規則適用於轉移訂單。
        3. 在 **出貨國家/地區** 欄位內輸入 **NLD**。
        4. 在 **寄送國家/地區** 欄位內輸入 **BEL**。
        5. 在 **稅務方向** 欄位內選擇 **輸入**，使規則適用於轉移訂單接收。
        6. 在 **稅組** 欄位內選擇 **RC-VAT**。

6. 定義項目稅組的適用性。

    1. 選擇 **管理列**，然後選擇應用於建立適用性資料表的列。
    2. 新增適用性規則。 請勿將 **項目稅組** 欄位留白。
        
        為轉移訂單裝運及接收新增新規則。
        1. 在 **適用性規則** 頁面選取 **新增**。
        2. 在 **業務程序** 欄位內選擇 **庫存**，使該規則適用於該轉移訂單。
        3. 請在 **項目稅組** 欄位內選取 **FULL**。
7. 完成並發佈新的稅務功能版本。


## <a name="set-up-finance-for-transfer-order-transactions"></a>為轉移訂單交易設定財務

按照以下步驟為轉移訂單啟用和設定稅費。

1. 在財務中，前往 **工作區** > **功能管理**。
2. 在列表中，尋找並選擇 **轉移訂單中的稅金** 功能，然後選擇 **立即啟用** 打開它。

    > [!IMPORTANT]
    > 此 **轉移訂單中的稅金** 功能完全依賴稅務計算服務。 因此，只有在您安裝完稅務計算服務後才能開啟。

    ![轉移訂單中的稅金功能。](../media/image7.png)

3. 啟用稅務計算服務，然後選擇 **庫存** 業務程序。

    > [!IMPORTANT]
    > 您必須為 Finance 中的每個法律實體完成此步驟，您希望稅務計算服務和轉移訂單中的稅務功能可以使用。

    1. 前往 **稅務** > **設定** > **稅務設定** > **稅務計算參數**。
    2. 在 **業務程序** 欄位內選擇 **庫存**。

4. 驗證是否設定了反向稽徵機制。 前往 **總帳**\>**設定**\>**參數**，然後在 **反向稽徵** 索引標籤，驗證 **啟用反向稽徵** 選項設為 **是**。

    ![啟用反向稽徵選項。](../media/image9.png)

5. 確認相關稅碼、稅組、項目稅組和增值稅登記編號已根據稅務計算服務指南設定在財務中。
6. 設定一個臨時過渡帳戶。 僅當適用於轉移訂單的稅不適用於免稅或反向稽徵機制時，才需要執行此步驟。

    1. 前往 **稅務** > **設定** > **銷售稅** > **分類帳過帳群組**。
    2. 在 **Interim transit** 欄位，選擇一個分類帳科目。

       ![選擇一個臨時過渡帳戶。](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>為轉移訂單交易設定基本庫存

按照以下步驟設定基本庫存以啟用轉移訂單交易。

1. 為您在不同國家或地區的倉庫建立出貨地點和寄送站點，並為每個站點添加主要地址。

    1. 前往 **倉庫管理** > **設定** > **倉庫** > **站點**。
    2. 選擇 **新增** 以建立稍後將分配給倉庫的站點。
    3. 對您必須建立的所有其他站點重複步驟 2。

    > [!NOTE]
    > 您建立的其中一個站點應命名為 **Transit**。 在此過程的後續步驟中，您將會將此站點分配到轉運倉庫，以便可以在轉移訂單的“出貨”和“收貨”交易中過帳與稅務相關的庫存憑單。 轉運地點的地址與稅務計算無關。 因此，您可以將其留白。

    ![設定站點。](../media/image11.png)

2. 建立出貨倉庫、轉運倉庫和寄送倉庫。 倉庫中維護的任何地址資訊都將在稅務計算期間覆寫該站點地址。

    1. 前往 **倉庫管理** > **設定** > **倉庫** > **倉庫**。
    2. 選擇 **新增** 建立倉庫，然後將其指派至相應站點。
    3. 重複步驟 2，根據需要為每個站點建立一個倉庫。

       ![設定倉庫。](../media/image12.png)

    > [!NOTE]
    > 對於出貨倉庫，必須在 **轉運倉庫** 欄位選擇轉移訂單交易的轉運倉庫。
    >
    > ![選擇一個轉運倉庫。](../media/image13.png)

3. 確定為轉移訂單交易設定庫存過帳設定。

    1. 前往 **庫存管理** > **設定** > **過帳** > **過帳**。
    2. 在 **庫存** 索引標籤，確定都為 **庫存發貨** 和 **庫存收貨** 過帳設定分類帳科目。

        ![設定庫存發貨和庫存收貨過帳。](../media/image14.png)

    3. 確定為 **內部應付帳款** 過帳設定了分類帳科目。

        ![設定內部應付帳款過帳。](../media/image15.png)

    4. 確定為 **內部應收帳款** 過帳設定了分類帳科目。

        ![設定內部應收帳款過帳。](../media/image16.png)
        
        
  [!INCLUDE[footer-include](../../../includes/footer-banner.md)]
