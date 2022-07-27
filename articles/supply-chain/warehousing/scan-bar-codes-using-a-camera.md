---
title: 在 Warehouse Management 行動裝置應用程式中使用相機掃描條碼
description: 本主題說明如何設定 Warehouse Management 行動裝置應用程式以使用行動裝置上的相機掃描條碼。
author: Mirzaab
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: cc58d88865fea17e0e27463b25e2ba815ee1a5b1
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449520"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a>在 Warehouse Management 行動裝置應用程式中使用相機掃描條碼

[!include [banner](../includes/banner.md)]

本主題說明如何設定 Warehouse Management 行動裝置應用程式以使用行動裝置上的相機掃描條碼。

## <a name="setup"></a>設定

在 Warehouse Management 行動裝置應用程式的顯示設定中，可選擇是否應使用相機進行條碼掃描。 如果啟用 **將相機做為掃描器**，則可以在將慣用輸入模式設定為 **掃描** 的每個輸入欄位上使用相機.

若要控制輸入欄位是否應可掃描，請在 **倉庫應用程式欄位名稱** 頁面，將 **慣用輸入模式** 設定為 **掃描**。 選擇此選項後，可以使用相機在 Warehouse Management 行動裝置應用程式中進行掃描。 如需更多資訊，請參閱[設定 Warehouse Management 行動裝置應用程式的欄位](configure-app-field-names-priorities-warehouse.md)。

## <a name="supported-bar-code-formats"></a>支援的條碼格式

支援最常見的條碼格式，包括 Code 128、Code 39、Code 93、EAN-8、EAN-13、UPC-E、UPC-A 和 QR 代碼。

## <a name="navigation"></a>瀏覽

在輸入欄位的 **慣用輸入模式** 設定為 *掃描* 的每個頁面上，將啟動相機頁面。進入相機頁面後，請使用以下選項進行瀏覽：

- 選擇返回按鈕返回到 **工作和詳細資料** 頁面。
- 選擇 **任務和細節** 頁面上的鉛筆以移至可手動鍵入輸入的頁面。
- 選擇 **任務和細節** 頁面上的相機以返回相機頁面。

在相機頁面上選擇相機按鈕時，在嘗試識別條碼時頁面會變暗。 如果在 5 秒內未識別出條碼，則程序將逾時，而相機按鈕將再次變為可用。 然後就能夠再次嘗試掃描條碼。

將相機對準條碼時，請讓條碼在括號內對齊以獲得最佳效果。 條碼掃描成功後將處理結果，並進入下一步。 如果下一步中又包含另一個將慣用輸入模式設定為 [掃描] 的輸入欄位，則會再次啟動相機頁面。 如果下一步不是掃描欄位，則不會啟動相機頁面。



[!INCLUDE[footer-include](../../includes/footer-banner.md)]