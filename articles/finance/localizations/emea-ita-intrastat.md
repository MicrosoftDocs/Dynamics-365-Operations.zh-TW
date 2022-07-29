---
title: 義大利 Intrastat
description: 本主題包含有關法國 Intrastat 回報的資訊。
author: anasyash
ms.date: 09/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 3b676ba754cded03fdc6d566ffbfbb35c204b03a
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2021
ms.locfileid: "8450981"
---
# <a name="italian-intrastat"></a>義大利 Intrastat

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>概觀

這 **內部統計** 頁面用於生成和報告有關歐盟 (EU) 國家之間貿易的資訊。 義大利 Intrastat 包含有關商品和服務貿易的月度或季度報告資訊。

下表顯示出現在義大利 Intrastat 申報中的欄位。

<table>
<tbody>
<tr>
<td rowspan="3">
<p><strong>值</strong></p>
</td>
<td rowspan="3">
<p><strong>Intrastat 日誌欄位</strong></p>
</td>
<td colspan="4">
<p><strong>商品</strong></p>
</td>
<td colspan="2">
<p><strong>服務</strong></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><strong>派遣</strong></p>
</td>
<td colspan="2">
<p><strong>到貨</strong></p>
</td>
<td rowspan="2">
<p><strong>派遣</strong></p>
</td>
<td rowspan="2">
<p><strong>到貨</strong></p>
</td>
</tr>
<tr>
<td>
<p><strong>每月</strong></p>
</td>
<td>
<p><strong>每季</strong></p>
</td>
<td>
<p><strong>每月</strong></p>
</td>
<td>
<p><strong>每季</strong></p>
</td>
</tr>
<tr>
<td>
<p>貴公司的增值稅 (VAT) 註冊號</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>客戶或廠商免稅編號</p>
</td>
<td>
<p><strong>免稅編號</strong>中的欄位<strong>一般</strong>部分</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>以會計貨幣表示的發票金額</p>
</td>
<td>
<p><strong>發票金額</strong>中的欄位<strong>發票面額</strong>部分</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>交易幣別的發票金額</p>
</td>
<td>
<p><strong>發票金額 (交易貨幣)</strong> 中的欄位<strong>發票面額</strong>部分</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>發票編號</p>
</td>
<td>
<p><strong>發票</strong>中的欄位<strong>一般的</strong>部分</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>發票日期</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>交易代碼</p>
</td>
<td>
<p><strong>代碼</strong>部分中的<strong>交易代碼</strong>欄位</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td>
<p>商品碼</p>
</td>
<td>
<p><strong>代碼</strong>部分中的<strong>商品</strong>欄位</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>重量</p>
</td>
<td>
<p><strong>重量</strong>中的欄位<strong>資料</strong>部分</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td>
<p>其他單位</p>
</td>
<td>
<p><strong>附加單元的數量</strong>中的欄位<strong>單元</strong>部分</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td>
<p>依記帳貨幣計價的統計值</p>
</td>
<td>
<p><strong>統計值</strong>中的欄位<strong>統計值</strong>部分</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td>
<p>交貨條件</p>
</td>
<td>
<p><strong>代碼</strong>部分中的<strong>交貨條件</strong>欄位</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td>
<p>交貨排程</p>
</td>
<td>
<p><strong>代碼</strong>部分中的<strong>交貨排程</strong>欄位</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>運輸方式</p>
</td>
<td>
<p><strong>代碼</strong>部分中的<strong>運輸</strong>欄位</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td>
<p>付款方式</p>
</td>
<td>
<p>在<strong>付款方式</strong>欄位中，選擇<strong>代碼</strong></p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>支付國家/地區的國際標準化組織 (ISO) 代碼</p>
</td>
<td>
<p>貴公司所在國家/地區 (用於發貨) 或供應商公司所在國家/地區 (用於到達) 的 ISO 代碼</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>X</p>
</td>
</tr>
<tr>
<td>
<p>國家/地區</p>
</td>
<td>
<p><strong>國家/地區欄位</strong>在裡面<strong>調度/目的地</strong>部分</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td>
<p>來源或目的地縣市</p>
</td>
<td>
<p><strong>原籍/目的地縣</strong>中的欄位<strong>發貨/目的地</strong>部分</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td>
<p>原產地國家/地區</p>
</td>
<td>
<p><strong>原產國/地區</strong>中的欄位<strong>原產國/地區</strong>部分</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
<tr>
<td>
<p>原產地</p>
</td>
<td>
<p><strong>原產國家/地區</strong>中的欄位<strong>原產國/地區</strong>部分</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>X</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>&nbsp;</p>
</td>
</tr>
</tbody>
</table>

您必須向當局發送兩份報告。 一份報告是針對社區內派遣的，另一份是針對社區內到達的。 每份報告由五個部分組成：

- **封面**

- **第 1 節貨物**：此部分包含與 Intrastat 申報期相同報告期的貨物發票相關的正常交易和貸方通知單的資訊。
- **第 2 節。 貨物更正**：本節包含與先前 Intrastat 報告期間的貨物發票相關的更正和貸方通知單的資訊。
- **第 3 節服務**：此部分包含與 Intrastat 申報期相同報告期的服務發票相關的正常交易和貸方通知單的資訊。
- **第 4 節。 服務更正**：本節包含與先前 Intrastat 報告期間的服務發票相關的更正和貸方通知單的資訊。

## <a name="set-up-intrastat"></a>安排 Intrastat

### <a name="preliminary-setup"></a>初步設置

在開始使用 Intrastat 之前，應設置以下一般資訊：

   - 商品碼。 對於服務，您應該定義六位數的商品代碼。
   - 交易代碼。 請注意，義大利使用一位交易代碼。
   - 運輸方式。
   - 統計資料程序。
   - 外貿參數。
   - 倉庫。
   - 已發佈產品詳細資料。
   - 代理程式連絡資訊。

如需相關資訊，請參閱 [Intrastat 總覽](emea-intrastat.md)。

### <a name="set-up-italian-intrastat"></a>設置義大利 Intrastat

按照以下步驟設置義大利語特定選項，以便您可以使用 Intrastat。

1. 在 [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index)，在共享資產庫中，為 Intrastat 申報下載以下電子申報 (ER) 配置的最新版本：

    - 內部統計模型
    - Intrastat 報表
    - Intrastat (IT)

    如需更多資訊，請參閱[從 Lifecycle Services 下載電子報表編製配置](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)。

2. 在 Dynamics 365 Finance 中，前往 **稅務**  >  **設置**  >  **外貌參數**。
3. 在 **內部統計** 索引標籤，在 **一般** 的 FastTab，設置以下欄位：

    - **原籍/目的地縣**：選擇您公司所在的縣。 這個縣將用於調度。
    - **交易代碼**：選擇房產轉讓的交易代碼。 此代碼將用於導致實際或計劃的財產轉移以補償的交易，以及更正。

    - **信用票據**：選擇退貨的交易代碼。
    - **銷售報告期**：選擇出口報關的報告期：**月** 或 **季**。 季度申報以簡化格式匯出。
    - **購買報告期**：選擇出口報關的報告期：**月** 或 **季**。 季度申報以簡化格式匯出。

4. 在 **電子報告** FastTab，設置以下欄位：

    - **檔案格式對應**：選擇 **Intrastat (IT)**。
    - **報告格式對應**：選擇 **Intrastat 報告**。

5. 在裡面 **商品代碼層次結構** FastTab，在 **類別層次結構** 欄位，選擇 **內部統計**。
6. 在 **統計值** 快速索引標籤，設置 **打印和匯出統計數據** 選項 **是的** 如有必要。 此設置激活統計部分的傳輸。 統計部分包含有關重量、附加單位、統計值、交貨條款、交貨時間表、運輸方式和原產地的數據。

    > [!NOTE]
    > 對於季度申報，Intrastat 報告將不包括統計部分或有關交貨條款和運輸方式的資訊。 關於詳細資訊，請參閱本主題的[概覽](#overview)部分中的表格。

7. 在 **國家/地區屬性** 索引標籤，列出與您的組織有業務往來的所有國家或地區。 對於每個國家/地區，設定下列欄位：

    - **締約方國家/地區**：選擇國家/地區代碼。
    - **內部統計代碼**：輸入兩位數的 Intrastat 代碼。
    - **貨幣**：指定國家或地區的本國貨幣。 如果供應商位於不使用歐元的歐盟國家/地區，發票金額將以供應商的貨幣和歐元報告。 例如，如果供應商位於丹麥，則報告的進口申報金額將以丹麥克朗 (DKK) 和歐元 (EUR) 為單位。
    - **國家/地區類型**：選擇與您的組織相關的國家或地區的類型。 對於 Intrastat 期刊，只有國家或地區 **歐盟** 和 **國內特價** 類型將被轉移。

    > [!NOTE]
    > 對於國家或地區 **國內特價** 類型，則 Intrastat 報告文件中省略了以下欄位：**重量**、**附加單元**、**統計值**、**交貨條件**、**運輸代碼**、**原產國/地區/目的地**，和 **原籍/目的地縣**。 例如，在 **締約方國家/地區** 欄位，選擇 **SMR（聖馬力諾）**，然後，在 **國家/地區類型** 欄位，選擇 **國內特價**。

8. 去 **應付帳款** > **設置** > **遞送條款**。
9. 在網格中，選擇交貨條款。
10. 在 **一般的** 快速索引標籤，在 **內部統計代碼** 欄位中，輸入將在 Intrastat 報告中使用的一位代碼。
11. 按照以下步驟為客戶和供應商分配免稅編號。 這些數字將出現在 Intrastat 報告中。
12. 去 **稅** > **設置** > **銷售稅** > **免稅號碼**，並列出您的客戶和供應商的所有免稅號碼。 對於每個合作夥伴，設定下列欄位：

    - **國家/地區**：選擇合作夥伴的國家/地區。
    - **免稅編號**：輸入合作夥伴的免稅編號。
    - **公司名**：輸入合作夥伴的名稱。

13. 去 **應收賬款** > **顧客** > **所有客戶**，並為每位客戶執行以下步驟：

    1. 請選取一名客戶。
    2. 在 **發票和交貨** FastTab，在 **銷售稅** 部分，在 **免稅編號** 欄位，選擇 **全部**。
    3. 選擇客戶的免稅編號。

14. 去 **應付賬款** > **廠商** > **所有廠商**，並為每位廠商執行以下步驟：

    1. 選取廠商。
    2. 在 **發票和交貨** FastTab，在 **銷售稅** 部分，在 **免稅編號** 欄位，選擇 **全部**。
    3. 選擇廠商的免稅編號。

15. 前往 **稅務** > **設置** > **外貿** > **內部統計的壓縮**，並選擇在匯總 Intrastat 資訊時應比較的欄位。 對於義大利，選擇 **免稅編號**、**交易代碼**、**商品**、**交貨條件**、**運輸**、**國家/地區**、**原產國/地區**、**原籍縣**、**原籍/目的地縣**、**貨幣**、**月**、**季** 和 **修正年份**。

## <a name="italian-vendor-invoice-journal-for-foreign-trade"></a>義大利外貿供應商發票日記帳

使用供應商發票日記帳時，考慮一些影響 Intrastat 報告的參數至關重要。 在 **外貿** 索引標籤，您可以查看和設置以下義大利特定欄位。

| **欄位**                    | **描述**                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------|
| 交易代碼             | 選擇交易代碼。                                                                    |
| 運輸                    | 選擇用於傳輸的傳輸。                                             |
| 商品                    | 選擇項目商品代碼。                                                                 |
| 其他單位             | 如果應為所選商品代碼報告附加單位，請輸入附加單位。 |
| 國家/地區               | 選擇合作夥伴的國家/地區。                                                            |
| 來源/目的地縣市 | 選取目的縣。                                                                  |

## <a name="intrastat-journal"></a>內部統計日誌

您使用 Intrastat 日誌來管理有關歐盟國家之間貿易的資訊。

要打開 Intrastat 日記帳，請轉到 **稅**&gt;**聲明**&gt;**外貿**&gt;**內部統計**。 每筆交易都會顯示以下資訊：

| **欄位**                              | **描述**                                                                                                                                                                                                                                                                                                                                                                                                         |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 日期                                   | 交易的過帳日期。                                                                                                                                                                                                                                                                                                                                                                                    |
| 方向                              | 該欄位設置為 **到達** 購買或 **派遣** 為銷售。                                                                                                                                                                                                                                                                                                                                            |
| 項目類型                              | 該欄位可以設置為 **商品** 或 **服務**。                                                                                                                                                                                                                                                                                                                                                                     |
| 修正                             | 當此選項設置為 **是的**、 交易是修正。 在這種情況中，您報告對已報告的 Intrastat 交易的更正。 在 **一般的** 索引標籤，在 **更正** 部分，使用 **月**、**季**，和 **修正年份** 欄位以指定原始交易期間。 使用 **原始 Intrastat 記錄** 欄位以指定原始記錄。 |
| 項目編號                            | 已發布產品的代碼。                                                                                                                                                                                                                                                                                                                                                                                      |
| 類別                               | 名稱或採購類別。                                                                                                                                                                                                                                                                                                                                                                                   |
| 商品                              | 品項商品代碼。 該值在 **已發布產品詳情** 產品頁面，也可以在交易行手動設置。                                                                                                                                                                                                                                                              |
| 重量                                 | 交易行的重量，以公斤為單位。 該值在 **已發布產品詳情** 產品頁面，也可以在交易行手動設置。                                                                                                                                                                                                                                |
| 發票金額                         | 記帳貨幣的金額                                                                                                                                                                                                                                                                                                                                                                                   |
| 以交易貨幣計價的發票金額 | 合作夥伴本國貨幣的金額。                                                                                                                                                                                                                                                                                                                                                                     |
| 貨幣                               | 合作夥伴本國貨幣。                                                                                                                                                                                                                                                                                                                                                                                   |

>[!NOTE]
>
>如果您在與報告期間相同的期間收到負更正（貸方通知單），您必須按照以下步驟手動更改內部統計日記帳。
>
> 1. 進入 **稅務** > **申報** > **外貿** > **Intrastat**。
> 2. 查找並刪除標記為更正的交易。
> 3. 找到原始交易，改變交易的價值 **發票金額** 視情況而定。
> 例如，您有一張 10,000 的發票，而您收到一張 -2,000 的貸方通知單。 在這種情況下，您必須打開 Intrastat 日記帳，找到並刪除 -2,000 的交易。 然後找到 10,000 的原始交易，並將發票金額設置為 8,000（= 10,000 - 2,000）。

### <a name="intrastat-transfer"></a>Intrastat 轉移

在操作窗格中，您可以選擇 **轉移** 從您的銷售訂單、普通發票、採購訂單、供應商發票、供應商產品收據、項目發票和轉移訂單中自動傳輸有關社區內貿易的資訊。 只有將歐盟國家作為目的地國家或地區 (對於派送) 或託運 (對於到達) 的文件才會被轉移。

或者，您可以通過在動作窗格中選擇 **全新** 手動輸入交易。

對於每筆交易，您可以在 **一般** 的標籤。下表提供了有關欄位的更多資訊。

| 欄位 | 描述 |
|-------|-------------|
| 項目類型 | 該欄位可以設置為 **商品** 或 **服務**。<br> 對於被視為服務的交易，您的發票行應通過以下方式之一設置：<br>- 沒有商品代碼<br>- 它有一個六位數的商品代碼  |
| 原產地 | 產品或服務的來源郡。 此值在 **已發布產品** 頁面上指定。 |
| 交貨模式 | 交貨模式。 <br>要指定交付方式，請訪問 **銷售和營銷** > **設置** > **分配** > **交貨方式**。 |
| 月 | 原始交易的月份。 |
| 季 | 原始交易的季 |
| 修正年度 | 原始交易的年份。 |
| 原始 Intrastat 記錄 | 對於服務更正，輸入原始 Intrastat 記錄的編號。 |
| 貨幣 | 合作夥伴本國貨幣。 |
| 以交易貨幣計價的發票金額 | 合作夥伴本國貨幣的發票。 |
| 以交易貨幣計價的發票費用金額 | 合作夥伴本國貨幣的收費。 |
| 以交易貨幣計價的發票值 | 合作夥伴本國貨幣的發票值。 |

有關以合作夥伴本國貨幣計價的發票費用的更多資訊，請參閱[Intrastat 概覽先決條件（雜項費用）](emea-intrastat.md)。

### <a name="generate-an-intrastat-report"></a>產生 Intrastat 報表

1. 要生成 Intrastat 報告，請轉到 **稅** > **聲明** > **外貿** > **內部統計**。
2. 在動作窗格上，選擇 **輸出**  >  **報告**。
3. 在裡面 **內部統計報告** 對話框中，選擇報告的開始和結束日期。
4. 在裡面 **生成文件** 欄位，選擇 **是的** 生成。txt 文件並輸入文件名。
5. 在裡面 **生成報告** 欄位，選擇 **是的** 生成 。xlsx 文件並輸入報告名。
6. 選擇 **到達** 或 **派遣** 根據報告的內容。
7. 在裡面 **參考編號** 欄位，輸入文件編號。 此值會影響 Intrastat 文件報告上的文件編號代碼。 
