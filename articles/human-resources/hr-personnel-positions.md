---
title: 職位
description: 本主題說明職位可以納入的概念元素。 它也提供範例，顯示貴組織內部如何使用這些元素。
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: anbichse
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 269054
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 95abd7548d23ef1b4f5fc31ebaa818e06e179d60
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452487"
---
# <a name="positions"></a>職位


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明職位可以納入的概念元素。 它也提供範例，顯示貴組織內部如何使用這些元素。

建立職位前必須先設定工作。 一些職位細節，例如薪酬區域、背景工作角色指派、職位持續期間和回報關係，須依照日期生效。

## <a name="general-information"></a>一般資訊

建立職位時，您必須選取工作。 下列資訊將自動從您選取的工作填寫：

- 描述
- 標題
- 全職等效項目
- 職系

職銜用來指稱員工的頭銜。 (員工不使用列出的頭銜。) 因此，職銜應該盡可能標準化。

> [!NOTE]
> 背景工作角色無法在可指派日期前，指派到某個職位。
>
> **人力資源共用參數** 頁面中，**職位** 索引標籤上的參考用來控制背景工作角色的指派行為。 選取下列其中一個值：
>
> - **始終** – 您可以在建立職位時指派背景工作角色給新職位。 建立職位時，**職位** 頁面，**一般** 索引標籤上的 **開放指派** 日期和時間會自動設定為建立日期和時間。
> - **絕不** – 您無法在建立職位時指派背景工作角色給新職位。 如果您選取本選項，您必須在有職缺時，打開每個新職位的 **職位** 頁面。 接著在 **一般** 索引標籤上輸入 **開放指派** 日期，啟用背景工作角色指派功能。 如果您選取此選項，當您試著指派背景工作角色時，指派日期預設值將設定為 **絕不**。

## <a name="position-duration"></a>職位持續期間

每份職位都有特定的有效時段，簡稱為持續期間。 例如，暑期職位的持續期間可能是 2021 年五月 1 日到 2021 年八月 31 日。 啟動日期是系統中，該職位有效的日期。 退休日期是系統中，該職位不再有效的日期。

須注意的是，可指派日期或背景工作角色指派日期都不能在啟動日期之前。 必須達到啟動日期後，職位才視同有效。 此外，背景工作角色指派不能超過職位的退休日期。

## <a name="reports-to-position"></a>主管職位

職位是組織階層架構中，較低等級的重要元素。 您可以在 **職位** 頁面上指明職位回報的職位。 當您指派背景工作角色到另一個主管職位時，等於您在被指派到這兩份職位的背景工作角色之間建立回報關係。 例如，000220 號職位向 000300 號職位回報。 Kim Akers 指派到 000220 號職位，而 Sanjay Patel 指派到 000300 號職位。 因此，Kim Akers 向 Sanjay Patel 回報。

> [!TIP]
> 主管職位會在整套系統中用來判定員工的經理身份。 前例中，如果系統中經理角色是指派給 Sanjay Patel，他在 Manager Self-Service 中會將 Kim Akers 視為下屬。 當您建立工作流程路由規則和核對清單任務時，也會使用回報關係。

## <a name="relationships"></a>關聯

如果貴組織使用矩陣階層架構或另一個自訂階層架構，您可以設定職位階層架構類型。 接著，您可以新增回報關係到您設定每個階層架構類型的職位。 例如，Lori Penor 是 Adventure Works 的總經理，被指派到 **總經理** 職位。 Lori 管理用來清理小程式的產品開發。 她需要一名會計師來幫助她處理財務問題。 因此，她已經招募 Kim Akers 擔任她的會計師。 Kim 直接回報 Sanjay Patel，但她也和 Lori Penor 一起處理小程式清理器開發的財務相關工作。

以前例而言，您必須完成下列任務才能設定 Kim Akers 和 Lori Penor 之間的工作關係：

1. 建立一個名為 **小程式** 的自訂職位階層架構類型就等於建立一個包括負責處理小程式清理產品職位的階層架構。
2. 在 **Widget** 階層架構中指明 **總經理** 職位為 Kim 要回報的職位。
3. 使用職位階層架構檢視職位的回報架構。 如果您有多個職位階層架構，您可以檢視職位階層架構中，每種類型的階層架構。 您也可以按照職位識別碼或指派給該職位的背景工作角色姓名搜尋職位。 職位階層架構是組織階層架構。

## <a name="labor-union"></a>工會

您可以記錄此職位是否需要工會協議，以及使用哪個工會。 您也可以產生協議與法人實體的關聯性。

## <a name="financial-dimensions"></a>財務維度

當您建立職位財務維度時，必須指明法人實體。 您可以個別為每個維度選取預設維度。 或者，您可以選取分佈範本，自動填寫預設維度。 分佈範本也提供橫跨多個維度值分配數額的選項。
