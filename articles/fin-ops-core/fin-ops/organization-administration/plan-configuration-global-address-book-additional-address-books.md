---
title: 規劃全球通訊錄和其他通訊錄
description: 本主題描述了您在規劃過程中必須做出的注意事項和決策。
author: msftbrking
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87b3f6a74c217b0cc7cec784ca6a964ab2caae0c7e9438aee2cc82987a508d63
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460155"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>規劃全球通訊錄和其他通訊錄

[!include [banner](../includes/banner.md)]

本主題介紹在設定和設定全球通訊錄和任何其他通訊錄之前，您必須在規劃過程中做出的注意事項和決策。 某些決策將要求您確認已針對產品的其他領域做出的決策，例如組織階層。

## <a name="global-address-book"></a>全球通訊錄

在開始使用全球通訊錄之前，您必須確定它的預設值。 然後，這些預設值將用於您建立的任何其他通訊錄。

**決策**

- 對於 **人員** 類型的參與方記錄，姓名應按什麼順序顯示？ 例如，一個序列是姓氏、中間名、名字。
- 刪除角色記錄時是否應該從通訊錄中刪除參與方記錄？ 例如，如果刪除了客戶記錄，是否也應該刪除參與方記錄？
- 建立新記錄時，如果在全球通訊錄中發現重複記錄，是否應該通知使用者？
- 資料通用編號系統 (DUNS) 編號是否應包含在參與方記錄的資訊中？
- 如果 DUNS 編號包含在一方記錄中，是否應該檢查該編號的唯一性？
- 在全球通訊錄中建立參與方記錄時，您是否需要預設的參與方類型、人員或組織？
- 哪些使用者角色應該有權存取參與方記錄的私人地址和聯絡資訊？

## <a name="additional-address-books"></a>其他通訊錄

建立全球通訊錄後，您可以根據需要建立其他通訊錄，例如為組織中的每個公司或每個企業營運建立單獨的通訊錄。 例如，Fabrikam 是一個擁有多家公司和多條企業營運的國際組織。 Fabrikam 計劃為每個企業營運建立一個通訊錄。 對於發生在多個地點的企業營運，例如氣動工具業務，Fabrikam 計劃為每個地點建立一個通訊錄。 Fabrikam 的 IT 經理 Chris 建立了以下所需的通訊錄清單。 此清單還描述了每個通訊錄必須包含的參與方記錄。

- **公共部門合約 (PubSC)**– 參與 Fabrikam 持有公共部門合約之所有各方的記錄。
- **私人部門合約 (PriSC)**– 參與 Fabrikam 持有私人部門合約之所有各方的記錄。
- **電子工具 (ET)**– 參與購買或銷售電子工具的各方記錄，或以其他方式與 Fabrikam-Japan 公司的 Fabrikam 提供或購買的電子工具互動的各方記錄。
- **氣動工具 (PTJPN)**– 參與購買或銷售氣動工具的各方記錄，或以其他方式與 Fabrikam-Japan 公司的 Fabrikam 提供或購買的氣動工具互動的各方記錄。
- **氣動工具 (PTUSA)**– 參與購買或銷售氣動工具的各方記錄，或以其他方式與 Fabrikam-US 公司的 Fabrikam 提供或購買的氣動工具互動的各方記錄。

**決策。**

- 您將建立多少個額外的通訊錄？


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]