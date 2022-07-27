---
title: 設定行動裝置功能表項目，以提供揀貨行概觀。
description: 本主題說明如何定義何時向在行動裝置上處理倉庫工作的倉庫員工顯示列出所有工作行的清單。 對於經常需要工單中揀貨行的概觀，以便最佳化揀貨順序的倉庫員工而言，此功能非常有用。
author: Mirzaab
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7d3a8972c5d2f4c52dddef458ebd6079118cadfe
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449517"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a>設定行動裝置功能表項目，以提供揀貨行概觀。

[!include [banner](../includes/banner.md)]

本主題說明如何為用於處理揀貨工作的行動裝置功能表項目設定與揀貨行概觀相關的選項。 揀貨行概觀可讓倉庫員工檢視與其目前工作相關的所有工作行清單，並從清單中進行選擇。 這種功能可以幫助員工最佳化他們的揀貨順序。 此功能提供可替代標準 **略過** 按鈕的選項，讓員工依固定順序以一次一行的方式循環進入行項。 (但是，使用該按鈕的選項仍然可用。)

管理員可以個別地設定每個功能表項目，以控制 Warehouse Management 行動應用程式呈現揀貨行概觀的方式、時間和位置。

## <a name="turn-on-the-work-pick-line-overview-feature"></a>開啟工作揀貨行概觀功能

使用此功能之前，您必須先在系統中開啟。 管理員可以使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定來檢查該功能的狀態，並視需要開啟該功能。 在 **功能管理** 工作區，該功能會依以下方式列出：

- **模組：**_倉庫管理_
- **功能名稱：** _工作揀貨行概觀_

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a>設定功能表項目以顯示所有工作行清單

若要設定行動裝置功能表項目，以提供揀貨行概觀，請遵循以下步驟。

1. 移至 **Warehouse Management\>設定\>行動裝置\>行動裝置功能表項目**。
1. 選擇或建立與揀貨工作相關的功能表項目，並設定以下值：

    - **模式：** *工作*
    - **使用現有工作：** *是*
    - **導向：** *使用者導向* 或 *系統導向*

    如需如何建立功能表項目及使用 **行動裝置功能表項目** 頁面上各種設定的詳細資訊，請參閱[針對倉庫工作設定行動裝置](configure-mobile-devices-warehouse.md)。

1. 在 **一般** FastTab 上設定此功能，方法是將 **顯示工作行清單** 欄位設定為以下其中一個值，：

    - **僅應要求顯示** – 員工可以透過選擇 Warehouse Management 行動應用程式中的 **跳至** 按鈕，來檢視揀貨行清單。
    - **在每次揀貨開始時顯示** – 員工每次開始或完成揀貨行時都會看到該清單。 員工還可以透過選擇 Warehouse Management 行動應用程式中的 **跳至** 按鈕，再次檢視該清單。
    - **僅在第一個揀貨開始時顯示** – 員工每次開始新的揀貨工作時都會看見此清單，但在每個行項之後則無法看見。 員工還可以透過選擇 Warehouse Management 行動應用程式中的 **跳至** 按鈕，再次檢視該清單。
    - **永不顯示** – 標準 **略過** 按鈕會出現在 Warehouse Management 行動應用程式中，且工作行清單的顯示會關閉。 **略過** 按鈕可讓員工按固定順序以一次一個的方式循環進入各行。 員工還可以根據需要多次在清單中循環，直到處理完所有行項為止。

1. 在動作窗格上，選擇 **儲存**。

    如果您將 **顯示工作行清單** 欄位設定為任何值 (*永不顯示* 除外)，則動作窗格中的 **欄位清單** 按鈕會變為可用。

1. 在動作窗格上，選擇 **欄位清單**。
1. 在 **欄位清單** 頁面上，設定 Warehouse Management 行動應用程式針對清單中的每一行顯示的資訊。

    - **主要控制** 欄位一律設定為 *LineNum*。 因此，清單中的每一列都以行號開頭。
    - 使用剩餘的 **顯示欄位** 欄位，以視需要新增最多七個額外的顯示欄位。 在每個 **顯示欄位** 欄位中，選擇工作行欄位的名稱。 之後每行將顯示該欄位的值。 這些值將按照您在此處選擇的順序顯示。 如果這七個值不是全部都需要，您可以將一些 **顯示欄位** 保留空白。

1. 在動作窗格上，選擇 **儲存**，然後關閉 **欄位清單** 頁面。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]