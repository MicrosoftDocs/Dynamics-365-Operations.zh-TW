---
title: 為財務和營運應用程式設定說明體驗
description: 本主題提供有關某些 Microsoft Dynamics 365 應用程式的說明系統組件的資訊。
author: margoc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bac06e258a96bb50bb6de7957e3e5ed07e966127
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460301"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>為財務和營運應用程式設定說明體驗

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

在本主題中，您將找到財務和營運應用程式說明系統組件的概述，例如 Microsoft Dynamics 365 Finance、Dynamics 365 Supply Chain Management、Dynamics 365 Commerce，和 Dynamics 365 Human Resources。 該主題還解釋了如何連線這些組件，並提供了建立自訂說明的過程摘要。

## <a name="help-architecture"></a>說明架構

財務和營運應用程式包括發佈到[Microsoft Dynamics 365 文件](/dynamics365/)網站的概念概述和其他主題。 然後可以從產品內的 **說明** 窗格中存取此內容。 下圖顯示了說明系統的各個部分。

[![說明架構。](./media/help-architecture.png)](./media/help-architecture.png)

產品內說明系統從 docs.microsoft.com 和其他連線的網站中提取文章。 它還引入了儲存在 Microsoft Dynamics Lifecycle Services (LCS) 中的業務流程建模器 (BPM) 中的工作指南。

## <a name="adding-task-guides"></a>新增工作指南

> [!NOTE]
> **工作指南** 索引標籤目前在 Human Resources 或 Commerce 中無法提供。 <!--We are currently working to enable this functionality in a future release.--> 但是，Human Resources 使用者入門體驗中的工作指南仍可用於涵蓋基本函數。 對於 Human Resources 和 Commerce，程式說明可在[Microsoft Dynamics 365 文件](/dynamics365/)網站。

在 **系統參數** 頁面，系統管理員可以設定對相關工作指南庫的存取以進行實作。

> [!NOTE]
> - 若要設定說明，您必須使用與部署應用程式的租戶在同一租使用者中的帳戶登入。
> - 無法從在本機虛擬硬碟 (VHD) 上執行的應用實體連線 LCS 庫。

[![帶有說明設定的系統參數表單。](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

若要為解決方案設定工作指南，請按照 **系統參數** 頁的步驟動作。

> [!IMPORTANT]
> 首次打開 **說明** 索引標籤時，您必須連線到 Lifecycle Services。 一定要選中表格中間的連結，等待連線，關閉對話方塊，然後選取 **確定** 前往 **系統參數** 頁。
>
> [![連線到 LCS](./media/connect-to-lcs-crop-1024x365.png "連線到 LCS。")](./media/connect-to-lcs-crop.png)

1. 選取要連線的 Lifecycle Services 專案。
2. 選取 BPM 庫 (在所選專案中) 以從中取出工作記錄。
3. 設定 BPM 庫的顯示順序。 顯示順序定義了庫中的工作記錄在 **說明** 窗格中的顯示順序。

完成這些步驟後，您可以打開 **說明** 窗格並選取 **工作指南** 索引標籤。 您現在將看到適用於您目前在財務和營運應用程式中的頁面的工作指南。 如果沒有找到工作指南，您可以輸入關鍵字來最佳化搜尋。

### <a name="showing-translated-task-guides"></a>顯示翻譯的工作指南

翻譯後的工作指南在 2016 年 5 月 APQC 統一庫和使用者入門庫中首次發佈。 若要查看本地化工作指南幫助，請確保您的 Dynamics 365 解決方案已連線到 2016 年 5 月庫。 使用者都可以透過更改 **選項**&gt;**偏好設定** 下的語言設定來更改工作指南顯示的語言。

> [!NOTE]
> 儘管已經翻譯了許多工作指南，但客戶端目前並未顯示翻譯後的工作指南名稱。 此外，在 2016 年 5 月的庫中，翻譯僅適用於 2016 年 2 月發佈的工作指南。 Microsoft 將發佈一個更新的庫，其中包括其他翻譯。
>
> - 如果工作指南已翻譯，當您打開該工作指南時，工作指南的所有文字都將以您選取的語言顯示。
> - 如果工作指南尚未翻譯，當您打開它時，只有部分文字 (控制項的文字) 會以您選取的語言顯示。

## <a name="adding-custom-help"></a>新增自訂說明

您可以使用工作指南建立自訂幫助，也可以將自訂說明網站連線到 **說明** 窗格。

### <a name="create-custom-help-by-using-task-guides"></a>使用工作指南建立自訂說明

您可以透過建立反映您的實作的工作記錄，然後將它們儲存到 LCS 中的業務流程庫，為受支援的應用程式建立自訂說明。 您不能為人力資源建立自訂工作指南。

如果您是合作夥伴，並且您將資料庫提升為公司資料庫並將其包含在解決方案中，那麼您的客戶將可以使用它。 您還可以製作 APQC 統一庫的副本，然後打開副本中的工作記錄，對其進行編輯並儲存您的更改。 如需相關資訊，請參閱[工作記錄器資源](../../dev-itpro/user-interface/task-recorder.md)。

### <a name="connect-a-custom-help-site"></a>連線自訂說明網站

財務和營運應用程式很少以其立即可用的形式使用。 相反，該解決方案可客製化和擴展以適應組織的需求。 您還可以自訂和擴展說明體驗。 例如，您可以將自訂幫助新增到產品內 **說明** 窗格中。

Microsoft 提供了一個工具箱來幫助您部署自訂說明並將其連線到 **說明** 窗格。 如需如何設定連線到 **說明** 窗格的自訂說明解決方案的相關資訊，請參閱[自訂說明概述](../../dev-itpro/help/custom-help-overview.md)。

如果您想與 Microsoft 就自訂說明的工具和流程進行合作，請填入以下表格：[https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback)。

## <a name="see-also"></a>另請參閱

[小幫手系統](help-overview.md)  
[自訂說明概述](../../dev-itpro/help/custom-help-overview.md)  
[工作記錄器資源](../../dev-itpro/user-interface/task-recorder.md)  
[使用工作記錄器建立檔案或訓練](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[自訂說明 GitHub 存放庫](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
