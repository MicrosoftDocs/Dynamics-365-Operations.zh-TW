---
title: 疑難排解規劃最佳化
description: 本主題介紹如何修正您在使用規劃最佳化時可能遇到的問題。
author: ChristianRytt
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: bbf21abae60d4adee5a23a8405d14907b91724fa2cbf31c901bb46c589b2ea49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447195"
---
# <a name="troubleshoot-planning-optimization"></a>疑難排解規劃最佳化 

[!include [banner](../../includes/banner.md)]

本主題介紹如何修正您在使用規劃最佳化時可能遇到的常見問題。

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>未完成規劃最佳化增益集的安裝

規劃最佳化需要啟用 Lifecycle Services (LCS)，高可用性環境，第 2 層或更高層（不是 OneBox 環境），具有 Dynamics 365 Supply Chain Management 10.0.7 版本或更高版本。 如果您嘗試在 OneBox 環境中安裝增益集，安裝將無法完成。

**修正**：取消安裝並使用高可用性環境，第 2 層或更高層（不是 OneBox 環境）。

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>啟用規劃最佳化時，批次工作計劃就會失敗

當您啟用規劃最佳化時，內建總規劃引擎將自動停用。 如果在啟用規劃最佳化時觸發為內建 Supply Chain Management 規劃引擎而建立的總規劃批次工作，那麼它們將會失敗。 您可能會收到一則錯誤訊息，例如 *此操作觸發了啟用規劃最佳化時不支援的總規劃*。

**修正**：取消為內建 Supply Chain Management 規劃引擎而建立的所有總規劃批次工作。

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>規劃最佳化結果與先前結果不同

規劃最佳化在某些方面不同於內建總規劃設計。 這也可由待決功能而引起。

**修正**：執行規劃最佳化適合度分析，然後在參考相關文件的同時分析結果以了解影響。 如需詳細資訊，請參閱[規劃最佳化適合度分析](planning-optimization-fit-analysis.md)。

## <a name="cant-enable-planning-optimization"></a>無法啟用規劃最佳化

在你可以將 **使用規劃最佳化** 設為 **是** 之前，此 **連線狀態** 必須為 **已連線**。 有關詳細資訊，請參閱[開始使用規劃最佳化](get-started.md)。

**修正**：確認規劃最佳化增益集已成功安裝。

## <a name="error-message-is-shown-during-ctp"></a>CTP 期間顯示錯誤訊息

如果您在啟用規劃最佳化時嘗試從銷售訂單執行可承諾能力 (CTP)，您將會收到以下錯誤訊息：*此操作觸發了啟用規劃最佳化時不支援的總規劃*。

這與計劃作為生產訂單支援的一部分的待決功能有關。

**修正：** 直到 CTP 支援可用之前，在啟用規劃最佳化時避免 CTP 計算。

## <a name="additional-resources"></a>其他資源

[開始使用規劃最佳化](get-started.md)

[規劃最佳化適合度分析](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]