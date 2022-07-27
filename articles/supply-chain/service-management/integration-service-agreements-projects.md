---
title: 服務合約與專案整合
description: 使用服務合約和服務合約明細時，您會使用專案管理和會計內設定的資料。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a43a8bab6a5e5ea527f4a062feea79b4313cb56f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449145"
---
# <a name="integration-for-service-agreements-and-projects"></a>服務合約與專案整合 

[!include [banner](../includes/banner.md)]


使用服務合約和服務合約明細時，您會使用 **專案管理和會計** 內下列區塊設定的資料。

## <a name="project-prices"></a>專案價格

服務合約交易的成本與銷售價格，來自於附加至此服務合約的專案所設定的成本價格。 成本與銷售價格可依據專案、員工和類別設定。 

## <a name="project-validation"></a>專案驗證

服務合約明細可選擇的專案、員工和類別，可在 **專案管理和會計** 內的驗證設定來予以限制。 使用驗證設定，即可結合員工、專案和類別來控制存取。 

## <a name="project-line-properties"></a>專案明細屬性

明細屬性會自動輸入服務合約明細。

明細屬性可在 **專案管理和會計** 的 **明細屬性** 表單內建立。 輸入服務合約的明細屬性會附加至該服務合約選擇之專案，之後服務合約明細會繼承。 

## <a name="default-offset-accounts"></a>預設沖銷帳戶

若輸入費用交易，則該交易會自動選擇預設費用沖銷帳戶。 附加至目前服務合約的專案會設定預設費用帳戶。

## <a name="project-categories"></a>專案類別

服務合約明細可用的類別，可於 **專案管理和會計** 的 **專案類別** 表單內設定。 

> [!NOTE]
> <P>若類別的<STRONG>專案類別</STRONG>表單的<STRONG>專案</STRONG>索引標籤已選擇<STRONG>日記帳內有效</STRONG>核取方塊，則可供選擇。 然而，若<STRONG>專案管理和會計參數</STRONG>表單的<STRONG>日記帳</STRONG>索引標籤已選擇<STRONG>非有效類別</STRONG>核取方塊，則所有類別皆可供選擇。</P>

## <a name="project-parameters"></a>專案參數

若 **專案管理和會計參數** 表單的 **日記帳** 索引標籤選擇 **被解僱工作者** 欄位，則 **服務合約** 和 **服務訂單** 表單可選擇非在職員工與在職員工。

此外，**服務訂單** 表單的 **專案** 索引標籤可啟用 **開始時間** 與 **結束時間** 欄位，以在服務訂單明細中輸入開始與結束時間。

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>啟用服務訂單的開始和結束時間功能

1.  按一下 **專案管理和會計** \> **設定** \> **專案管理和會計參數**。

2.  按一下 **日記帳** 索引標籤，然後選擇 **顯示開始/結束時間** 核取方塊。

3.  按一下 **專案管理和會計** \> **設定** \> **日記帳** \> **日記帳名稱**。

4.  選擇附加到服務訂單的日記帳名稱。

5.  按一下 **一般** 索引標籤，然後選擇 **顯示開始/結束時間** 核取方塊。


> [!NOTE]
> <P>為該服務訂單選擇日記帳名稱，位置在<STRONG>服務管理參數</STRONG>表單<STRONG>日記帳</STRONG>索引標籤的<STRONG>時數</STRONG>欄位。</P>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]