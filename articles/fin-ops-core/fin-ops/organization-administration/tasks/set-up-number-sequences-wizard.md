---
title: 使用精靈設定數列
description: 本主題說明如何使用精靈同時設定所有必需的數列。
author: SunilGarg
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7388a835147e1e8242463fee98c57c300d062877
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2021
ms.locfileid: "8460313"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>使用精靈設定數列

[!include [banner](../../includes/banner.md)]

數列用於為需要識別碼的主資料記錄和交易記錄產生可讀的唯一識別碼。 需要識別碼的主資料或交易記錄稱為參考。 在為參考建立新記錄之前，您必須設定數列並將其與參考相關聯。 本主題說明如何使用精靈同時設定所有必需的數列。 用來建立此程序的示範資料公司為 USMF。

1. 進入 **導覽 > 模組 > 組織管理 > 數列 > 數列**。
2. 選取 **產生**。
3. 選取 **下一步**。

   - 在此頁面上，您可以修改識別碼、最低值和最高值。 此外，您可以指示數列是否必須是連續的。   
   - 如果您必須為數列預先指派編號，請不要選取 **連續** 選項。 若要將範圍區段新增到數列的格式中，請在清單中選取格式，然後選取 **在格式中加入範圍**。 若要將範圍區段從數列的格式中移除，請在清單中選取格式，然後選取 **從格式中移除範圍**。 若要從自動產生中排除數列，請選取清單中的數列，然後選取 **刪除**。  

4. 選取 **下一步**。
5. 選取 **完成**。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
