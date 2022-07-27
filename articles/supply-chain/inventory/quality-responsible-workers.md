---
title: 負責核准不符合項的工作人員
description: 本主題介紹如何設定負責核准不合格項的工作人員。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fd1c7c86ac8627bd332bc578e98b4d7f091cdc8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448854"
---
# <a name="workers-responsible-for-approving-nonconformances"></a>負責核准不符合項的工作人員

[!include [banner](../includes/banner.md)]

本主題介紹如何設定負責核准不合格項的工作人員。

必須先核准不符合項，使用者才能開始輸入更正或操作等詳細資料。 在使用者可核准或拒絕不符合項之前，他們的使用者識別碼 (使用者記錄) 必須連結到工作人員記錄。 您可以視需要設定負責品質的工作人員，然後允許一名工作人員代表另一名工作人員核准工作。

## <a name="enable-a-user-for-nonconformance-processing"></a>允許使用者處理不符合項

在使用者可核准或拒絕不符合項之前，您必須將他們的使用者識別碼 (使用者記錄) 連結到工作人員記錄。 接著，系統可以自動設定核准欄位，並且可以自動填寫目前使用者的時程表。 在使用者可以使用文件附註之前，您必須在其使用者選項中啟用文件處理選項。

1. 進入 **系統管理 \> 使用者 \> 使用者**。
1. 查找並開啟應可以核准或拒絕不符合項的使用者。
1. 將 **人員** 欄位設定為與目前使用者記錄相關的工作人員名稱。
1. 在動作窗格上，選擇 **使用者選項**。
1. 在目前使用者記錄的 **選項** 頁面，在 **喜好設定** 索引標籤中，將 **啟用文件處理** 選項設定為 *是*。
1. 關閉頁面。

## <a name="define-workers-that-are-responsible-for-quality"></a>定義負責品質的工作人員

1. 移至 **庫存管理 \> 設定 \> 品質控制 \> 對品質負責的工作者**。
2. 在動作窗格上，選擇 **新增**。
3. 在 **工作人員** 欄位，選擇輸入品質資料的工作人員。
4. 在 **負責的工作者** 欄位，選擇所選工作人員代表的工作人員。 當建立和更新不符合項時，系統會根據預設，將這位工作人員輸入 **工作人員** 欄位。

## <a name="additional-resources"></a>其他資源

- [品質管理概觀](quality-management-processes.md)
- [啟用品質和不符合項管理](enable-quality-management.md)
- [品質收費](quality-charges.md)
- [不符合項隔離區](quality-quarantine-zones.md)
- [不符合項的診斷類型](quality-diagnostic-types.md)
- [不符合項的品質收費](quality-charges.md)
- [不符合項操作](quality-operations.md)
- [倉庫流程的品質管理](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
