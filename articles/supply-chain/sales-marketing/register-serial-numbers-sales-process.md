---
title: 使用序列化品項
description: 本主題說明如何在銷售流程中登記裝箱單或發票的序號。 如果許多公司取得序號只是為了用於服務和保固用途，而無需在從收貨到發貨的庫存中維護序號，則此功能很實用。
author: Henrikan
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResTrackingDimensionGroup, InventTrackingRegisterTrans, SalesEditLines, SalesTable, InventSerial
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28931
ms.assetid: 5d39630f-607e-492b-8c1e-790ca53effa0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62e53ec57a8d5c5c922f580219e4bde5338d0707
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448443"
---
# <a name="working-with-serialized-items"></a>使用序列化品項

[!include [banner](../includes/banner.md)]

本主題說明如何在銷售流程中登記裝箱單或發票的序號。 如果許多公司取得序號只是為了用於服務和保固用途，而無需在從收貨到發貨的庫存中維護序號，則此功能很實用。

許多公司取得序號只是為了用於服務和保固用途，而無需在從收貨到發貨的庫存中維護序號。 在這些情況下，在產品銷售時可以登記裝箱單或發票的序號。 如果產品之後被退回，您可以追蹤每個發票的產品以確定是否已銷出產品，以及服務或保固合約是否有效。

您必須透過選擇 **追蹤維度群組** 頁面的 **在銷售流程中有效** 選項來啟用銷售流程的序號。 然後，在 Supply Chain Management 中將發生以下事件：
-   在 **序號** FastTab，選取 **序號控制** 選項。 如果選取此選項，則必須在裝箱單或發票上登記每個品項的序號。
-   除了 **允許空白發貨** 選項外，清除序號跟追蹤維度群組的所有選擇。 可以選取 **允許空發貨** 選項來覆寫序號控制並允許產品在沒有登記序號的情況下包裝和開立發票。

## <a name="when-do-i-register-serial-numbers-during-the-sales-process"></a>在銷售過程中何時登記序號？
可以在銷售訂單的裝箱單或在發票上登記序號。 當為附有裝箱單的已裝運序列化品項準備發票時，可以選擇裝箱單上的某些序號開立發票。 登記的序號不能超過已裝運品項的數量。 若建立一張部分發票，可以選擇數量少於登記在裝箱單上的序列化品項。 當您列印裝箱單或發票時，要包括已登記的序號。

## <a name="can-i-enter-serial-numbers-by-scanning-them-or-do-i-have-to-type-them"></a>我可以透過掃描輸入序號嗎？還是必須鍵入它們？
您可以掃描或鍵入序號。 在使用掃描器時，掃描模式確定是否要在發票或裝箱單的序號清單中加入或刪除序號。 如果想要掃描序號，例如：使用手持式條碼掃描器，則將掃描器設定為在序號後發送 Enter 或 TAB 命令。 該命令將指示資料流的結束。 否則，您必須在掃描每個序號後按鍵盤上的 Enter 或 TAB。

## <a name="if-i-enable-serial-numbers-for-the-sales-process-do-i-have-to-register-all-serial-numbers-for-all-items"></a>若啟用銷售流程的序號，是否必須登記所有品項的所有序號？
分配給產品的追蹤維度群組之設定決定是否必須為裝箱單或發票上的所有品項登記序號。 當啟用銷售流程的序號時，將自動選取 **序號控制** 選項。 然後您必須為裝箱單或發票上的每個品項登記序號，或者為無法讀取的號碼登記一個空白登記。 若不想為每個品項提供序號，在該品項所指派的追蹤維度群組上選擇 **允許空白發貨** 選項。 然後可以登記的序號少於裝運物料的數量。 若登記的序號多於裝運品項的數量，裝箱單或發票將無法過帳。

## <a name="can-i-register-serial-numbers-for-partial-invoices-and-partial-shipments"></a>可以登記部分發票或部分裝運的序號嗎？
可以為銷售訂單建立部分發票和裝箱單，只登記那些發票和裝箱單所包括的品項序號。 若想建立部分發票，並且銷售訂單具有多個裝箱單，則可以包括多個裝箱單中的序號。 但是，只能有一張不包括所有序號的裝箱單。 例如，若有三個裝箱單且每個裝箱單包含兩個序列化品項，則不能從每個裝箱單中為品項建立部分發票。

## <a name="what-do-i-do-when-a-serial-number-isnt-readable"></a>無法讀取序號時該怎麼辦？
如果無法讀取或掃描序號，可以透過按一下 **序號** 頁面的 **無法讀取** 為該品項建立一個空白明細。 如果稍後有序號可用，則可以更新發票或裝箱單。 有關詳細資訊，請參閱下一節「是否能更正或更改已登記的銷售訂單序號？」

## <a name="can-i-correct-or-change-the-serial-numbers-that-i-have-registered-for-a-sales-order"></a>是否能更正或更改已登記的銷售訂單序號？
可以，當滿足以下條件時可以更正序號：
-   **發票** – 可以更改尚未開立發票品項的序號。 然後還更新裝箱單。 但是，若透過登記負數量更改銷售訂單明細，則不能更改銷售訂單明細的序號。
-   **裝箱單** – 不能部分更正包含序列化品項的裝箱單明細。 必須沖銷該明細的全部數量。 若已取消或更正裝箱單，當為相同的序列化品項建立新裝箱單時則不必再登記已沖銷的序號。 將使用已登記的編號。

## <a name="can-i-view-the-serial-numbers-that-were-shipped-together-with-a-specific-packing-slip-or-that-were-included-on-an-invoice"></a>可以查看隨特定裝箱單裝運的序號或包含在發票中的序號嗎？
可以，您可以在裝箱單日記帳明細或發票日記帳明細執行查詢來查看包含在文件中的所有序號清單。

## <a name="can-i-view-the-serialized-items-that-i-have-on-hand"></a>可以查看現有序列化品項嗎？
不可以，您無法查看現有序列化品項，因為直到品項出售後才會為品項登記序號。

## <a name="can-i-register-serial-numbers-for-catchweight-items"></a>可以為實秤重量品項登記序號嗎？
不可以，在銷售流程中不能為實秤重量品項登記序號。 此外，如果產品設定為實秤重量品項，您無法將產品指派到設定為僅在銷售流程中使用序號的追蹤維度群組。

## <a name="can-i-register-serial-numbers-at-the-retail-pos"></a>可以在 Retail POS 登記序號嗎？

可以，當使用者銷售指派到設定為僅在銷售流程中使用序號的追蹤維度群組之物料時，銷售點 (POS) 將提示使用者輸入序號。

## <a name="what-security-roles-are-required-in-order-to-register-serial-numbers-during-the-sales-process"></a>在銷售過程中登記序號需要哪些安全角色？
此功能適用於所有可以維護銷售裝箱單和銷售發票的角色。 以下職責使工作人員可更正序號，為無法讀取或掃描的序號登記空白項目：
-   維護序號更正
-   維護無法讀取序號的登記







[!INCLUDE[footer-include](../../includes/footer-banner.md)]