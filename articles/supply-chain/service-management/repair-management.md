---
title: 維修管理
description: 系統性地分組問題，以協助提出過去成功解決方案的建議。
author: kamaybac
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1456c65f28d2a1d06497ddde81c9e68cc078c061
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448059"
---
# <a name="repair-management"></a>維修管理       

[!include [banner](../includes/banner.md)]


對於維修管理，您可以系統性地分組問題。 這是為了協助提出過去成功解決方案的建議。

您設定徵兆、診斷和解決設置。 當您收到類似的維修物品時，所有這些設置之後都可以應用。 您還可以設定能夠追蹤某一維修問題進度的維修階段。

## <a name="setting-up-repair-management"></a>設定維修管理

使用以下設定表格輸入將用於指定維修的徵兆、診斷和解決方法資訊。

- **服務管理** \> **設定** \> **維修** \> **條件**。
- **服務管理** \> **設定** \> **維修** \> **徵兆區域**。
-  **服務管理** \> **設定** \> **維修** \> **診斷區域**。
- **服務管理** \> **設定** \> **維修** \> **解決方法**。
- **服務管理** \> **設定** \> **維修** \> **維修階段**。

## <a name="symptoms-and-conditions"></a>徵兆和條件

徵兆是客戶提出的問題特點。 徵兆包括指示需要維修的客戶觀察。

您可以設定徵兆區域、徵兆代碼和條件。 徵兆區域包含故障區域，徵兆代碼包含故障徵兆。 條件說明問題發生時的情況或環境。

**範例**

電腦送修，因為硬碟在長時間使用後出現故障。 硬碟故障導致藍畫面錯誤。 收到電腦的技術人員輸入以下徵兆和條件：

1.  徵兆區域是硬碟

2.  徵兆代碼是藍畫面錯誤

3.  條件是硬碟長時間使用後出現故障

## <a name="diagnosis-and-resolutions"></a>診斷和解決方法

診斷和解決方法欄位是從維修角度進行的陳述。 這些是技術人員為調查問題所執行的步驟。

診斷區域包含解決問題而必須執行的操作。 診斷代碼是處理問題的方式，解決方法可能是維修、更換物品，或是客戶取消訂單。 例如，如果電腦已維修完成，診斷區域可以是「瑕疵零件」，診斷代碼可以是「安裝新顯示卡」，解決方法可以是「已更換」。

## <a name="repair-stages"></a>維修階段

維修階段說明維修過程的進度。 維修階段具有 **已完成** 驗證參數，表示維修明細已經完成，並已記錄完成日期和時間。

## <a name="applying-repair-management"></a>應用維修管理

若要將維修管理應用於某一品項，必須為該品項在服務訂單上設定服務對象關係。 然後，可以從服務訂單中建立維修明細，明細中包含與目前問題有關的資訊。 在維修明細上，您定義處於維修狀態的服務對象以及有關徵兆、診斷和執行的資訊。 您還可以為維修明細建立備註。

可以為維修過程中的每個步驟建立維修明細。

## <a name="create-a-repair-line-on-a-service-order"></a>在服務訂單上建立維修明細

1.  前往 **服務管理** \> **一般** \> **服務訂單** \> **服務訂單**。

2.  選擇需要維修的服務對象之服務訂單。

3.  選擇 **維修** \> **維修明細** 以開啟 **維修明細** 表單。

4.  選取 **新增** 以建立新明細。

5.  選取服務物件。 您可以選擇已在服務訂單上設定對象關係的任何服務對象。

6.  選擇維修明細中相關的任何預設徵兆、診斷和執行值，然後選擇 **備註** 索引標籤以視需要在維修明細中建立備註。

7.  選擇 **儲存**，以儲存維修明細。 使用保存時間更新 **維修明細** 表單的 **一般** 索引標籤的 **建立日期和時間** 欄位。

## <a name="tracking-progress-and-resolving-a-repair-issue"></a>追蹤進度並解決維修問題

您可以設定維修明細的維修階段以追蹤維修進度。

解決維修問題後，您可以關閉維修明細。 將修復階段設定為 **已完成** 屬性啟用的階段。 目前日期和時間在明細上登記為結束時間。

## <a name="close-a-repair-line-for-a-resolved-issue"></a>關閉已解決問題的維修明細

1.  開啟 **維修明細** 表單。 按照本主題前述的過程建立維修明細。

2.  選擇含有想要關閉維修問題的維修明細。

3.  在 **維修階段** 欄位中，選擇 **已完成** 屬性已啟用的階段。

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]