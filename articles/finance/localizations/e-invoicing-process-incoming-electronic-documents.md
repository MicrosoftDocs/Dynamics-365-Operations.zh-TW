---
title: 處理傳入的電子文件
description: 本主題概述了傳入電子文件的處理。
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9701367e1ba1f9dbd1e53deb863c10af4213a359
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451671"
---
# <a name="processing-of-incoming-electronic-documents"></a>處理傳入的電子文件

[!include [banner](../includes/banner.md)]

可以透過兩種方式匯入和處理傳入的電子文件，例如廠商電子發票：

- 文件從外部通道擷取，並直接傳遞到您連接的應用程式。 在那裡，它們將經過另外的轉換，然後匯入資料庫中。
- 文件在電子開票服務中進行預先處理，然後傳遞到您連接的應用程式。

電子開票支援兩種傳入文件的通道：電子郵件和 Microsoft SharePoint 資料夾。

有兩種設定類型來指定文件是經過預先處理還是直接傳遞到您連接的應用程式：

- **資料通道** – 系統會將文件直接傳遞給已連接的應用程式。
- **具有處理管道的資料通道** – 您可以設定將在文件傳遞到已連接的應用程式之前執行的其他動作。

有關如何為不同通道設定處理傳入電子文件的方案的資訊，請參閱[設定電子郵件通道](e-invoicing-configure-email.md)和[設定 SharePoint 通道](e-invoicing-configure-sharepoint-channel.md)。
