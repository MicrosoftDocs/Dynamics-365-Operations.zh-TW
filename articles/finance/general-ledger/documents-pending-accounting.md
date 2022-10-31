---
title: 待記帳單據
description: 本文章描述如何在 [待記帳單據] 頁面中使用該功能。
author: ryanCCarlson2
ms.date: 09/02/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: f37d46659b2fc5bf9933719811a7b90cc4e80f52
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709241"
---
# <a name="documents-pending-accounting"></a>待記帳單據

[!include [banner](../includes/banner.md)]

本文章描述如何在 **待記帳單據** 頁面中使用該功能。

在 Microsoft Dynamics 365 Finance 10.0.30，可以使用 **增強的來源文件會計架構效能** 功能。 此功能從普通發票的過帳流程開始，改善了已啟用來源文件的單據過帳之過帳流程。

啟用此功能後，分類帳單據的過帳會與會計產生或 *記入帳目* 流程分開進行，會計產生或記入帳目流程會建立轉移至總帳的完整會計明細。 例如，在普通發票過帳流程中，會先在 **應收帳款** 模組中記錄客戶發票才產生完整會計。 此增強效能功能可以更快速記錄客戶發票，但會延遲會計產生。

**待記帳單據** 頁面上可使用下列按鈕。

- **產生會計** – 提交目前待記帳科目產生所需的單據以便記入帳目。
- **檢視分配** – 檢視清單中所選取單據的會計分配。
- **檢視錯誤記錄檔** – 檢視會計狀態指出有錯誤的單據現有的任何錯誤訊息詳細資料。 您可以透過選取文件明細上的 **錯誤記錄檔** 連結來檢視相同錯誤訊息的詳細資料。

會計產生是由名為 **會計架構處理器** 的流程自動化背景程序來完成。 如需有關所有流程自動化的設定和組態之詳細資訊，請參閱[流程自動化](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
