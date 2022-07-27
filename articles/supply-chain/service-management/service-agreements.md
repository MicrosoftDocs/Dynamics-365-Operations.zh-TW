---
title: 制定和建立服務合約概觀
description: 服務合約可讓您定義在典型服務造訪中使用的資源，以及這些資源如何向客戶開立發票。
author: kamaybac
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 955e360a1c0d6aec51e82598737c847b190e5e1d
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449760"
---
# <a name="develop-and-establish-service-agreements-overview"></a>制定和建立服務合約概觀

[!include [banner](../includes/banner.md)]

服務合約可讓您定義在典型服務造訪中使用的資源，以及這些資源如何向客戶開立發票。

每個服務合約都會附加到一個專案，透過該專案對交易進行過帳和開立發票。 但是，您也可以直接透過專案為服務訂單交易開立發票，而無需先將服務訂單連接到服務合約。 如果服務訂單針對一次性服務造訪，並且快速處理服務交易的需求優先於維護一段時間內有關客戶的詳細服務合約資訊的需求，您可能會決定執行此操作。

## <a name="service-agreement"></a>服務合約

在每個服務合約中，您必須指定專案、服務合約識別碼和服務合約群組。 服務合約群組可用於排序和組織服務合約。

服務合約標題包含適用於所有附加合約行的設定：

-  服務合約是否暫停。 如果服務合約暫停，您將不能根據服務合約產生服務訂單。
-  服務合約的持續時間。
-  如何將服務訂單行組合成服務訂單。
-  服務合約是否為範本。

在服務合約標題中，您還可以透過輸入要附加到合約各行的特定服務工作或服務對象來設定可與服務合約一起使用的所有服務對象和服務工作。

從服務合約標題中，您還可以將服務合約行或服務範本行複製到目前的服務合約中。

您可以暫停服務合約並停止個別服務合約行。

如果您選擇服務合約上的 **暫停** 核取方塊，則不能：

-    從服務合約自動或手動建立服務訂單。

如果您選擇服務合約行上的 **暫停** 核取方塊，則不能：

-    從服務合約行自動或手動建立服務訂單。
-    將服務合約行複製到另一個服務合約或服務訂單中。


> [!NOTE]
> 如果服務合約暫停，所有附加的行都將停止，無論它們各自的狀態如何。

## <a name="service-agreement-lines"></a>服務合約行

每個服務合約行都詳細描述了建議的服務工作的內容。 這些行包含以下設定：

-  交易類型和交易類型的描述。
-  執行服務工作的員工。
-  必須根據服務合約對其執行服務的對象。
-  執行工作和登記關聯品項、支出和費用交易的頻率。
-  可以將服務訂單行分組為服務訂單的時間範圍。
-  用於將多組合約行分組成工作，並用於向服務技術人員和客戶總結要提供的服務工作。
-  行是否停止。 如果一個行已停止，您將無法為該單獨的行建立服務訂單。
-  專案設定，例如類別和行屬性。

## <a name="related-topics"></a>相關主題

[建立服務合約](create-service-agreements.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]