---
title: 釋出生產訂單
description: 此程序說明如何釋出生產訂單。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f6d0db7f93e113d8f41effd68ce19aa065b031fd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448638"
---
# <a name="release-a-production-order"></a>釋出生產訂單

[!include [banner](../../includes/banner.md)]

此程序說明如何釋出生產訂單。 建立此程序的示範資料公司為 USMF。 這是解釋生產訂單生命週期的第四個程序 (共七個程序)。

1. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
    * 在網格中，選擇具有「已排程」狀態的生產訂單。  
2. 在 [動作窗格] 上按一下 [產品訂單]。
3. 按一下 [釋出]。
    * 在此頁面，您可以確認釋出所選範圍的生產訂單。 如果要新增訂單，按一下 [選取]。  
    * 釋出步驟指示何時將生產訂單釋出到工廠生產線，以便工廠操作員可以報告生產作業的進度。 可以發出包含有關處理工作資訊的生產文件。 對於倉庫流程設定的品項，會產生原物料揀料的倉庫工作。  
4. 按一下「一般」索引標籤。
    * 選擇應列印的生產報告。 作業卡報告列印每個排程工作的頁面，並要求在工作層級安排生產訂單。 該報告包含有關排程的開始和結束時間、要生產的數量以及處理工作的資源之資訊。 途程工作報告收集同一頁面的相同資訊，但不會列印每個工作的頁面。 途程卡報告僅顯示作業，但不顯示工作。 因此，此報告不需要工作排程，但可以在作業層級排程生產訂單時使用。  
5. 按一下 [列印途程卡] 核取方塊。
6. 按一下 [確定]。
7. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]