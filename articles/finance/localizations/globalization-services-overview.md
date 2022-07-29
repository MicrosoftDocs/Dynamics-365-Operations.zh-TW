---
title: Dynamics 365 全球化服務
description: 本主題概述 Microsoft Dynamics 365 全球化服務。
author: JaneA07
ms.date: 04/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1dfe88bf6eb0cf479f8febd8a599b165b71d932d
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451455"
---
# <a name="dynamics-365-globalization-services"></a>Dynamics 365 全球化服務

[!include [banner](../includes/banner.md)]

您可以配置下列全球化服務來擴展某些 Microsoft Dynamics 365 線上服務存在的功能：

- **Regulatory Configuration Service (RCS)** 支援不同類型的電子文件和報表組態。 RCS 提供組態存放庫為獨立服務的電子申報 (ER) 設計器強化版。 有關詳細資訊，請參閱[Regulatory Configuration Service](rcs-overview.md)。
- **電子發票** 匯集用於轉換、數位簽名的可組態格式，以及用於搭配外部 Web 服務連線能力的可組態整合功能，包括認證和應變處理。 有關詳細資訊，請參閱[電子發票](e-invoicing-service-overview.md)。
- **稅金計算** 藉由支援多組稅號、稅碼決定、稅金計算設計器和執行引擎提供更靈活的功能，以符合全世界複雜的納稅法規。 如需詳細資訊，請參閱[稅金計算](global-tax-calcuation-service-overview.md)。

這些全球化服務提供與下列 Dynamics 365 Online Service 整合的開箱即用服務。

| 線上服務 | RCS | 電子發票 | 稅金計算 (預覽) |
|----------------|-----|----------------------|---------------------------|
| Dynamics 365 Finance | 是 | 是 | 是 | 
| Dynamics 365 Supply Chain Management | 是 | 是 | 是 | 
| Dynamics 365 Project Operations | 是 | 是 | 不適用 | 
| Dynamics 365 Commerce | 是 | 不適用 | 不適用 | 

> [!NOTE]
> 由於 RCS 的可用性因 Azure 地理位置 (geos) 而有不同，此服務的組態可能導致客戶資料傳輸到非屬 Dynamics 365 Online Service 選取的適用地理位置。 有關詳細資訊，請參閱[Dynamics 365 和 Power Platform：可用性、資料位置、語言和在地化](https://aka.ms/rcs/D365Productavailabilityguide)。