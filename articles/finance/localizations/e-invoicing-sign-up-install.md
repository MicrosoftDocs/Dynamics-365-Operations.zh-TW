---
title: 註冊並安裝電子發票服務
description: 本主題提供有關如何註冊和安裝電子發票服務的資訊。
author: dkalyuzh
ms.date: 02/07/2022
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
ms.openlocfilehash: 4ab16652e4a50dd71a5d0b2b49b4dd79e327f7a8
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451689"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>註冊並安裝電子發票服務

[!include [banner](../includes/banner.md)]

本主題提供有關如何註冊和安裝電子發票服務的資訊。 這個程序有四個步驟。 步驟 1 到 3 是必需的，步驟 4 是可選的。

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>第 1 步：註冊 Regulatory Configuration Service

Regulatory Configuration Service (RCS) 提供用於設定電子發票的設定和設計體驗。 在 RCS 中建立、維護和管理環境和電子發票功能等資源。 資源準備就緒後，將會發佈到電子發票服務。

如需更多關於 RCS 的資訊，請參閱 [Regulatory Configuration Services (RCS)](rcs-globalization-feature.md)

若要註冊 RCS，請前往 [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) 頁面。

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>步驟 2：在 Microsoft Dynamics Lifecycle Services 中安裝微服務增益集

電子發票服務是一組託管在 Microsoft 資料中心中的微服務。 預設情況下，Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management 的客戶無權存取電子發票服務。 您必須將其作為增益集安裝在 Microsoft Dynamics Lifecycle Services (LCS) 中。 安裝增益集時，您的 Finance 或 Supply Chain Management 環境將在允許連接到電子發票服務的應用程式的註冊表中註冊。

若要完成此步驟，請參閱[在 Lifecycle Services 中安裝微服務增益集](e-invoicing-install-add-in-microservices-lcs.md)。

### <a name="step-3-set-up-rcs"></a>第 3 步：設定 RCS

您必須設定 RCS 和電子發票服務之間的整合。 您也必須設定主要元件。

要完成此步驟，請參閱[設定 Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md)。

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>第 4 步：Microsoft Power Platform 外掛程式管理參考

某些方案需要在 Microsoft Power Platform 範圍內與 Dataverse 整合。

目前，如果您將電子發票解決方案用於印尼電子發票方案，則此設定是強制性的。 但是，對於沙烏地阿拉伯電子發票方案，這是可選的。 如需更多詳細資訊，請參閱[按國家/地區劃分的電子發票功能可用性](e-invoicing-country-specific-availability.md)。

若要完成此步驟，請參閱 [Microsoft Power Platform 插件管理員參考資料](e-invoicing-power-platform-plug-in.md)
