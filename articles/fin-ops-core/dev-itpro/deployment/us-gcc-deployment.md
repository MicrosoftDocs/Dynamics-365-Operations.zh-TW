---
title: 美國政府社群雲端 (GCC) 的 Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management
description: 本主題提供有關可供合格政府和私人實體使用的 Microsoft Dynamics 365 US Government 產品的資訊。
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 0c8b88e5d190f6dc9beb9342909d1e489d4af10b
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460588"
---
# <a name="dynamics-365-finance-and-dynamics-365-supply-chain-management-in-us-government-community-cloud-gcc"></a>美國政府社群雲端 (GCC) 的 Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]



選取 Microsoft Dynamics 365 美國 (US) 政府產品可供合格的政府和私人實體使用。 這些實體僅限於以下類型：

- 美國聯邦、州、地方、部落和地區政府實體
- 使用 Dynamics 365 US Government 向政府實體或雲端社群的合格成員提供解決方案的私人實體
- 擁有受政府法規約束的客戶資料的私人實體，Dynamics 365 US Government 是滿足法規要求的合適服務

如需相關資訊，請參閱[Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)。

## <a name="onboarding"></a>Onboarding

若要在 Microsoft Dynamics Lifecycle Services (LCS) 中完成實作專案的初始載入，請按照[上線實作專案](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md)中的說明進行動作。 但是，請勿使用這些說明中提供的公用 LCS 連結。 相反，請使用以下 URL 打開美國政府社群雲端 (GCC) 的 LCS：<https://gov.lcs.microsoftdynamics.us>。

初始入職完成後，按照[專案上線](../lifecycle-services/project-onboarding.md)中的說明進行動作。 再一次，使用[GCC 的 LCS](https://gov.lcs.microsoftdynamics.us)而不是公用 LCS。

## <a name="environment-deployment"></a>環境部屬

完成專案上線後，您可以查看[面向財務和營運應用程式客戶的 Lifecycle Services (LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md)中描述的 LCS 其他功能。 然後繼續進行環境部署。

- 若要透過 LCS 部署 Microsoft 託管的環境，請按照[面向財務和營運應用程式客戶的 Lifecycle Services (LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience)中的說明進行動作。
- 如需雲端託管環境，請參閱[部署和存取開發環境](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md)。 您還必須完成連接器的資源管理器上線流程，如[完成美國政府生 Lifecycle Services 專案的 Azure Resource Manager 上線流程](arm-onbarding-us-goverment.md)中所述。

> [!NOTE]
> 對於美國政府 LCS 專案，僅支援特定於 Azure Government 的 Azure 訂閱。

## <a name="features-that-arent-available"></a>無法提供的功能

某些功能無法在 GCC 中部署，或者它們無法與 GCC 中的 Dynamics 365 一起使用。 例如，Azure DevOps GCC 中將不提供服務。 但是，可使用內部 Azure DevOps 或公用 Azure DevOps 服務。 如需函數可用性的詳情，請參閱[商務應用程式美國政府函數可用性](https://aka.ms/BAPFunctionalParity)。

## <a name="frequently-asked-questions"></a>常見問題

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>是否在 GCC-High 中支援 Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management？

否。 僅在 GCC 中支援 Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management。

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>我可以在 GCC 中將公用 Azure DevOps 與 Finance 和 Supply Chain Management 一起使用嗎？

是的，如果您對透過聯邦風險和授權管理計劃 (FEDRAMP) 認證的解決方案沒有要求，則可以使用公用 Azure DevOps 服務。 或者，您可以使用 Azure DevOps 伺服器。

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>我可以在 Azure 商業訂閱上部署雲端託管環境 Tier-1 開發環境嗎？

否。 在[GCC 的 LCS](https://gov.lcs.microsoftdynamics.us)，您必須使用 Azure Government 訂閱來部署雲端託管環境。

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>如果我需要來自共用資源庫的套件，但它在 GCC 的 LCS 中無法使用，我該怎麼辦？

您可以從[公用 LCS](https://lcs.dynamics.com)的共用資源庫中下載相同的套件。 或者，您的合作夥伴可以幫助您下載軟件套件。

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>GCC 中是否提供代碼升級工具？

不，代碼升級工具目前在 GCC 中無法使用。 但是，您可以在[公用 LCS](https://lcs.dynamics.com)中建立潛在專案並使用代碼升級工具。 請注意，您將無法在潛在專案中部署環境。

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>我的合作夥伴可以代表我開具支援票證嗎？

是。 但是，如果您的合作夥伴使用非 GCC 身份，支援票證將被定向到公用支援佇列。 我們建議您使用 LCS 中的客戶 GCC 權利來打開支援票證。

## <a name="see-also"></a>另請參閱

- [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)
- [商務應用程式美國政府函數可用性](https://aka.ms/BAPFunctionalParity)。
- [Lifecycle Services (LCS) 使用者指南](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [雲端部署概述](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
