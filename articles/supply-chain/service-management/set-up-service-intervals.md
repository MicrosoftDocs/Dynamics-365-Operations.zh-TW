---
title: 設定服務間隔
description: 本主題介紹如何設定服務間隔。 服務間隔表示建立服務訂單時為服務合約行建立服務訂單行的頻率。
author: kamaybac
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementinterval
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e0aeaef9fcf0c909638a9452633a321121e20814
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448056"
---
# <a name="set-up-service-intervals"></a>設定服務間隔  

[!include [banner](../includes/banner.md)]

服務間隔表示建立服務訂單時為服務合約行建立服務訂單行的頻率。

1. 按一下 **服務管理** \> **設定** \> **服務合約** \> **服務間隔**。
2. 建立新的服務間隔。
3. 輸入服務間隔的識別碼和描述。
4. 在 **範圍** 欄位，選擇範圍。
5. 在 **頻率** 欄位，輸入頻率。 必須將頻率作為係數乘以範圍，以獲得服務協議的間隔。
6. 按 **Alt+S** 以儲存服務間隔。

## <a name="example"></a>範例

您要建立 10 天的服務間隔。

**建立 10 天服務間隔**

1. 按一下 **服務管理** \> **設定** \> **服務合約** \> **服務間隔**。
2. 建立新的服務間隔。
3. 輸入服務間隔的識別碼和描述。
4. 在 **範圍** 欄位，選擇 **每天**。
5. 在 **頻率** 欄位，輸入「10」。
6. 按 **Alt+S** 以儲存服務間隔。

## <a name="related-topics"></a>相關主題

[服務間隔](service-intervals.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]