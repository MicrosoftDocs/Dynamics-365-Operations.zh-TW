---
title: 審核收帳資料
description: 本主題說明如何審核收帳資料，以及各種設定選項和收帳交易。
author: ShivamPandey-msft
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustCollectionsPool, SysQueryForm, CustCollectionsAgent, OMTeamSelectMemberDialog, CustVendReportInterval, CustParameters, CustAgingSnapshot, CustVendAgingBucketLookUp, CustCollectionsPoolsListPage, CustCollectionsContactPart, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 59fcaef39460761dbe68273aecb5cbff8850ef031d43393277a17d07dd92db3b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450852"
---
# <a name="review-collections-information"></a>審核收帳資料

[!include [banner](../../includes/banner.md)]

本主題說明如何審核收帳資料，以及各種設定選項和收帳交易。 此程序使用的是 USMF 示範公司。

## <a name="create-customer-pools"></a>建立客戶群
1. 在瀏覽窗格中，前往 **模組 > 信用和收帳 > 設定 > 客戶群**。
- 使用此頁面建立客戶群，作為定義客戶帳戶群組的資料庫，可以用於展示和管理收帳或帳齡流程。 在 **收帳** 清單頁面以及相關清單頁面使用客戶群篩選資料。 如果已建立帳齡快照，也可以使用客戶群篩選包含在該帳齡快照中的客戶帳戶。  
- 如果已建立帳齡快照，可以使用客戶群篩選其所包含的客戶帳戶。  
2. 選擇 **新建**。
3. 在 **群識別碼** 欄位中，輸入一個值。
4. 在 **群說明** 欄位中，輸入一個值。
5. 按一下 **選擇群條件**。
6. 在 **條件** 欄位中，輸入一個值。
7. 選取 **確定**。
8. 選擇 **預覽客戶群**。

## <a name="create-collections-agents"></a>建立收帳代理人
1. 在瀏覽窗格中，前往 **模組 > 信用和收帳 > 設定 > 收帳代理人**。  
- 使用此頁可以將工作人員設定為收帳代理人，同時可以選擇性地將客戶群指派給他們。 *收帳代理人* 是處理客戶工作以確保按時收到付款的人員。  
- 設定在此頁面的收帳代理人會自動加入收帳團隊。 在 **應收帳款參數** 頁面的 **團隊** 欄位中所選擇的團隊就是收帳代理人加入的團隊。 如果未選擇團隊，則將自動建立一個名為「收帳」的新團隊，同時收帳代理人也會加到該團隊。  
2. 選擇所需的代理人，然後在頁面中選擇 **新增**。
3. 在 **群識別碼** 欄位中，在下拉式選單中選擇所需的記錄。
4. 選取或清除 **預設群** 核取方塊。
- 選擇此選項，則所選的收帳代理人可以包含所有客戶群。 如果未選擇此選項，則篩選清單中只有指派給收帳代理人的客戶群。  

## <a name="create-aging-period-definition"></a>建立帳齡期間定義
1. 在瀏覽窗格中，前往 **模組 > 信用和收帳 > 設定 > 帳齡期間定義**。
- 可以使用帳齡期間定義，根據您所輸入的日期分析客戶帳戶和廠商帳戶的到期情況。 進行分析時，您為每個帳齡期間所設定的帳齡期間定義對應於清單頁面或表單或報告中的一欄。  
2. 選擇 **新建**。
3. 在 **帳齡期間** 欄位中，輸入一個值。
4. 在 **描述** 欄位中，輸入一個值。
- 為每個帳齡期間指定期間名稱、單位和間隔，並列入帳齡期間定義中。 [單位] 欄位中有 0 (零) 的行顯示該分析執行的日期。 在 [單位] 欄位中零之前的行預設值為 -1，零之後的行預設值為 1，該預設值可以更改。 選擇 **向上** 和 **向下** 重新排列明細。 但不能移動 0 (零) 行。  
- 將指針放置在新建插入行的位置，然後選擇 **新增**。  
- 選取指標以表示 **收帳** 表單和清單頁面中的帳齡期間。 例如，您可以為目前期間選擇綠色指標、為過去 30 天期間選取黃色指標，以及為過去 90 天期間選取紅色指標。  
- 選取帳齡期間定義的列印方向。 此選取項目決定各欄在客戶帳齡報表或廠商帳齡報表中的顯示順序。  
  - 正向 – 從頂端列開始，依標題在表格中出現的相同順序列印各欄。  
  - 反向 – 從底部列開始，依標題在表格中出現的相反順序列印各欄。    

## <a name="setup-collections-parameters"></a>設定收帳參數
1. 在瀏覽窗格中，前往 **模組 > 信用和收款 > 設定 > 應收帳款參數**。
2. 選擇 **收帳** 索引標籤。
3. 展開或摺疊 **收帳預設** 區段。
- 為該預設帳齡快照選擇一個帳齡期間定義，以用於 **收帳** 表單。  
- 在 **收帳代理人** 表單中，選擇收帳代理人所指派到的團隊。 在此清單中僅顯示「收帳」類型的團隊。  
4. 展開或摺疊 **沖銷** 區段。
- 在使用 **收帳** 表單或相關清單頁面沖銷交易時，選擇要使用為每日分類帳日記帳設定的日記帳名稱。  
- 在使用 **收帳** 表單或相關清單頁面建立沖銷交易時，選擇要使用的預設原因代碼。  
- 在使用 **收帳** 頁面或相關清單頁面建立沖銷交易時，選擇此選項為銷售稅金額建立一個單獨的日記帳明細。 如果選擇此選項，則可以輕鬆追踪沖銷交易所涉及的銷售稅金額。 您可以單獨追踪該銷售稅金額，使您可以在受影響期間更輕鬆地應對該銷售稅的不利因素。  
5. 展開或摺疊 **電子郵件範本** 區段。
- 透過使用 **收帳** 表單中的 **電子郵件 > 交易** 發給連絡人功能發送郵件時，選擇要使用的電子郵件範本。  
- 透過使用 **收帳** 表單中的 **電子郵件 > 報表** 發給連絡人功能發送郵件時，選擇當將客戶對帳單作為電子郵件附件發送時要使用的電子郵件範本。  
- 透過使用 **收帳** 表單中的 **電子郵件 > 交易** 發給業務人員功能發送郵件時，選擇要使用的電子郵件範本。  

## <a name="age-customer-balance"></a>客戶餘額年限
1. 在瀏覽窗格中，前往 **模組 > 信用和收帳 > 定期任務 > 客戶餘額年限**。
- 選擇帳齡期間定義。 帳齡快照根據所選帳齡期間定義中帳齡期間處理帳齡交易。  
- 選擇一個客戶群或者保持該欄位空白，為所有客戶建立一個帳齡快照。 如果已選擇客戶群，則帳齡快照流程僅適用於屬於客戶群的客戶帳戶。 所選的客戶群必須是「帳齡快照類型」。  
- 選擇帳齡快照所依據的日期類型。  
  - 交易日期：根據交易日期對每筆交易計算帳齡。    
  - 到期日：根據到期日對每筆交易計算帳齡。    
  - 單據日期：根據單據日期對每筆交易計算帳齡。  
- 選擇要作為帳齡快照目前日期的日期。 帳齡期間根據此日期計算。    
  - 今天的日期：使用系統日期。 如果設定為發生定期的批次處理，則使用此選項。 如果使用此日期，則可以定期執行週期性批次處理並使用當時的系統日期。    
  - 選定日期：使用您指定的日期。 如果選擇此選項，請輸入一個帳齡日期。  
2. 選取 **確定**。

## <a name="view-aged-customer-balances"></a>查看帳齡客戶餘額
1. 在瀏覽窗格中，前往 **模組 > 信用和收帳 > 收帳 > 帳齡餘額**。
- 使用此清單頁面可按帳齡期間查看客戶餘額和帳齡金額。 此資料儲存在帳齡快照中。 帳齡期間由所用的帳齡期間定義決定。 如果為群查詢指定了某個客戶，則帳齡期間定義從自客戶群中提取。 如果客戶群裡沒有帳齡期間定義，則使用應收帳款參數表單中設定的預設帳齡期間定義。  
2. 展開 **連絡人** FactBox。 可在此處查看連絡人資料：
- 客戶收帳連絡人。  
- 客戶預設銷售人員。  
3. 展開 **信用額度** FactBox。
- 使用 **信用資料** FactBox 查看客戶的信用額度和目前餘額資料。  

## <a name="view-customer-collections-details"></a>查看客戶收帳詳細資料
1. 確保選擇所需記錄。
2. 展開 **地址**、**連絡人**、**帳齡**，和 **信用額度** FactBoxes 查看給定資料。
3. 在「動作窗格」上，選擇 **收帳**。
- 使用目前的日期更新客戶帳齡快照，因為帳齡日期是與交易日期相比較而來的。 如果該帳齡快照包含多個法律實體的資料，則更新的帳齡快照也包含同一組法律實體的資料。 當更新該帳齡快照時，您所登錄的法律實體記帳貨幣金額已儲存。  
- 選擇帳齡期間定義。 預設情況下，顯示的是該客戶帳齡快照相關的帳齡期間定義。 帳齡期間定義決定帳齡期間以及在 **帳齡餘額** 和 **信用資料** FactBoxes 中顯示的金額。  
- 開啟包含以下項目的選單：    
  - 在 [帳齡餘額] 和 [信用資料] FactBoxes 中以法律實體的記帳貨幣顯示金額。  
  - 客戶 – 在 [帳齡餘額] 和 [信用資料] Fact Boxes 中以客戶的貨幣顯示金額。  
- 在客戶帳齡快照中選擇一個或多個法律實體以查看其資料。 建立帳齡快照時，已選擇在清單中顯示的法律實體。  
- 用 Microsoft Excel 格式查看客戶的報表。 為包含在此報表中之交易的範圍選擇一個開始日期，並確定是否僅包含未結交易，或同時包含未結和已結交易。 如果該帳齡快照包含多個法律實體，則包含所有這些法律實體的交易。  
- 開啟 **單據** 表單，可在其中建立或編輯單據或註解。  
4. 在「動作窗格」上，選擇 **通訊**。  
- 開啟 Outlook，在 [連絡人] 欄位中給指定連絡人發送電子郵件。 如果未指定收帳連絡人，則使用客戶的主要地址。 如果未指定主要連絡人，則電子郵件將發送到 **連絡人** 表單中列出的第一個地址。 所選擇的交易將以附件的方式附加在內。 附件為 Excel 格式，共有三個工作表。 在 **應收帳款參數** 表單中指定客戶連絡人的電子郵件訊息範本。  
- 如果此表中所選的連絡人未設定電子郵件地址，則無法使用此按鈕。  
- 準備一份報表並開啟 Outlook，在 **連絡人** 欄位中給該指定連絡人發送一封附有報表的電子郵件。 如果未指定收帳連絡人，則使用客戶的主要地址。 如果未指定主要連絡人，則電子郵件將發送到 **連絡人** 表單中列出的第一個地址。  
- 如果此表中所選的連絡人未設定電子郵件地址，則無法使用此按鈕。  
- 開啟 Outlook，給指派給客戶銷售組的銷售代表員工發送一封電子郵件。 如果所選擇的交易將以附件的方式附加在內。 附件為 Excel 格式，共有兩個工作表。 在 **應收帳款參數** 表單中指定銷售人員的電子郵件訊息範本。  
- 如果此表中顯示的銷售人員未設定電子郵件地址，則無法使用此按鈕。  
- 查看客戶的交易並執行操作。 如果使用集中付款，則客戶帳齡快照中包括所有法律實體的資料。 可以透過在「動作窗格」上的 **選擇** 群組中選擇 **公司** 來限制法律實體資料。  
- 為選定的交易修改收帳狀態。    
  - 無爭議：本交易未發生收帳動作。    
  - 有爭議：客戶通知交易有問題。    
  - 答應付款：客戶已同意按約定交易額付款。    
  - 已解決：所有與交易有關的問題已解決，無需進一步的收帳動作。  
- 開啟選單並選擇以下其中一個項目，以指定要在此表單中顯示交易：    
  - 未結：僅顯示尚未結算的交易。    
  - 未結和已結：顯示所有交易，包括已結算和未結算。  
- 將所選的付款作為資金不足 (NSF) 付款處理。    
  - 本按鈕僅可用於所選的交易是記錄在輸入的付款下 (沒有發票的貸方餘額)，有關聯的銀行帳號，且付款在以前沒有被取消。  
- 沖銷所選的交易。  
- 選擇並標記需要雙方協商的交易。  
- 開啟 **原始單據** 表單，可以查看和列印所選交易的單據。  
- 開啟包含以下項目的 **選單**：    
  - 收帳：僅顯示在「收帳」表單中建立的活動。    
  - 全部：顯示客戶的所有活動，無論是在何處建立的。  
- 開啟包含以下項目的 **選單**：    
  - 未結：僅顯示未結的活動。    
  - 未結和已結：顯示所有活動，無論其狀態為何。  
- 選擇指派給客戶的收帳案例或將此欄位保持空白。 如果已選擇一個案例，則此表單中只會顯示與該案例相關的交易和活動。  
5. 選取 **顯示清單**。
- 選擇一個客戶帳戶或接受預設分錄。 在該清單頁面或您所開啟表單中所選的客戶帳戶為預設帳戶。 如果在清單頁面開啟該表單，則清單中的客戶就是在該清單頁面中所用收帳群的客戶。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]