---
title: 廠商要求設定
description: 本主題說明需要在新廠商要求中填入的欄位。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 1d34a9974da41b7abb40bb2cf046a15432c249eb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448293"
---
# <a name="vendor-request-configurations"></a>廠商要求設定
[!include [banner](../includes/banner.md)]

若要完成廠商要求，廠商連絡人必須完成潛在廠商註冊精靈。

在 **廠商要求設定** 表單中可以建立設定檔，以在潛在廠商註冊精靈中指定必填欄位和可見欄位。

廠商註冊精靈將先詢問潛在廠商使用者廠商在哪個國家/地區開展業務。 此資訊決定適用的設定。 如果沒有為某個國家/地區定義特定設定，則將使用預設設定。

### <a name="set-up-a-vendor-request-configuration"></a>設定廠商要求設定

根據預設，廠商要求設定表單中提供了廠商設定。

無法為預設設定選擇國家/地區，因此 **國家/地區** 區段無法變更。

1. 按一下 **採購和資源開發** > **設定** > **廠商**，然後按一下 **廠商要求設定**。
2. 按一下 **欄位** 索引標籤以設定所列欄位的狀態。
3. 隱藏 (不可見)
4. 顯示 (可見但非必填)
5. 必填 (可見且必填)
6. 按一下 **內容** 索引標籤以指定是否要在精靈上顯示文字，以及是否應確認潛在廠商使用者必須接受此內容，然後才能進入精靈的下一步。 對於使用者必須接受才能繼續的任何條款和條件，都將要求確認。

您還可以輸入要在精靈完成時顯示的確認訊息，且可以新增一個或多個問卷。

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>為特定國家/地區建立廠商設定
1.  按一下 **採購和資源開發** > **設定** > **廠商**，然後按一下 **廠商要求設定**。
2.  按一下 **新增** 建立新設定，並為設定命名。
3.  按一下 **儲存**。
4.  打開 **國家/地區** 索引標籤以選擇要套用設定的國家/地區。
5.  按照預設設定的指南完成設定。



[!INCLUDE[footer-include](../../includes/footer-banner.md)]