---
title: 將固定資產作為報廢處置
description: 本主題介紹清除作為報廢處置的固定資產交易的流程。
author: moaamer
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 90eb791bae2bbe70cf9fe7127a98962305449e1d0b370cfa001afbd3654046ec
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450555"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a>將固定資產作為報廢處置

[!include [banner](../includes/banner.md)]

本主題介紹清除作為報廢處置的固定資產交易的流程。 可以清除的交易類型包括資產購置及累計折舊交易和其他固定資產交易。 清除這些交易會影響資產負債表科目，例如購置調整、折舊調整、重估、增值和減值科目。

| 交易                                         | 借記 (Dr.) | 貸記 (Cr.) |
|-----------------------------------------------------|-------------|--------------|
| 借記累計折舊                        | X           |              |
| 貸記固定資產損益                          |             | X            |
| 借記固定資產損益                          | X           |              |
| 貸記固定資產購置帳戶                 |             | X            |
| 借記固定資產損益 (帳面淨值 \[NBV\]) | X           |              |
| 貸記固定資產損益 (NBV)                    |             | X            |

> [!NOTE]
> 建議您與公司的首席財務官 (CFO) 或財務總監密切合作，以確定套用於每種交易類型的正確帳戶，並驗證處置流程及其產生的交易是否正確更新了這些帳戶。

在將固定資產作為報廢處置之前，您必須建立與資產的購置價值、當年折舊、前一年折舊和資產的 NBV 相關聯的會計科目。 固定資產交易類型列在 **固定資產過帳設定檔** 頁面上。 前往 **固定資產 \> 設定 \> 固定資產過帳設定檔**，然後在 **處置** FastTab，在格線上方的欄位中選擇 **廢料**。 下圖顯示了 **固定資產過帳設定檔** 頁面上的固定資產交易類型清單。


[![將資產處置為廢料，圖 1。](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)

對於以下範例，固定資產於 2018 年 1 月 1 日購置，並將於 2019 年 3 月 31 日報廢。

- **購置價格：** 24,000.00 美元 (USD)
- **使用年限：** 兩年
- **折舊方法：** 直線法使用年限
- **折舊金額：** 每月 1,000.00 美元

使用以下公式計算固定資產的 NBV：

帳面價值 = 購置價格 - 折舊

在此範例中，從 2018 年 1 月到 2019 年 3 月，購置了固定資產並進行 15 個月的折舊。 因此，資產的 NBV 為 9,000.00 美元 (24,000.00 美元 – 15,000.00 美元)。

[![固定資產折舊範例。](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)


要建立處置日記帳，請前往 **固定資產 \> 日記帳分錄 \> 固定資產日記帳**，然後在動作窗格中，選擇 **行**。 選擇 **處置 - 報廢**，然後選擇固定資產識別碼。 要完全處置資產，請勿在 **借記** 欄位或 **貸記** 欄位中輸入值。

[![固定資產日記帳。](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)

固定資產處置報廢交易透過以下方式變更固定資產帳簿的欄位值：

- 在 **餘額** 區段，**狀態** 欄位更新為 **已報廢**。
- 在 **簽發** 區段，**處置日期** 欄位設定為資產報廢的日期。

[![固定資產日記帳詳細資料。](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)

下圖顯示了固定資產餘額。

[![固定資產餘額。](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)

下圖顯示了已過帳的憑單。

[![帳面價值。](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]