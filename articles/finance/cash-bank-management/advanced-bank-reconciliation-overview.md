---
title: 進階銀行對帳概觀
description: 本文介紹進階銀行對帳流程的流程。 進階銀行對帳功能可讓您匯入可從銀行交易中自動對帳的銀行對帳單。
author: panolte
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "22104"
- intro-internal
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ebddf6c77df227f896e6f275f741ea69fb68474
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451392"
---
# <a name="advanced-bank-reconciliation-overview"></a>進階銀行對帳概觀

[!include [banner](../includes/banner.md)]

本文介紹進階銀行對帳流程的流程。 進階銀行對帳功能可讓您匯入可從銀行交易中自動對帳的銀行對帳單。

進階銀行對帳功能可讓您匯入銀行對帳單。 然後可以從銀行交易中自動對帳匯入的銀行對帳單。 以下是進階銀行對帳流程中的步驟。

1.  設定銀行對帳單匯入。
    -   透過資料實體框架匯入銀行對帳單。
    -   三種典型的銀行對帳單建立格式：ISO20022、BAI2 和 MT940。
    -   該功能可以延伸為任何格式。

2.  設定用於進階銀行對帳的編號規則，並定義銀行對帳比對規則。
    -   對帳比對規則是一組條件，用於在對帳過程中篩選銀行對帳單明細和 Microsoft Dynamics 365 Finance 銀行交易明細。 根據您的業務慣例，您可以設定多個比對規則來自動化和最佳化您的對帳流程。

3.  將銀行對帳單與 Finance 銀行交易進行對帳。
    -   執行自動比對和建立對帳日記帳。
    -   並排查看銀行對帳單和 Finance 銀行交易。
    -   如果 Finance 銀行交易出現在銀行對帳單上，但未出現在 Finance 應用程式中，則自動過帳這些銀行交易。
    -   產生對帳單。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]