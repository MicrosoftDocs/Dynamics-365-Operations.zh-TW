---
title: 混合牌照收貨
description: 本主題介紹如何使用混合牌照收貨，透過行動裝置註冊和建立多個品項的工作。
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84b01e9c6ad041fe95b46c97d89b90e85422d170399754062a6422319fc23a63
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447207"
---
# <a name="mixed-license-plate-receiving"></a>混合牌照收貨

[!include [banner](../includes/banner.md)]

混合牌照收貨允許您在註冊和建立上架工作之前，建構由多個品項組成的牌照。 

由多個品項組成的牌照不必在接收站分割，以便您註冊每個品項。 

使用與品項相關的流程識別來源文件行時，您可以掃描品項控制上的條碼。 如果條碼上設定了數量和測量單位 (UOM)，品項和數量將自動新增到混合牌照中，您將返回螢幕掃描另一個品項。 這使您可以快速掃描所有品項，無需在每個步驟中進行確認。 

在混合牌照收貨流程中，您可以顯示已掃描到牌照的品項清單，並可在此處修改或更正品項的數量。

## <a name="where-it-applies"></a>適用處

混合牌照收貨是一種行動裝置收貨流程，用於同時註冊和建立多個行/品項的工作。 如果您收到包含多個品項的入站牌照，這很有用。 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a>如何設定混合牌照收貨
混合牌照收貨設定為行動裝置功能表項目。

您需要以不使用現有工作的模式工作建立一個新功能表項目，並使用以下方法之一：

- 混合牌照收貨
- 混和牌照接受及存放

識別來源文件行的選項是訂購單品項、訂購單行、退貨單、轉移訂單品項和轉移訂單行。 這些選項可以變更單個牌照上的收貨順序。 最後一個選項是依據裝載品項。 您可以將多個品項新增到牌照，但不能在多個裝載之間切換。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]