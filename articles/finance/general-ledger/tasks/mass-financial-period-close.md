---
title: 大規模財務期結束
description: 本主題顯示如何暫停某段期間或一次永久關閉某段期間或多間法人實體。
author: aprilolson
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7dac267d2d4ce0824bc47b63b8d07913a8dd7f02bcccc025880701cb4d0bdd3d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450537"
---
# <a name="mass-financial-period-close"></a>大規模財務期結束

[!include [banner](../../includes/banner.md)]

本主題顯示如何暫停某段期間或一次永久關閉某段期間或多間法人實體。 此外，本任務將顯示如何限定使用者群組過帳到特定模組。

1. 請在瀏覽窗格中前往 **模組 > 總帳 > 期間關閉 > 分類帳行事曆**。 請注意，顯示的法人實體清單取決於頁面上選取的會計行事曆。 唯有使用選取會計行事曆的法人實體才會顯示。
2. 選取 **編輯**。
3. 選取您希望修改狀態的期間。
4. 請選取您希望更新狀態的法人實體。 您可以藉由選取網格左上角的勾選標記快速選取所有法人實體。  
5. 選取 **更新模組存取** 定義對選取模組的過帳存取權。 模組狀態也可藉由編輯網格記錄逐一更新。 當您希望快速更新多筆法人實體記錄時，此按鈕很有用。  
6. 在 **應用程式** 模組中，選取您希望更新狀態的模組。 點選 **選取**。
7. 在 **存取** 等級，選取 **全部**、**無** 或特定的使用者群組。 點選 **選取**。 全部指出如果期間打開，所有對模組具有編輯存取權的使用者都可以過帳。 無指出如果期間打開，使用者無法過帳到模組。 特定使用者群組指出只有此群組的使用者才能在期間打開時過帳到模組。  
8. 選取 **更新**。
9. 選取另一段期間更新狀態。
10. 選取您希望更新期間狀態的法人實體。
11. 選取 **更新期間狀態** 和設定 **暫停**、**打開** 或 **永久關閉** 的狀態。 **打開** 指出可以過帳的期間，前提是使用者有存取權。 **暫停** 意指期間不能過帳，但可以重新打開。 **永久關閉** 意指期間關閉，永遠不再打開。 調整項無法過帳。 我們不建議將期間設定為 **永久關閉**，除非所有調整項和稽核完成。  
12. 選取 **更新**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]