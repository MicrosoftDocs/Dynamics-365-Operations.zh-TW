---
title: 設定和產生付款確認檔案
description: 本主題說明如何設定付款確認和產生付款確認檔案。
author: panolte
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 992c73b1ba1f461542873a7df97f1539b99fc015c3e6ef090993e90212993851
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450384"
---
# <a name="set-up-and-generate-positive-pay-files"></a>設定和產生付款確認檔案

[!include [banner](../includes/banner.md)]

本主題說明如何設定付款確認和產生付款確認檔案。 

設定付款確認以產生提供給銀行的電子支票清單。 然後，當支票提交給銀行時，銀行將會比較支票與支票清單。 如果支票與清單中的支票相符，銀行將清除支票。 如果支票與清單中的支票不相符，銀行將保留支票以供審查。

## <a name="security-for-positive-pay-files"></a>付款確認檔案的安全性
付款確認檔案可能含有相關收款人和支票金額的敏感資料。 因此，請確保從檔案產生後直到銀行接收檔案之前，採取合適的安全措施。 付款確認檔案將下載到您的 Web 瀏覽器指定的位置。 由於付款確認檔案可能含有敏感資料，務必確保僅授權使用者可以在 Microsoft Dynamics 365 Finance 中產生和查看此資料。 使用下表可幫助您確定所需的權限。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>工作</th>
<th>權限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>從<strong>銀行帳戶</strong>清單頁面或<strong>銀行帳戶</strong>頁面產生付款確認檔案。</td>
<td><ul>
<li><strong>維護銀行付款確認資料</strong>(BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>從<strong>產生付款確認檔案</strong>頁面產生多個法律實體和銀行帳戶的付款確認檔案。</td>
<td><ul>
<li><strong>維護銀行付款確認資料</strong>(BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>在<strong>付款確認檔案總覽</strong>頁面查看付款確認檔案。</td>
<td><strong>查看多個法律實體的銀行付款確認資料</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>在<strong>付款確認檔案總覽</strong>頁面確認銀行付款確認檔案。</td>
<td><strong>確認付款檔案</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>在<strong>付款確認檔案總覽</strong>頁面撤回銀行付款確認檔案。</td>
<td><strong>撤回付款確認檔案</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a>設定付款確認格式
使用資料實體建立付款確認檔案。 在產生付款確認檔案之前，必須設定要用於將支票資料轉化為可與銀行通信格式的轉換輸入格式。 在 **付款確認格式** 頁面，可以建立檔案格式識別碼和說明。 轉換輸入格式必須是 XML 類型。 具體格式視使用的轉換檔案而定。 例如，提供的可擴充樣式表語言轉換 (XSLT) 範例檔使用 **XML-Element** 格式。 使用 **上傳用於轉換的檔案** 操作指定您的銀行所需格式的轉換檔案位置。

## <a name="example-xslt-file-for-positive-pay-file"></a>範例：付款確認檔案的 XSLT 檔案

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
  <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
  <xsl:template match="/">
    <xsl:value-of select="'
'" />
    <Document>
      <xsl:value-of select="'
'" />
      <!--Header Begin-->
      <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
      <xsl:value-of select="'
'" />
      <!--Header End-->
      <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
        <!--Cheque Detail begin-->
        <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
            <xsl:value-of select='string("Yes")'/>
          </xsl:when>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
            <xsl:value-of select='string("No")'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='string(" ")'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("Payment")'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='CHEQUENUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='AMOUNTCUR/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("BOA-#1812")'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
            <xsl:value-of select='VENDGROUP/text()'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='CUSTGROUP/text()'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="'
'" />
      </xsl:for-each>
    </Document>
  </xsl:template>
</xsl:stylesheet>
```

> [!NOTE]
> XSLT 中的 XML 名稱必須與 XML 中節點的大小寫相符。 XSLT 和 XML 檔案均區分大小寫。 

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a>指派付款確認格式至銀行帳戶
對於想要產生付款確認資料的每個銀行帳戶，必須指派在前一部分中指定的付款確認格式。 在 **銀行帳戶** 頁面中，選擇與銀行帳戶對應的付款確認格式。 在 **付款確認開始日期** 欄位中，輸入第一個日期以產生付款確認檔案。 務必在此欄位中輸入日期。 否則，您產生的第一個付款確認檔案會包含曾經為此銀行帳戶建立的所有支票。

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>指派付款確認檔案的數字序列
每個付款確認檔案僅具有一組唯一的編號。 使用 **現金和銀行管理參數** 頁面中的 **數字序列** 索引標籤建立付款確認檔案的數字序列。

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>產生單個銀行帳戶的付款確認檔案
您可以產生單個法律實體和單個銀行帳戶的付款確認檔案。 有關如何同時為多個法律實體和銀行帳戶產生付款確認檔案的資料，請參閱下一部分。 若要生成單個法律實體和單個銀行帳戶的付款確認檔案，從 **銀行帳戶** 頁面開啟 **產生付款確認檔案** 對話方塊。 在 **截止日期** 欄位中，輸入要包含在付款確認檔案中的最後支票日期。 所有在該支票日期結束前，未包含在付款確認檔案中的支票將包括在該檔案中。

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>產生多個銀行帳戶的付款確認檔案
若要生成多個銀行帳戶的付款確認檔案，使用 **產生付款確認檔案** 定期任務。 選擇檔案的付款確認格式，並指定是為所有法律實體還是所選法律實體產生檔案。 您還可以為使用指定付款確認格式的所有銀行帳戶或為所選銀行帳戶產生付款確認檔案。 在 **截止日期** 欄位中，輸入要包含在付款確認檔案中的最後支票日期。 所有在該支票日期結束前，未包含在付款確認檔案中的支票將包括在該檔案中。

## <a name="view-the-results-of-positive-pay-file-generation"></a>查看付款確認檔案產生的結果
付款確認檔案產生後，可以在 **付款確認檔案總覽** 頁面查看結果。 若要查看單張支票的詳細資料，則使用 **付款確認檔案** 詳細資料頁面。

## <a name="confirm-a-positive-pay-file"></a>確認付款確認檔案
當付款確認檔案中列出的支票支付後，您會從銀行收到一組確認編號。 然後，您可以確認付款確認檔案。 在 **付款確認檔案** 頁面中，選擇狀態為 **已建立** 的付款確認檔案，然後選擇 **輸入確認** 操作。 在確認付款確認檔案時，會記錄您從銀行收到的確認編號。

## <a name="recall-a-positive-pay-file"></a>撤回付款確認檔案
如果您必須更改付款確認檔案，您可以將其撤回。 在 **付款確認檔案** 頁面中，選擇狀態為 **已建立** 的付款確認檔案，然後選擇 **撤回** 操作。 對於付款確認檔案中的每張支票，將重設指示該支票是否包括在付款確認檔案中的欄位。 然後，您可以建立一個新的付款確認檔案，其中包括已撤回的支票。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
