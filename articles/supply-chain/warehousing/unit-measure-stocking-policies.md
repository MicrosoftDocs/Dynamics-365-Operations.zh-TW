---
title: 測量單位和庫存原則
description: 本文介紹如何在倉庫流程中使用預設單位、單位序列和單位換算。
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetails, EcoResProductDetailsExtended, EcoResStorageDimensionGroup, InventItemOrderSetup, UnitOfMeasureConversion, WHSRFMenuItem, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29611
ms.assetid: 4b5ca875-9a06-416d-9ac0-cc3ab8f7338e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0de12620bca54c7e43713138d7a152c2bd6edff3453f81cf779f9b875cf77eb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446643"
---
# <a name="unit-of-measure-and-stocking-policies"></a>測量單位和庫存原則

[!include [banner](../includes/banner.md)]

本文介紹如何在倉庫流程中使用預設單位、單位序列和單位換算。

單位序列群組定義可用於倉庫工序的單位序列。 它們在 **單位序列群組** 頁面上建立。 該序列顯示各個單位的關係。 例如，您儲存包含具有品項個別部分的箱子的托盤。 在這種情況下，您必須提供三種不同的單位和階層的邏輯順序。 單位序列群組可讓您定義牌照分組原則，以及應用於各種倉庫流程的預設單位。 本文適用於可用於倉庫管理的進階倉儲解決方案，和可用於庫存管理的更基本的倉儲解決方案。

## <a name="unit-sequence-groups-for-released-products"></a>已發佈產品的單位序列群組
如果要在倉庫工作流程中使用已發佈產品，則必須為其指派單位序列群組。 如果您驗證與儲存尺寸群組關聯的產品，並且儲存尺寸群組的 **使用倉庫管理流程** 選項設定為 **是**，如果沒有為產品定義單位序列群組識別碼，則會收到錯誤訊息。 如果您使用的單位序列群組包含多行 (因此包含多個單位)，您必須設定單位之間的單位轉換。 您可以在 **單位轉換** 頁面上完成此設定。 序列群組中與已發佈產品關聯的最小單位必須與為相應產品定義的庫存單位相符。 庫存單位是用於現有庫存量的基本計算的單位。 您還可以使用 **啟用測量單位轉換** 選項設定基礎產品的產品變型測量單位轉換。

## <a name="license-plate-grouping"></a>牌照分組
您可以指定是否應將少於或多於特定單位的收貨分組到一個牌照中，或者為每個單元劃分為一個單獨的牌照。 要設定此行為，請使用 **單位序列群組** 頁面 **行詳細資料** 索引標籤上的 **牌照分組** 選項。 如果您想在使用行動裝置處理工作時使用牌照分組，則必須在 **行動裝置** 功能表項目上選擇 **牌照分組** 選項。 例如，您使用行動裝置登記與具有兩行的單位序列群組關聯的品項。 第一行用於「件」，且 **牌照分組** 選項設定為 **是**。 第二行用於「托盤單位」，且 **牌照分組** 選項設定為 **否**。 在這種情況下，系統會自動引導每 100 件牌照的拆分和建立。

## <a name="units-for-cycle-counting"></a>週期盤點單位
若要定義哪些單位應用作週期盤點流程的一部分，請在 **單位序列群組** 頁面上選擇 **週期盤點使用的單位** 上的選項。 您在序列群組中最多可選擇四個單位。 如果選擇超過四個單位，則其他單位將不會顯示在行動裝置上。

## <a name="default-units-for-mobile-device-receiving-processes"></a>行動裝置接收流程的預設單位
若要設定應用於行動裝置接收流程的預設單位，請在 **單位序列群組** 頁面上啟用 **採購和轉移的預設單位** 和 **生產的預設單位** 選項。 例如，您可以指定預設情況下，系統在使用行動裝置接收訂購單現有庫存時應使用「托盤數量」，但庫存單位應為「件」。 若要取得每個托盤包含的件數的換算，必須定義單位換算，例如 100 件 = 1 PL。

## <a name="default-order-settings"></a>預設訂單設定
作為建立已發佈產品的一部分，必須為採購、銷售和庫存選擇預設單位以處理各種訂單。 您可以使用 **預設訂單設定** 和 **站點特定的訂單設定** 頁面來設定各個來源文件的預設單位和數目。 您可以從 **已發佈產品** 頁存取這些頁面。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]