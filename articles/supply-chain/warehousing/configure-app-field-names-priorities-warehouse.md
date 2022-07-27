---
title: 設定 Warehouse Management 行動裝置應用程式中的欄位
description: 本主題介紹如何定義和設定 Warehouse Management 行動裝置應用程式中的欄位名稱和優先程度。
author: Mirzaab
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8c9c1d921f68538d5b84db16b1e88e28147e6b41
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449550"
---
# <a name="configure-fields-for-the-warehouse-management-mobile-app"></a>設定 Warehouse Management 行動裝置應用程式中的欄位

[!include [banner](../includes/banner.md)]

本主題介紹如何定義和設定 Warehouse Management 行動裝置應用程式中的欄位名稱和優先程度。

> [!NOTE]
> 本主題適用在 Warehouse Management 中的功能。 不適用庫存管理中的功能。 Warehouse Management 行動裝置應用程式是用於執行倉庫任務的應用程式。 您可以定義和設定應用程式中使用的欄位名稱，以及設定欄位名稱指派的優先順序。 本主題解釋如何定義和設定這些 Warehouse Management 行動裝置應用程式欄位名稱和優先程度，以及使用方式。

## <a name="configure-warehouse-app-field-names"></a>設定倉庫應用程式欄位名稱

在行動裝置上使用倉儲時，您可以到 **倉庫應用程式欄位名稱** 頁面設定中繼資料在裝置上的顯示方式。 在新公司中，選取 **建立預設設定** 生成在倉庫行動裝置工作流程中使用的所有欄位名稱，然後指派偏好輸入模式和輸入類型。 生成所有欄位名稱後，您可以選取以下輸入選項。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>選項</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>偏好輸入模式</td>
<td>此選項定義是否應為選定欄位名稱顯示掃描欄位或手動輸入的輸入欄位。 這有助於依欄位是否使用條碼來進行區分。 <strong>注意：</strong>對於偏好輸入模式設定為<strong>掃描</strong>的欄位名稱，如果條碼無法讀取或損壞，您可以手動輸入資訊。</td>
</tr>
<tr class="even">
<td>輸入類型</td>
<td>此選項定義選定欄位名稱應使用的輸入類型。 可用的四個選項如下：
<ul>
<li><strong>選擇</strong>- 包含可供選擇的選項清單。 選定此選項的欄位名稱不可編輯。</li>
<li><strong>日期</strong>- 指定為日期的欄位名稱將顯示帶有標籤的日期格式。 這有助於倉庫工作人員查看日期的輸入格式。 選定此選項的欄位名稱不可編輯。</li>
<li><strong>字母</strong>-如果選定，在應用程式中將使用設備鍵盤手動輸入資訊。 可依使用的設備變更鍵盤體驗。</li>
<li><strong>數字</strong>- 對於僅使用數字輸入的欄位名稱，您可以選擇此選項顯示帶有輸入欄位的自訂數字鍵盤，無須鍵盤設備。</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a>設定倉庫應用程式欄位名稱優先順序

在 **倉庫應用程式欄位優先順序** 頁面，您可以將欄位名稱放入不同的優先順序群組中。 這可以決定在倉庫工作人員使用應用程式執行任務時，應該在主任務頁面上顯示哪些資訊。 如果你按一下 **建立預設設定**，將生成一組預設的優先順序群組。 可以依需要建立任意數量的優先順序群組，但任務頁面上只會顯示三個優先順序群組。 當系統將中繼資料發送到應用程序時，會根據其優先順序群組為每個字欄位指派一個相對順序群組，應用應用程式將在任務頁面上顯示中繼資料中的前三個順序群組。 其餘溢出的中繼資料將顯示在次要詳細資訊頁面上。 下表顯示了五個優先順序群的範例。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>優先順序群組</th>
<th>已指派欄位</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> 優先順序 10</td>
<td><ul>
<li>項目</li>
<li>數量</li>
<li>測量單位</li>
</ul></td>
</tr>
<tr class="even">
<td> 優先順序 20</td>
<td><ul>
<li>叢集位置</li>
<li>叢集</li>
</ul></td>
</tr>
<tr class="odd">
<td> 優先順序 30</td>
<td><ul>
<li>品項說明</li>
</ul></td>
</tr>
<tr class="even">
<td> 優先順序 40</td>
<td><ul>
<li>組態</li>
<li>色彩</li>
<li>大小</li>
<li>樣式</li>
</ul></td>
</tr>
<tr class="odd">
<td> 優先順序 50</td>
<td><ul>
<li>位置</li>
<li>牌照</li>
</ul></td>
</tr>
</tbody>
</table>

例如，在倉庫工作人員在行動裝置上執行任務時，如果在應用程式中顯示的中繼資料包含以下欄位：

-   項目
-   數量
-   測量單位
-   品項說明
-   大小和位置

根據上表中設定的倉庫應用程式欄位優先順序，任務頁面會顯示以下 3 列資訊：

-   列 1：品項、數量、測量單位
-   列 2: 品項說明
-   列 3：尺寸

其餘中繼資料，例如位置，將不會顯示在任務頁面上，而是會顯示在詳細資訊頁面上。 若要了解更多資訊並查看用戶介面範例，請參閱部落格文章[宣布財務和運營 - 倉儲](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/)。

## <a name="additional-resources"></a>其他資源

[安裝並連接 Warehouse Management 行動裝置應用程式](../warehousing/install-configure-warehouse-management-app.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]