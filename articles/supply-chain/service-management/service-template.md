---
title: 服務範本
description: 您可以將某個服務合約定義為範本，然後將範本的行複製到另一個服務合約或服務訂單中。
author: kamaybac
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82a19dbee91f13eb3ef56dfd67a775930170b8e7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448893"
---
# <a name="service-templates"></a>服務範本

[!include [banner](../includes/banner.md)]

您可以將某個服務合約定義為範本，然後將範本的行複製到另一個服務合約或服務訂單中。

## <a name="example"></a>範例

您為其提供服務的客戶在五個不同的地點具有完全相同的服務電梯。

您想為客戶設定五份服務合約，每個站點一份。
為減少重複性的設定工作，並確保服務合約中的設定資訊完全相同，您建立服務合約並將其指定為電梯服務工作的範本。

您現在可以將範本行複製到五個新的服務合約中，以便每個服務合約都填入範本中的行。

## <a name="create-a-template"></a>建立範本

建立服務範本時，建立服務合約，在其上建立所需的行，然後將服務合約附加到服務範本群組。

> [!NOTE]
> 只有當服務合約沒有附加服務訂單時，才能將服務合約定義為範本。 此外，不能從定義為範本的服務合約產生服務訂單。

## <a name="copy-template-lines"></a>複製範本行

您可以將服務範本的範本行複製到另一個服務合約或服務訂單中。

將範本行複製到服務訂單或服務合約中時，範本群組將顯示在樹狀檢視表中，檢視表中的每個群組都展開。 此顯示方式可讓您查看每個範本和範本行。

如果您已根據反映範本用途的名稱將範本分組，則可以更容易確定要複製哪些服務範本行。

## <a name="related-topics"></a>相關主題

[複製服務範本行](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]