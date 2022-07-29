---
title: 確認付款概觀
description: 本文章提供有關確認付款的資訊，其用來產生可向銀行出具的電子支票清單。
author: panolte
ms.date: 08/22/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "88463"
- intro-internal
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 5f36230b68986cffc985353a7130ba429dabd10e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451425"
---
# <a name="positive-pay-overview"></a>確認付款概觀

[!include [banner](../includes/banner.md)]

本文章提供有關確認付款的資訊，其用來產生可向銀行出具的電子支票清單。 

確認付款用來產生可向銀行出具的電子支票清單。 確認付款檔案可幫助銀行防止支票詐騙。 您設定確認付款產生每次列印支票時的電子支票清單。 接著向銀行出具支票時，銀行會比較這張支票與您先前提交的支票清單。 如果支票與清單中的支票相符，銀行將清除支票。 如果支票與清單中的支票不相符，銀行將保留支票以供審查。

確認付款也稱為 SafePay。 

付款確認檔案可能含有相關收款人和支票金額的敏感資料。 因此，請確保從檔案產生後直到銀行接收檔案之前，採取合適的安全措施。 確認付款是根據網路瀏覽器的下載說明下載。 

使用資料實體建立付款確認檔案。 產生確認付款檔案之前，您必須設定 XML 的轉換格式，以便將資料轉換為銀行可以使用的格式。 

您必須針對您希望產生確認付款資訊的各個銀行帳戶指派確認付款格式。 產生付款後，您可以產生單一法人實體和單一銀行帳戶的確認付款檔案。 或者，您可以同時產生多間法人實體和銀行帳戶的確認付款檔案。 

當付款確認檔案中列出的支票支付後，您會從銀行收到一組確認編號。 接著您可以在系統中確認此確認付款檔案。 

如果您必須更改付款確認檔案，您可以將其撤回。 而付款確認檔案中的每張支票方面，會重設已指出該支票是否納入付款確認檔案的欄位。

更多資訊，請參閱[設定和產生確認付款檔案](set-up-generate-positive-pay-files.md)。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]