---
title: 自訂和使用客戶入口網站
description: 本主題說明如何在客戶入口網站新增到系統後對其進行自訂。
author: Henrikan
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 02ad0470b7886b2e9b259682a7f8c8150d656cfb
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449865"
---
# <a name="customize-and-use-the-customer-portal"></a>自訂和使用客戶入口網站

[!include [banner](../includes/banner.md)]


本主題介紹客戶入口網站立即可用的不同頁面。 其中說明頁面的作用以及如何自訂。

客戶入口網站提供了一些立即可用的網頁和動作。 以下網站地圖概述了這些網頁和動作，以及可以執行這些動作的角色。

![客戶入口網站地圖。](media/customer-portal-site-map.png "客戶入口網站地圖")

## <a name="typical-customizations"></a>典型自訂

以下主題將幫助您瞭解 Power Apps 入口網站的基本資訊，以及如何自訂入口網站：

- [使用範本](/powerapps/maker/portals/work-with-templates) – 本主題概述 Power Apps 入口網站的運作方式，以及如何對入口網站進行簡單自訂。
- [管理入口網站內容](/dynamics365/portals/manage-portal-content) – 本主題說明如何管理和自訂您在入口網站中顯示的內容。
- [編輯 CSS](/powerapps/maker/portals/edit-css) – 本主題可幫助您對入口網站的使用者介面 (UI) 進行更複雜的自訂。
- [為您的入口網站建立主題](/dynamics365/portals/create-theme) – 本主題可幫助您為入口網站建立 UI 主題。
- [輕鬆建立和公開入口網站內容](/dynamics365/portals/create-expose-portal-content) – 本主題可幫助您管理用於入口網站的基礎資料和表格。
- [設定聯絡人以在入口網站使用](/powerapps/maker/portals/configure/configure-contacts) – 本主題說明如何建立和自訂使用者角色，以及安全性和身份驗證如何在 Power Apps 入口網站運作。
- [為入口網站上的表格表單和 Web 表單設定註釋](/powerapps/maker/portals/configure-notes) – 本主題說明如何將文件和其他儲存體新增到您的入口網站。
- [入口網站的錯誤處理](/powerapps/maker/portals/admin/view-portal-error-log) – 本主題說明如何查看入口網站錯誤記錄，並將其儲存在您的 Microsoft Azure Blob 儲存體帳戶。

## <a name="customize-the-order-creation-process"></a>自訂訂單建立流程

使用者透過客戶入口網站提交訂單時，訂單會自動同步到對應的 Dynamics 365 Supply Chain Management 環境。 因為使用者是外部客戶，所以故意向他們隱藏了一些必要資訊。 提交表單時將自動填寫此資訊。

本節介紹如何設定聯絡人以避免錯誤。 其中解釋了自動設定的欄位，以及如何在必要時修改這些欄位的值。

### <a name="the-out-of-box-order-creation-process"></a>立即可用的訂單建立流程

以下是從客戶入口網站提交訂單的標準步驟。

1. 在首頁選擇 **建立訂單** 磚，開啟 **建立訂單** 精靈。
1. 在 **訂單資訊** 頁面設定以下欄位：

    - **要求收貨日期** – 指定交貨日期。
    - **交貨地址** – 輸入訂單應送達的地址。
    - **公司** – 選擇客戶公司的名稱。 此欄位會為非管理使用者自動設定。
    - **申請編號** – 輸入訂單的申請編號。 此欄位並非必填。
    - **運送到國家/地區** – 輸入商品送往的國家或地區。 此欄位會為非管理使用者自動設定。

    ![訂單資訊頁面。](media/customer-portal-order-information.png "訂單資訊頁面")

1. 選擇 **下一步**。
1. 在 **項目** 頁面，選擇 **新增項目**。

    ![項目頁面。](media/customer-portal-items.png "項目頁面")

1. 在 **項目資訊** 對話方塊中，設定以下值：

    - **產品名稱** – 尋找並選擇要新增到訂單的產品。
    - **數量** – 輸入所選產品的數量。
    - **單位** – 指定測量單位 (例如 **個**、**公斤** 或 **箱**)。
    - **估計淨額** – 該值計算為商品的估計價格 × 所選單位的數量。

    ![項目資訊對話方塊。](media/customer-portal-item-information.png "項目資訊對話方塊")

1. 選擇 **提交** 將項目新增到訂單中。
1. 重複第 4 步到第 6 步，直到您新增了所有要訂購的項目。
1. 新增項目完成後，選擇 **項目** 頁面的 **下一步**。
1. **訂單資訊** 頁面提供訂單摘要。 檢閱訂單內容和交貨詳細資料。 如果一切看起來都正確，請選擇 **提交** 以提交訂單。

    ![已完成訂單資訊頁面。](media/customer-portal-order-submit.png "已完成訂單資訊頁面")

### <a name="standard-data-setup"></a>標準資料設定

為幫助確保流暢的使用者體驗，客戶入口網站會自動填寫多個必填欄位的值。 這些值是依據提交訂單客戶的聯絡記錄資訊。

每個[聯絡人列](/powerapps/maker/portals/configure/configure-contacts)如果屬於將使用客戶入口網站提交訂單的客戶，則必須為以下必填欄位指定值。 否則會出現錯誤。

- **公司** – 訂單所屬的法律實體
- **潛在客戶** – 與訂單關聯的客戶帳戶
- **價目表** – 為客戶自訂的價目表
- **貨幣** – 價格的貨幣
- **運送到國家/地區** – 商品送往的國家或地區

銷售訂單資料表會自動設定以下欄位：

- **語言** – 訂單的語言 (預設情況下，該值取自聯絡人記錄。)
- **運送到國家/地區** – 物品運送到的國家或地區 (預設情況下，該值取自聯絡人記錄。)
- **聯絡人** – 可以聯繫以獲取有關訂單資訊的使用者 (預設情況下，該值取自聯絡人記錄。)
- **公司** – 訂單所屬的法律實體 (預設情況下，該值取自聯絡人記錄。)
- **潛在客戶** – 與訂單關聯的客戶帳戶 (預設情況下，該值取自聯絡人記錄。)
- **發票客戶** – 訂單的計費帳戶 (預設值為聯絡人記錄的潛在客戶。)
- **銷售訂單名稱** – 銷售訂單的名稱 (預設值為 **銷售訂單**。)
- **貨幣** – 價格的貨幣 (預設情況下，該值取自聯絡人記錄。)
- **價目表** – 客戶的自訂價目表 (預設值取自聯絡人記錄。)
- **交貨地址說明** – 銷售訂單的交貨地址 (預設值為 **交貨地址說明**。)

### <a name="modify-the-order-creation-process"></a>修訂訂單建立流程

如果您不更改基本訂單建立流程，您可以自由修改客戶入口網站的外觀和 UI。 如果您想更改訂單建立流程，您必須牢記以下幾點。

不要從 Microsoft Dataverse 的銷售訂單資料表中刪除以下欄，因為需要這些欄以雙重寫入方式建立銷售訂單：

- **公司** – 訂單所屬的法律實體
- **名稱** – 銷售訂單名稱
- **貨幣** – 價格的貨幣
- **價目表** – 為客戶自訂的價目表
- **運送到國家/地區** – 商品送往的國家或地區
- **潛在客戶** – 與訂單關聯的客戶帳戶
- **語言** – 訂單的語言 (一般為潛在客戶語言。)
- **交貨地址說明** – 銷售訂單的交貨地址

對於項目，以下欄為必填：

- **產品** – 要訂購的產品
- **數量** – 所選產品的數量
- **單位** – 測量單位 (例如 **個**、**公斤** 或 **箱**)
- **運送到國家/地區** – 交貨國家或地區
- **交貨地址說明** – 訂單的交貨地址

您必須確保您的客戶入口網站提交所有這些欄的值。

如果要向頁面新增欄或刪除欄，請參閱[建立或編輯快速建立表單以獲得簡化的資料輸入體驗](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms)。

如果要更改欄的預設方式以及儲存頁面時值的設定方式，請參閱 Power Apps 入口網站文件的下列資訊：

- [預填欄位](/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [儲存時設定值](/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a>自訂首頁

客戶入口網站中的所有控制項都是內建的 Power Apps 入口網站控制項。 您可以按照 Power Apps 入口網站文件之中[撰寫頁面](/powerapps/maker/portals/compose-page)的下列步驟進行自訂。

客戶入口網站範本中包含的唯一自訂控制項用於在首頁建立磚。

![首頁的磚。](media/customer-portal-home-page-tiles.png "首頁的磚")

若要修改磚，請按照以下步驟操作。

1. 開啟[入口網站管理應用程式](/powerapps/maker/portals/configure/configure-portal)。
1. 在左側的功能窗格中，選擇 **頁面範本**。

    ![入口網站管理功能窗格。](media/customer-portal-nav.png "入口網站管理功能窗格")

1. 選擇名為 **首頁** 的頁面範本。
1. 在 **網頁範本** 欄位，選擇 **首頁** 連結以開啟該頁面的原始程式碼。

    ![網頁範本欄位。](media/customer-portal-web-template.png "網頁範本欄位")

1. 您現在應該可以看到首頁的所有原始程式碼，並且可以根據需要對其進行修改。

## <a name="resources"></a>資源

如欲瞭解有關如何設定和自訂客戶入口網站的更多資訊，請參閱以下資源：

- [Power Apps 入口網站文件](/powerapps/maker/portals/overview)
- [雙重寫入文件](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [關於入口網站生命週期](/powerapps/maker/portals/admin/portal-lifecycle)
- [升級入口網站](/powerapps/maker/portals/admin/upgrade-portal)
- [遷移入口網站設定](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [解決方案生命週期管理：Dynamics 365 for Customer Engagement 應用程式](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]