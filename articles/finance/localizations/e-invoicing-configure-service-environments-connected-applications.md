---
title: 設定服務環境和已連接的應用程式
description: 本主題說明如何設定服務環境和已連接的應用程式。
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c3366e75b4a6d3f33a1aac9e444236d9ae57c829
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451674"
---
# <a name="configure-service-environments-and-connected-applications"></a>設定服務環境和已連接的應用程式

[!include [banner](../includes/banner.md)]

本主題說明如何設定服務環境和已連接的應用程式。 此流程分為三個步驟。 步驟 1 是必要的，步驟 2 和步驟 3 是選擇性的。

## <a name="step-1-create-a-service-environment"></a>步驟 1：建立服務環境

建立服務環境時，定義可以向其部署全球化功能的使用者清單。 或者，對於某些情況，定義可以與電子發票服務通訊的外部應用程式清單。 如果您將在案例中使用編號規則，請進行設定。

要完成此步驟，請參閱[服務環境](e-invoicing-service-environments.md)。

## <a name="step-2-add-certificates-and-secrets"></a>步驟 2：新增憑證和秘密

新增參考 Microsoft Azure 金鑰保存庫和秘密，以便在您的方案中使用它們。 如果處理管道中的操作使用憑證和秘密進行數位簽署或與外部 Web 服務通訊，則此步驟是必需的。

要完成此步驟，請參閱[客戶憑證和秘密](e-invoicing-customer-certificates-secrets.md)。

## <a name="step-3-configure-connected-applications"></a>步驟 3：設定已連接的應用程式

要在 Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management應用程式與電子開票之間建立通訊，您必須設定 Finance 或 Supply Chain Management 以構建對電子開票服務的呼叫，並以可以轉換為所需電子格式的統一結構準備業務資料。 應用程式還必須正確處理來自服務的回應。 您可以直接在 Finance 或 Supply Chain Management 環境中完成此設定，也可以在 Regulatory Configuration Service (RCS) 中完成。 如果您在 RCS 中完成設定，則可以將其部署到您的 Finance 或 Supply Chain Management 環境中。 在此步驟中，您將註冊連接的應用程式以進行參數部署。

要完成此步驟，請參閱[已連接的應用程式](e-invoicing-connected-applications.md)。
