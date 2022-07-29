---
title: 設定電子開票功能的 Azure 資源
description: 本主題概述了為電子開票功能設定 Microsoft Azure 資源的流程。
author: dkalyuzh
ms.date: 01/26/2022
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
ms.openlocfilehash: cb1fcddce1054aebf9ef70ba69eb7aca98093cbe
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451695"
---
# <a name="set-up-azure-resources-for-electronic-invoicing"></a>設定電子開票功能的 Azure 資源

[!include [banner](../includes/banner.md)]

為電子開票功能設定 Microsoft Azure 資源的流程分為三個步驟。 前兩個步驟「在 Azure 入口網站中建立 Azure Key Vault」和「在 Azure 入口網站中建立 Azure 儲存體帳戶」是必須完成的步驟。 第三個步驟「設定 SharePoint 連線」是選擇性的步驟。

## <a name="create-an-azure-key-vault-in-the-azure-portal"></a>在 Azure 入口網站中建立 Azure Key Vault

在 Azure 訂閱中建立金鑰保存庫。 建議您為電子開票建立單獨的金鑰保存庫，並且不要將密碼與其他應用程式合併。 根據您在電子文件中的案例需要，建立所需數量的密碼和憑證。 您必須建立至少一個密碼來儲存您將在下一步中建立的 Azure 儲存體帳戶的共用存取簽章 (SAS) 權杖。

有關如何完成此步驟的資訊，請參閱[在 Azure 入口網站中建立 Azure 金鑰保存庫](e-invoicing-create-azure-key-vault-azure-portal.md)。

## <a name="create-an-azure-storage-account-in-the-azure-portal"></a>在 Azure 入口網站中建立 Azure 儲存體帳戶

您負責由電子開票服務產生或進入該服務的所有電子文件和檔案。 這些文件和檔案儲存在您在 Azure 訂閱中建立的 Azure 儲存體帳戶中。 該服務將使用從您的 Key Vault 密碼中取得的 SAS 權杖存取您的儲存體帳戶。

有關如何完成此步驟的資訊，請參閱[在 Azure 入口網站中建立 Azure 儲存體帳戶](e-invoicing-create-azure-storage-account-azure-portal.md)。

## <a name="configure-a-sharepoint-connection"></a>設定 SharePoint 連接

在某些情況下，您可能需要將電子文件儲存到 SharePoint 並從 SharePoint 中擷取它們。 為確保電子發票服務可以存取您的 SharePoint 資料夾，請設定 SharePoint 的存取權。

有關如何完成此步驟的資訊，請參閱[設定 SharePoint 連線](e-invoicing-create-sharepoint-connection.md)。
