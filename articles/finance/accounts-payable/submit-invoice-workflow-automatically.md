---
title: 向工作流程系統提交發票並比對產品收據行
description: 本主題說明將匯入的廠商發票提交到工作流程系統，並將已過帳的產品收據行與廠商發票自動進行比對的程序。
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0962ea2bfa28deb3e86620c364feffd209cfc38e
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451557"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines"></a>向工作流程系統提交發票並比對產品收據行

[!include [banner](../includes/banner.md)]

本主題說明將匯入的廠商發票提交到工作流程系統，並將已過帳的產品收據行與廠商發票自動進行比對的程序。

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>將匯入的廠商發票提交至工作流程系統，並將已過帳的產品收據行與待處理的廠商發票行比對。

作為非接觸式應付帳款開立發票程序的一部分，匯入的發票可以自動提交到工作流程系統。 您可以在 **應付帳款參數** 頁面的 **廠商發票自動化** 的索引標籤設定將匯入的發票提交到工作流程系統的程序 (**應付帳款\>設定\>應付帳款參數**)。 該提交至工作流程的程序將以您指定的頻率 (每小時或每天) 在背景執行。

當您自動向工作流程系統提交發票時，您必須從匯入的發票開始。 若要確保可以在沒有手動干預的情況下從頭到尾處理發票，您必須在工作流程設定中包含自動過帳工作。 與訂購單 (PO) 相關的發票以及包含非 PO 採購類別和非庫存行的發票可以自動提交到工作流程系統。 手動輸入的發票必須手動提交到工作流程系統。

工作流程中該 **提交者** 的值是使用者識別碼，該識別碼是為 **程序自動化** 頁面上的 **將廠商發票提交到工作流程** 背景工作而輸入。 擁有該使用者識別碼的使用者將能依需要從工作流程系統中回收發票。

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>將過帳的產品收據與具有三向比對原則的發票行進行比對

作為非接觸式應付帳款開立發票流程的一部分，過帳的產品收據可以與發票行自動進行比對。 必須為此工作定義三向比對原則。 如果 **廠商發票自動化** 功能已在 **功能管理** 頁面啟用，則可使用此功能。

該比對流程將一直執行，直到相符的產品收據數量等於發票數量。 但是，如果單個發票行有多個產品收據，則需要多次執行該流程以實現全數量匹配。 您可以指定系統在斷定流程失敗之前應嘗試比對產品收據與發票行的最多次數。 該程序將每小時或每天在背景執行， 

您可以在將發票提交到工作流程系統的過程中執行自動比對程序。 或者，您可以將其作為獨立程序執行。 在 **應付帳款參數** 頁面的 **廠商發票自動化** 的索引標籤上所設的將產品收據與發票行進行比對的設定 (**應付帳款\>設定\>應付帳款參數**)。

具有三向比對原則的發票行，其中相符的收據數量小於發票數量，將包含在自動比對產品收據程序中。

要檢視不屬於自動提交到工作流程程序的發票 **最後比對** 狀態，請從 **廠商發票** 頁面開啟發票。 當您檢視發票時，會更新比對驗證資訊。 可以使用 **驗證發票比對** 背景工作來自動更新該 **最後比對** 狀態。 您可以在 **程序自動化** 頁面的 **背景工作** 索引標籤設定自動更新 **最後比對** 狀態的程序 (**系統管理\>設定\>程序自動化**)。

如果滿足以下任何條件，發票行將從自動處理中排除: 

- 該 **自動收據比對狀態** 發票行的值為 **失敗**。
- 發票正在使用中。
- 發票在工作流程系統中。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
