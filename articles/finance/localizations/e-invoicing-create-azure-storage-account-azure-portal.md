---
title: 在 Azure 入口網站中建立 Azure 儲存體帳戶
description: 本主題說明如何為電子開票建立 Azure 儲存體帳戶。
author: dkalyuzh
ms.date: 02/14/2022
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
ms.openlocfilehash: 3d9647e234b3603ef6305ec6031a793b744bbe98
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451710"
---
# <a name="create-an-azure-storage-account-in-the-azure-portal"></a>在 Azure 入口網站中建立 Azure 儲存體帳戶

[!include [banner](../includes/banner.md)]

由電子開票服務產生或在處理過程中轉到該服務的所有電子文件都儲存在您的 Microsoft Azure 儲存體帳戶容器中。 為確保電子開票可以存取這些容器，您必須向電子開票服務提供儲存體帳戶的共用存取簽名 (SAS) 權杖。 此外，為確保安全儲存權杖，請勿直接提供 SAS 權杖。 而是將其儲存在 Azure Key Vault 中，並提供 Azure Key Vault 秘密。

1. 打開您計劃用於電子開票服務的儲存體帳戶。
2. 前往 **設定** \> **設定**，並確保 **允許 Blob 公用存取** 參數設定為 **啟用**。
3. 前往 **資料儲存體** \> **容器**，並建立一個容器。
4. 輸入容器的名稱，然後將 **公用存取級別** 欄位設定為 **私人 (無匿名存取)**。
5. 打開新容器，然後前往 **設定** \> **存取原則**。
6. 選擇 **新增原則** 以新增儲存的存取原則。
7. 視情況設定 **識別碼**。
8. 在 **權限** 欄位，選擇所有權限。

    ![在「新增原則」對話方塊的「權限」欄位中選擇的所有權限。](media/e-invoicing-azure-1.png)

9. 輸入開始日期和結束日期。 結束日期應該是將來的日期。
10. 選擇 **確定** 以儲存原則，然後將變更儲存到容器。
11. 前往 **設定** \> **共用存取權杖**，並設定欄位值。
12. 輸入開始日期和結束日期。 結束日期應該是將來的日期。
13. 在 **權限** 欄位，選擇以下權限：

    - 讀取
    - 新增
    - 建立
    - 撰寫
    - 刪除
    - 清單

14. 選擇 **產生 SAS 權杖和 URL**。
15. 複製並儲存 **Blob SAS URL** 欄位中的值。 此值將稍後在此流程中使用，並將稱為 *共用存取簽章 URI*。
16. 打開您打算用於電子開票的金鑰保存庫。
17. 前往 **設定** \> **秘密**，然後選擇 **產生/匯入** 以建立秘密。
18. 在 **建立密碼** 頁面的 **上傳選項** 欄位，選擇 **手動**。
19. 輸入秘密名稱。 此名稱將在 Regulatory Configuration Service (RCS) 中的服務設定期間使用，將稱為 *金鑰保存庫秘密名稱*。 有關如何設定 RCS 的詳細資訊，請參閱[設定 Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md)。
20. 在 **值** 欄位，輸入您之前複製的共用存取簽章 URI。
21. 選取 **建立**。
