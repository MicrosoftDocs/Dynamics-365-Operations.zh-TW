---
title: 範本 BOM
description: 範本物料清單 (BOM) 能為定期維護的服務對象提供標準化的元件清單。
author: kamaybac
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d34502d74590595f26ba5aae78158ed893a095df
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448401"
---
# <a name="template-boms"></a>範本 BOM

[!include [banner](../includes/banner.md)]

範本物料清單 (BOM) 能為定期維護的服務對象提供標準化的元件清單。 範本 BOM 中列出的元件代表服務物件的各個子元件。 透過將範本 BOM 應用於服務物件，您可以記錄已在服務物件上替換的子元件。

若要將範本 BOM 應用於服務協議或服務訂單，請將其附加到服務物件關係。

> [!NOTE]
> 您只能將一個範本 BOM 應用於服務物件。

## <a name="create-a-template-bom"></a>建立範本 BOM

下方資料表中包含可用於建立範本 BOM 的各種方法資訊。

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>方法</p></th>
<th><p>描述</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>生產</p></td>
<td><p>範本 BOM 以生產訂單為基礎。 只有當您在生產環境中作業時，此選項才適用。 這麼做的好處是您能擁有品項構成元件的最新詳細清單。</p></td>
</tr>
<tr class="even">
<td><p>項目 BOM</p></td>
<td><p>以項目 BOM 為基礎建立的範本 BOM。 與生產 BOM 不同，品項 BOM 是構成品項元件的靜態清單。</p></td>
</tr>
<tr class="odd">
<td><p>現存範本</p></td>
<td><p>以現存範本 BOM 為基礎建立的範本。</p></td>
</tr>
<tr class="even">
<td><p>手動</p></td>
<td><p>如果您知道服務物件上通常會更換哪些備件，則可以手動建立範本 BOM。 此方法有助於確保範本中包含的元件，反映您工作場所的實際要求。</p></td>
</tr>
</tbody>
</table>

## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a>將範本 BOM 應用於服務合約或服務訂單

您可以將範本 BOM 應用於服務合約、服務訂單或同時應用於兩者。 服務合約通常涵蓋與客戶的長期關係。 記錄在服務 BOM 中的更換紀錄是服務合約的實用資料。

您也可以將範本 BOM 應用於服務訂單，以記錄已在服務物件上執行服務的紀錄。

## <a name="copy-the-history-of-a-service-bom"></a>複製服務 BOM 的紀錄

您可以將服務 BOM 行的記錄從一個服務合約複製到另一個服務合約。 透過複製服務合約之間的服務紀錄，您可以保留品項的更換記錄。

### <a name="example"></a>範例

您已為客戶的汽車簽訂了一份為期三年的服務合約。 在此期間，客戶會習慣公司提供的優質服務。 因此，在合約到期後，客戶會想要設定一份新的合約。 現在，您可以為公司協商更有利的合約。 因為替換元件的記錄在將來可能有用，所以您可以將服務 BOM 的記錄複製到新合約中。

## <a name="modify-the-template-bom"></a>修改範本 BOM

如果範本 BOM 尚未附加至服務物件，您可以修改或刪除其中的行。 將範本 BOM 附加到服務物件後，您只能修改 BOM 的本地版本。 如果要複製範本 BOM 的本地版本設定，則可以根據本地版本建立新的範本 BOM。 更多詳細資訊，請參閱[修改服務 BOM](modify-service-bom.md)。

如果您替換 BOM 中的品項，則可以在 BOM 設計工具的 BOM 行上註冊替換。 或者，您可以為替換物件建立服務訂單行。 如果您建立服務訂單行，您可以開立替換品項。 如果您沒有為更換建立服務訂單行，則會保留更換註冊以追蹤服務物件的記錄。

## <a name="change-how-information-on-the-bom-line-is-displayed"></a>變更 BOM 行資訊的顯示方式

您可以更改所有範本和服務 BOM 的 BOM 行資訊的顯示方式。 變更將應用於所有範本 BOM 和服務 BOM。 其中包括附加到服務物件的內容。

## <a name="set-up-number-sequences-for-template-boms"></a>設定範本 BOM 的數字序列

若要使用範本 BOM，您必須設定兩個編號序列。 為範本 BOM 設定一個編號序列，為 BOM 紀錄行編號設定一個編號序列。

> [!NOTE]
> 編號序列用於將標識符分配給需要它們的記錄。 在您可以將編號序列分配給範本 BOM 或 BOM 紀錄行編號之前，您必須設定編號序列代碼。

## <a name="set-up-number-sequences"></a>設定編號序列

1. 在 **編號序列** 列表頁面，為範本 BOM 和 BOM 紀錄行編號建立編號序列。
1. 選取 **服務管理** \> **設定** \> **服務管理參數**。
1. 選擇 **編號序列**，然後為您在 **編號序列** 表單中建立的編號序列引用選擇一個編號規則代碼。
1. 關閉表單以儲存變更。

> [!NOTE]
> 系統使用 BOM 紀錄行編號將 BOM 紀錄中的事務與服務合約或服務訂單相關聯。 此號碼不會顯示在使用者界面中。

## <a name="see-also"></a>另請參閱

[建立範本 BOM](create-template-bom.md)

[管理物件關係的範本 BOM](manage-template-boms-on-object-relations.md)

[修改服務 BOM](modify-service-bom.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
