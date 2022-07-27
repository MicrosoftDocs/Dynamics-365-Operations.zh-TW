---
title: 服務等級協定概觀
description: 在服務等級協定中，客戶同意接受根據服務公司記錄問題的時間和解決問題的時間的最短回應時間。
author: kamaybac
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a36b1c0e18201ae04a9fe13cb4f9524a19655c92
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449757"
---
# <a name="service-level-agreements-overview"></a>服務等級協定概觀       

[!include [banner](../includes/banner.md)]


服務等級協定 (SLA) 是服務公司和服務客戶之間的協定。 在 SLA 中，客戶同意接受根據服務公司記錄問題的時間和解決問題的時間的最短回應時間。

SLA 設定了為客戶提供服務的標準等級，並使服務公司明確何時應完成服務工作。

可以建立任意數量的 SLA 來為服務客戶提供不同等級的服務。

## <a name="create-a-service-level-agreement"></a>建立服務等級協定

1.  點選 **服務管理** \> **設定** \> **服務合約** \> **服務等級協定**。

2.  在 **服務等級協定** 欄位中輸入服務等級協定的名稱。

3.  輸入允許附加到服務等級協定的服務呼叫完成時間。 然後，如果您希望服務等級協定是以特定行事曆為基礎，請選擇行事曆。

## <a name="apply-a-service-level-agreement"></a>套用服務等級協定

SLA 直接套用於服務協定。

您手動建立並附加到具有 SLA 服務協定的服務訂單將根據該 SLA 進行衡量。

您自動建立的服務訂單不會附加到 SLA。

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a>將服務等級協定套用至服務協定

1.  按一下 **服務管理** \> **常用** \> **服務合約** \> **服務合約**。 選擇要套用 SLA 的服務協定，然後在 **動作窗格** 點選 **編輯**。

2.  在 **服務等級協定** 欄位中，選擇您要指派的 SLA。

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a>將服務等級協定套用至服務協定群組

1.  點選 **服務管理** \> **設定** \> **服務合約** \> **服務合約群組**。

2.  在 **服務等級協定** 欄位中，選擇您要指派的 SLA。

## <a name="track-time-on-a-service-order-against-an-sla"></a>根據 SLA 追蹤服務訂單的時間

當您為指派了 SLA 的服務協定建立新服務訂單時，將啟動服務交付的時間間隔，並且系統會開始追蹤交付時間。 此外，您可以設定以下選項：

  - 您可以在服務訂單上開始和停止時間記錄，以記錄在服務訂單上花費的總時間。

  - 您可以監視服務等級協定中設定的時間間隔的合規性。

  - 可以定義超出服務等級協定的時間間隔時，必須設定的原因代碼。

## <a name="see-also"></a>請參閱

[查看服務等級協定的合規性](view-compliance-with-service-level-agreements.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]