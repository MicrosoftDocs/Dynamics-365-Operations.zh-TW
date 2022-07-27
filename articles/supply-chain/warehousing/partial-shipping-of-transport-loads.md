---
title: 運輸工具裝載的部分運送
description: 本主題說明要如何將裝載部分運送，及延後裝載的容量規劃。
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 5ea844531314b4dd2ff3fa46d8f0b57d9c47059e684d677f06f8259b264d4a90
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447339"
---
# <a name="partial-shipment-of-a-transport-load"></a>運輸工具裝載的部分運送

[!include[banner](../includes/banner.md)]

透過設定部分運送裝載，您可以處理在將所有銷售行新增到裝載之前無法確定容量的裝載。 之後當知道確切的貨板數量時，便可以完成該流程。 因此，將運輸工具從暫存庫存中實際裝載貨物出來之前，您不必決定要將哪些貨板指派給哪個運輸工具。

此功能提供一個替代方法來替代強制執行更嚴格的結構，若是強制執行，您必須先決定要將哪些貨板指派給哪一個運輸工具，才能建立揀貨工作或裝載工作。 若採用替代方法，使用者可以設定個別裝載以確認部分運送。 接著會進行這些裝載的運輸工具裝載流程。 因此，運輸規劃部門可以規劃裝載，而不必考慮個別運輸工具的容量。

裝載時，員工可以定義可裝載貨板的新運輸工具裝載。 或者，他們可以識別現有的運輸工具裝載。 此資料可以透過行動裝置來記錄。 因此，數個倉庫員工可以將相同裝載或不同裝載的庫存裝載到同一輛卡車上。 然後可以運送裝載的全部或部分。

> [!NOTE] 
> 為了將裝載中的庫存裝載到特定運輸工具裝載，並運送裝載的一部分，則必須使用工作範本中的裝載類別來產生工作。 **揀貨** 類型的普通揀貨工作無法裝載至運輸工具裝載，例如卡車。

## <a name="set-up-transport-loads-for-partial-shipment"></a>設定要部分運送的運輸工具裝載

部分運送裝載的設定流程包含以下兩個程序。

### <a name="set-the-loading-strategy"></a>設定裝載策略

您必須透過設定裝載策略來啟用部分裝載。 在建立裝載後，您可以設定裝載策略。

1. 選擇 **倉庫管理**\>**裝載**\>**所有裝載**。
2. 選擇裝載，然後按一下 **標題**。
3. 在 **裝載策略** 欄位中，選擇 **允許裝載部分運送**。

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a>建立一個功能表項目用於裝載運輸工具裝載

您必須建立一個新的功能表項目，以允許裝載運輸工具裝載。 運輸工具裝載可讓您將一個裝載或多個裝載的工作行分組。 接下來，便可以透過使用行動掃描器來運送新增至運輸工具裝載所有一切。

1. 選擇 **倉庫管理** \> **設定** \> **行動裝置** \> **行動裝置功能表項目**。
2. 選擇 **新增**，然後在 **模式** 欄位中選擇 **工作**。
3. 將 **使用現有工作** 選項設定為 **是**。
4. 在 **一般** 索引標籤上的 **導向** 欄位中，選擇 **運輸工具裝載**。
5. 若要在行動掃描器上啟用運送確認，請在 **允許的運送確認類型** 欄位中選擇 **運輸工具裝載**。

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a>確認客戶運輸工具裝載的運送

此設定可讓您確認運輸工具裝載，包括完全裝載或部分裝載要運送的裝載。

1. 選擇 **倉庫管理**\>**裝載**\>**運輸工具裝載**。
2. 在動作窗格上，在 **出貨與收貨** 索引標籤的 **確認** 群組中，選擇 **運輸工具**。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]