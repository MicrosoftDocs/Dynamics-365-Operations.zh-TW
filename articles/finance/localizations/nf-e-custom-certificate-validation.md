---
title: NF-e 自訂證書驗證
description: 本主題提供有關啟用和使用 NF-e 自訂證書的資訊。
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8144e16b127bdbe954ef44f52c5ac71689a2036e6085e9a4ccc8bb17f91ae9b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450576"
---
# <a name="nf-e-custom-certificate-validation"></a>NF-e 自訂證書驗證

[!include [banner](../includes/banner.md)]

巴西根憑證授權機構核發憑證的 **伺服器驗證目的** 屬性預設是關閉的，必須手動啟用。 某些情況下，自動憑證更新會切換此屬性為不再啟用。 屆時，TLS 連接會受到影響並且不再受到信賴。 針對米納斯吉拉斯州 (MG) 和巴拉那 (PR) 州正式環境核發巴西電子財政文件模型 55 (NF-e) 的能力受到影響。

若要對 **NF-e 自訂憑證驗證** 啟用修正功能，請前往 **功能管理**。 本項能允許 V5 和 V10 憑證驗證替代解決方案，並准許與 Web 服務建立受信任連接，這是 NF-e 安全傳輸和接收 SEFAZ 授權的必要成因。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
