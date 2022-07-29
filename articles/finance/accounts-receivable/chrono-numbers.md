---
title: 按時間順序對文件和憑單進行編號
description: 本主題介紹如何為適用文件和相關憑單設定和使用時間順序編號。
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ced09fb4be49dbfd10dac9f9ece86372d38e854460c7ca6cd72922c64ac7cce4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450234"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a>按時間順序對文件和憑單進行編號

[!include [banner](../includes/banner.md)]


在某些國家/地區，法律要求按時間順序對文件和相關憑單進行編號。 時間順序必須受期間支援。 屬於較早期間的所有數字必須小於屬於較晚期間的數字。 為了滿足此要求，已執行按時間順序編號的功能。 本主題介紹如何為適用文件和相關憑單設定和使用時間順序編號。

## <a name="prerequisites"></a>先決條件

在功能管理工作區中，打開 **按時間順序編號** 功能。 更多資訊，請參閱[功能管理概觀](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。

## <a name="configure-chronological-numbering"></a>設定按時間順序編號

按時間順序編號會影響以下文件。

**應收帳款**
- 客戶發票
- 客戶發票憑單
- 銷售貸方通知單
- 銷售貸方通知單憑單
- 普通發票
- 普通發票憑單
- 普通發票貸方通知單
- 普通發票貸方通知單憑單
- 裝箱單
- 裝箱單憑單
- 裝箱單更正憑單
- 利息單憑單
- 催款單憑單

**應付帳款**
- 發票憑單
- 貸方通知單憑單
- 產品收據憑單

**專案管理**
- 發票
- 發票憑單
- 貸方通知單
- 貸方通知單憑單 

### <a name="define-number-sequences"></a>定義編號規則

要定義編號規則，請前往 **組織管理** > **編號規則** > **編號規則**。 您可以根據需要定義任意數量的編號規則，以涵蓋所需憑單的受影響期間。 

為每個編號規則指定一個公司。 必須定義編號規則的區段，以便它們提供期間的時間順序。 例如，區段名稱可以包含特殊的首碼來識別特定的期間。

![編號規則設定。](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a>設定編號規則群組

要設定編號規則群組，請前往 **應收帳款** > **設定** > **應收帳款參數**。 在 **編號規則** 索引標籤，根據需要盡量定義編號規則群組以涵蓋受影響的期間。 

對於每個群組，在 **參考** 區段選擇其中一個支援的文件參考，然後在 **編號規則代碼** 欄位中，參考先前為相關期間建立的編號規則。

![編號規則群組設定。](media/chrono-num-sequence-group.jpg)

同樣，在 **應付帳款** 和 **專案管理和會計** 模組編號規則群組。

### <a name="configure-number-sequence-groups-chronology"></a>設定編號規則群組的時間順序

要設定編號規則群組的時間順序，請前往 **組織管理** > **編號規則** > **按時間順序編號規則群組**。 定義編號規則群組的適用條件。

![時間順序編號設定。](media/chrono-num-sequence-group-period.jpg)

| 欄位            | 描述                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 生效  | 編號規則群組適用性的開始日期。 |
| 到期      | 編號規則群組適用性的結束日期。 如果不套用結束日期，請選擇 **永不**。 |
| 編號規則群組 | 期間將用於產生文件編號的編號規則群組。 |
| 原始編號規則群組 | 此編號規則群組代碼用於在文件已分配特定的 *永久* 編號規則群組的情況下進行其他篩選。 空值視為特定值。 如果您需要忽略初步分配的群組，請為此設定使用 **預設** 選項。 |
| 預設 | 如果啟用，系統將忽略初步分配的文件編號規則群組，並僅使用期間開始日期和結束日期進行適用性分析。 如果關閉，系統使用完整組合 **生效日期** + **到期日期** + **原始編號規則群組** 進行選擇。 |

## <a name="document-posting"></a>文件過帳
過帳文件時，會根據文件的過帳日期將相應的編號規則群組分配給該文件，然後用於根據檢測到的編號規則產生文件編號。 系統將提供有關編號規則群組分配的訊息。

![文件編。](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> 對於某些國家/地區，已經為文件編號實施了特定邏輯。 在這種情況下，特定國家/地區的邏輯將覆寫 **按時間順序編號** 功能。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
