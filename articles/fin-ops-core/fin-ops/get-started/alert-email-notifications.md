---
title: 透過電子郵件通知用戶端警示
description: 本主題提供有關如何設定傳送電子郵件通知預定義事件發生的規則的資訊。
author: RichdiMSFT
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 4e2205ba3bdf5ec2a4e6d9390007eaf1098293c3dd2a5b2ff1b3c73c7de5a83f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460156"
---
# <a name="client-alert-notifications-by-email"></a>透過電子郵件通知用戶端警示

[!include [banner](../includes/banner.md)]

您可以定義自訂警示規則來監控篩選的資料檢視，並在發生預定義事件時自動傳送電子郵件通知。 傳送電子郵件通知的選項適用於所有已支援的警示類型，您還可以在現有警示規則下打開它們。

您可以使用內建控制項建立可監控系統批次作業的篩選檢視的警示規則。 透過監控 **狀態** 欄位的值，您還可以設定在批次作業失敗時傳送電子郵件的警示規則。 建立這些警示規則後，您不再需要檢查報告以了解業務資料的更改。 相反，您可以讓智慧型變更偵測服務為您監控。

用戶端警示依賴於透過與 Microsoft Office 整合所提供的電子郵件子系統。 我們建議您使用簡單郵件傳輸通訊協定 (SMTP) 提供者，以便電子郵件傳送不必依賴本地郵件用戶端。

若要透過電子郵件發送通知，客戶必須設定整合的電子郵件服務。 電子郵件通知代表警示擁有者傳送給收件者。

如需如何設定電子郵件的相關資訊，請參閱[設定和寄送電子郵件 ](../organization-administration/configure-email.md)。

下圖顯示了 **建立警示規則** 對話方塊，現在包括一個 **寄送電子郵件** 選項。

[![建立警示規則對話方塊，其中寄送電子郵件選項已設定為是。](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> 當 **寄送電子郵件** 選項已設定為 **是** 的時候，警示通知將繼續從操作中心傳送。

## <a name="alert-notification-email-templates"></a>警示通知電子郵件範本

該服務使用提供警示通知基本詳情的預定義電子郵件範本發送電子郵件通知。

下圖顯示了透過電子郵件收到警示通知時的結構。

[![用於記錄建立、欄位更改和範本刪除的範本型警示通知。](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]