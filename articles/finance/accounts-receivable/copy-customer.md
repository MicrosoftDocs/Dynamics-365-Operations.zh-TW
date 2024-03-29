---
title: 使用共用數序來複製客戶
description: 本文章說明如何使用共用數序將客戶複製到另一個法律實體，但保留相同的客戶識別碼。
author: abruer
ms.date: 08/31/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 54639356007198f256f0d80fce9bfa2013f7b2b7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899977"
---
# <a name="copy-customers-by-using-shared-number-sequences"></a>使用共用數序來複製客戶

[!include [banner](../includes/banner.md)]

您可以使用共用數序來指派客戶識別碼。 共用數序還允許您將客戶從一個法律值體複製到另一個法律實體，但在兩個法律實體中使用相同的客戶識別碼。

## <a name="setup"></a>設定

該功能會在您使用共用數序指派客戶識別碼時啟動。 您必須在要複製客戶的每個法律實體中使用相同的數序。 您在每個法律實體的 **應收帳款參數** 頁面上更改客戶數序。 選擇 **應收帳款** \> **參數**，然後選擇 **數序** 索引標籤。

您還可以為每個客戶群組設定客戶數序。 這些數序也必須共用。 首先使用客戶群組的數序。 如果沒有為客戶群組指定數序，則會使用 **應收帳款參數** 頁面上指定的數序。

如果您使用手動客戶識別碼，您還可以在法律實體之間複製客戶。 但是，如果您嘗試將客戶複製到客戶識別碼已存在的法律實體，則不會啟動複製程序。

## <a name="copy-a-customer"></a>複製客戶

要複製客戶，請選擇 **所有客戶** 清單頁面上的 **新增** 以打開 **建立客戶** 對話方塊。 請注意，不會立即指派新客戶識別碼。 此行為與先前版本中的行為不同。 由於您尚未選擇客戶群組，系統無法確定要使用的正確數序。 此外，它無法確定您是試圖建立新客戶還是複製客戶。 因此，在您選擇對話方塊底部的 **儲存** 之前不會指派客戶識別碼。

如果您正在建立一個新客戶，您可以繼續像往常一樣填寫所有欄位。 完成後，選擇 **儲存**，您將看到已自動指派客戶識別碼。 或者，對於手動數序，您將看到已使用您的手動客戶識別碼。

要複製客戶，在 **名稱** 欄位中，輸入一個或多個代表您正在尋找的客戶的字元。 搜尋對話方塊會顯示可能代表您正在尋找之客戶各方的清單。 當您選擇其中一方時，對話方塊右側會顯示附加資訊：

- **一般** 索引標籤會顯示該方的電話號碼和地址。
- **角色** 索引標籤會顯示所選方可以擁有的角色以及它擁有每個角色的法律實體。
- **稅務登記識別號** 索引標籤會顯示指派至該方的稅務登記識別碼。

僅當一方具有客戶角色並且在非目前法律實體的法律實體中具有該角色時，您才能複製該方。 當您找到符合這些條件的一方時，請執行以下步驟。

1. 出現 **複製客戶** 選項。 預設情況下，此選項設定為 **否**。 要將客戶複製到目前法律實體，請將選項設定為 **是**。 
2. 出現 **法律實體** 欄位。 選擇要從中複製客戶的法律實體。 如果客戶僅存在於一個法律實體中，則該欄位預設會設定為該法律實體。
3. 選取 **選取**。 新客戶建立完成。

## <a name="validation"></a>驗證

當您複製客戶時，系統會嘗試儲存新的客戶資訊。 系統會執行驗證以確認複製的資料是否正確。 對於每個失敗的驗證，您都會收到一則錯誤訊息。 錯誤訊息解釋必須更新哪些資訊。 在您修正所有驗證錯誤之前，無法儲存客戶的複製作業。

## <a name="copy-a-customer-by-using-tax-exempt-number-search-feature"></a>使用免稅編號搜尋功能來複製客戶

您也可以使用免稅編號搜尋功能來複製客戶，該功能位於 **所有客戶** 頁面的動作窗格上的 **客戶** 索引標籤上的 **註冊** 頁面。 出現的 **免稅編號搜尋** 對話方塊會顯示免稅編號、客戶識別碼、客戶名稱和使用免稅識別碼的法律實體。 唯當客戶位於非目前法律實體的法律實體中時，您才能複製該客戶。 選擇符合此條件的客戶後，請執行以下步驟。

1. 出現 **複製客戶** 選項。 預設情況下，此選項設定為 **否**。 要將客戶複製到目前法律實體，請將選項設定為 **是**。 
2. 選取 **選取**。 新客戶建立完成。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
