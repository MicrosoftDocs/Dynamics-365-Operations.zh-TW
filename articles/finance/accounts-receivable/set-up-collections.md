---
title: 設定收帳
description: 本文介紹如何設定收帳功能。
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustCollectionsActivitiesListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 14031
ms.assetid: dcc6da2f-9af5-4f1d-abaa-b72967b66979
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f2e06da265271e2148804c51abc7cd9ffc29a3e20e73dda3a1a23966f0e6586e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450747"
---
# <a name="set-up-collections"></a>設定收帳

[!include [banner](../includes/banner.md)]

本文介紹如何設定收帳功能。 使用收帳功能時，必須完成一些設定步驟。 還有一些選擇性功能，包括客戶群和收帳團隊。 

- 帳齡期間定義
- 帳齡快照
- 日記帳名稱
- 沖銷交易的原因代碼
- 收帳代理人
- 沖銷帳戶
- NSF (資金不足) 資料
- 使用 **收帳** 頁面之使用者的 Outlook 設定
- 電子郵件地址

在本主題的其餘部分，將更詳細地討論這些要點。 

## <a name="set-up-aging-period-definitions"></a>設定帳齡期間定義

設定帳齡期間定義。 帳齡期間定義用於定義在 **帳齡餘額**、**收帳活動** 和 **收帳案例** 清單頁面上顯示的列。 它還定義在 **收帳** 頁上顯示的期間。 如果已設定客戶群，使用群的帳齡期間定義。 如果未設定群，則使用在 **應收帳款參數** 頁面中指定的預設帳齡期間定義。 如果未指定預設帳齡期間定義，則在 **帳齡期間定義** 頁面中使用第一個帳齡期間定義。

## <a name="create-an-aging-snapshot"></a>建立帳齡快照
為所有客戶或客戶群中的客戶建立帳齡快照記錄。 帳齡快照資料顯示在 **帳齡餘額** 清單頁面和 **收帳** 頁面上。 您必須先建立一個帳齡快照，然後才能使用清單頁面。 清單頁面僅顯示已建立帳齡快照的客戶資料。

## <a name="optional-set-up-customer-pools"></a>選擇性：客戶群
您可以設定客戶群來代表客戶群組。 您可以使用客戶群作為篩選條件，用來顯示 **收帳** 清單頁面、**收帳** 頁面的客戶資料，或者，當您建立帳齡快照時。

## <a name="optional-create-a-collections-team"></a>選擇性：建立收帳團隊
如果您組織的多名人員執行收帳工作，您可以建立收帳團隊。 您可以在 **應收帳款參數** 頁面中選擇團隊。 如果您沒有建立收帳團隊，當您在 **收帳代理人** 頁面中設定收帳代理人時，將自動建立一個團隊。

## <a name="set-up-a-collections-case-category"></a>設定收帳案例類別
若要使用案例安排您的收帳工作，請設定具有 **收帳** 類別類型的案例類別。 只有當您要在 **收帳** 頁面中使用案例功能時，才需要執行。

## <a name="set-up-journal-names-settlement-writeoff-and-nsf"></a>設定日記帳名稱 (結算、沖銷和 NSF)
設定在 **收帳** 頁面中處理交易時使用的日記帳名稱。 此處理包括結算交易、沖銷交易和處理資金不足(NSF) 付款。

| 描述 | 日記帳類型     |
|-------------|------------------|
| 結算  | 客戶付款 |
| 沖銷   | 每日            |
| NSF         | 客戶付款 |

## <a name="set-up-a-reason-code-for-writeoff-transactions"></a>設定沖銷交易的原因代碼
在 **收帳** 頁面上設定在沖銷交易時使用的預設值原因代碼。 您可以在沖銷流程中更改代碼。

## <a name="set-up-a-folder-for-email-attachments-and-create-email-templates"></a>設定電子郵件附件的資料夾和建立電子郵件範本
如果您從 **收帳** 頁面發送具有 Microsoft Excel 附件的電子郵件，您可以為這些訊息建立選擇性的電子郵件範本。

## <a name="set-up-accounts-receivable-parameters-for-collections"></a>設定收帳的應收帳款參數
設定在 **收帳** 索引標籤上顯示的應收帳款參數。

## <a name="optional-set-up-collections-agents"></a>選擇性：設定收帳代理人
如果您組織的多名人員執行收帳工作，您可以建立收帳代理人。 收帳代理人是在 **使用者關係** 頁面上設定為使用者的工作者。 您可以將客戶群 (客戶查詢) 指派給收帳代理人，以協助代理人安排他們的工作。 收帳代理人會加入 **應收帳款參數** 頁面中選擇的團隊。 如果未在此頁面中選擇團隊，則將自動建立名為 **收帳** 的新團隊，同時收帳代理人也會加入該團隊。

## <a name="set-up-a-writeoff-account"></a>設定沖銷帳戶
已沖銷交易時，設定用於總帳沖銷分錄的沖銷帳戶。 此帳戶儲存在客戶過帳設定檔中。

## <a name="set-up-nsf-information-for-bank-accounts"></a>設定銀行帳戶 NSF 資料
更新銀行帳戶，以便在 **收帳** 頁面中標識 NSF 付款時，這些帳戶具有正確的日記帳。 在 **貨幣管理** 索引標籤中的 **NSF 付款日記帳** 欄位內，選擇付款日記帳。

## <a name="set-up-outlook-settings-for-users-of-the-collections-page"></a>設定 [收帳] 頁面的使用者 Outlook 設定
在工作者可以使用 **收帳** 頁面建立活動或發送電子郵件訊息之前，您必須確認已選擇 **Microsoft Outlook 同步** 組態金鑰，並且為這些工作者設定 Outlook 同步。

## <a name="set-up-email-and-addresses"></a>設定電子郵件和地址
您可以使用電子郵件與客戶和銷售人員針對收帳問題進行溝通，以便從 **收帳** 頁面發送電子郵件。 

### <a name="set-up-email-and-address-settings-for-collections-customer-contacts"></a>設定收帳客戶聯絡人的電子郵件和地址設定
設定客戶聯絡人的電子郵件地址，以將電子郵件發送給來自 **收帳** 頁面的連絡人。 收帳連絡人用來作為 **收帳** 頁面中的預設連絡人。 如果報告應該使用主要地址以外的地址，您可以設定客戶的報告地址。 

在客戶的 **信用和收帳** FastTab 上，在 **收帳連絡人** 欄位中，選擇客戶組織中與您的收帳代理人合作的人員。 此人視為 **收帳** 頁面上的預設連絡人，並且是電子郵件的收件人員。 

> [!NOTE] 
> 如果未指定客戶收帳連絡人，則使用客戶的主要連絡人。 如果未指定主要連絡人，則電子郵件會發送到 **連絡人** 頁面中列出的第一個地址。

### <a name="set-up-email-settings-for-salespeople"></a>設定銷售人員的電子郵件設定
設定銷售人員聯絡人的電子郵件地址，以將電子郵件發送給來自 **收帳** 頁面的銷售人員。 為每個佣金銷售群組中的每個銷售代表設定電子郵件地址。 已選取 **連絡人** 選項的銷售代表是接收電子郵件的預設銷售人員。 

如果未指定銷售代表，則使用客戶組織的主要銷售人員。 如果未指定主要銷售人員，則電子郵件會發送到頁面中列出的第一個銷售人員。


有關詳細資訊，請參閱下列主題：

 - [建立收帳委託書序列](tasks/create-collection-letter-sequence.md)

 - [處理催款單](tasks/process-collection-letters.md)

 - [審核收帳資料](tasks/review-collections-information.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]