---
title: 波蘭 Intrastat
description: 本主題包含有關波蘭 Intrastat 回報的資訊。
author: andosip
ms.date: 11/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: 9564892f768adb8f48208fe10b31c7c6392a4567
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2021
ms.locfileid: "8451182"
---
# <a name="polish-intrastat"></a>波蘭 Intrastat

[!include[banner](../includes/banner.md)]

這 **內部統計** 頁面用於生成和報告有關歐盟 (EU) 國家之間貿易的資訊。 波蘭 Intrastat 申報包含有關貨物貿易的資訊以供報告。

以下欄位包含在波蘭內部統計聲明中： 所有欄位都包含在到達和發貨中，除了 **羅扎伊運輸公司** (運輸方式) 和 **KrajPochodzenia** (原產國或地區) 未包含在快件中，以及 **IdKontrahenta** (客戶的外國增值稅號) 不包括在到達時。

| 欄位名稱 | 描述 |
|-------------------------|-------------------------|
| Deklaracja 數據 | 單據的建立日期。 |
| Miesiac | 申報的參考月份。 |
| Rok | 申報的參考月份。 |
| Numer | 參考期內的申報編號。 |
| Wersja | 聲明的版本編號。 |
| NrWlasny | 聲明識別碼。 該值是自動生成的。 |
| 類型 | 報告方向。</br><li>對於到達，列印「P」。</li><li>對於調度，列印「W」。</li> |
| 羅扎伊 | 聲明的類型。 該值指示報告是原始聲明還是更正聲明。 |
| 加州大學 | Intrastat 聲明所針對的單位代碼。 該值在 **免稅編號** 中的欄位 **銷售稅** 部分 **代理人** 的索引標籤 **外貿參數** 頁。 |
| Nazwa | 公司名稱。 |
| Miejscowosc、UlicaNumer、KodPocztowy | 商家的完整地址 |
| Nip | 波蘭稅號 (增值稅 [VAT] ID) 。 |
| Regon | 波蘭統計標識號 (企業號) 。 |
| LacznaWartoscFaktur | 發票值的總和。 |
| LacznaWartoscStatystyczna | 統計值的總和。 |
| LacznaLiczbaPozycji | 商品項目的總數。 |
| PozId | 給定商品的連續編號。 |
| OpisTowaru | 商品的交易名稱。 |
| KrajPochodzeniaWysylki | 交易對手所在國家或地區的國際標準化組織 (ISO) 代碼。 |
| WarunkiDostawy | 交貨條款的 Intrastat 代碼。 |
| RodzajTransakcji | 指示交易性質的代碼。 波蘭公司使用兩位數的交易代碼。 |
| KodTowarowy | 根據組合命名法的八位商品代碼。 |
| 羅扎伊運輸公司 | 運輸方式的 Intrastat 代碼。 |
| KrajPochodzenia | 生產或製造商品的國家或地區的 ISO 代碼。 |
| MasaNetto | 以整公斤為單位的淨質量。 |
| IloscUzupelniajacaJm | 補充計量單位中的數量，以整數表示。 |
| WartoscFaktury | 一個項目涵蓋的所有交易的發票價值。 |
| WartoscStatystyczna | 統計值。 |
| Wypelniajacy：NazwiskoImie、Telefon、Faks、電子郵件 | 提交聲明的人的姓名、電話號碼、傳真號碼和電子郵件地址。 |
| IdKontrahenta | 客戶在歐盟成員國的外國增值稅號。 |


## <a name="set-up-intrastat"></a>安排 Intrastat

從全局存放庫中，匯入以下電子申報 (ER) 配置的最新版本：

   - 內部統計模型
   - Intrastat 報表
   - Intrastat (PL)

關於詳細資訊，請參閱[從設定服務的全域存放庫下載 ER 設定](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)。

## <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>為您的公司設置增值稅號和企業編號

### <a name="create-registration-types-for-company-codes"></a>為公司代碼創建註冊類型

您必須為公司代碼創建兩種註冊類型：一種用於增值稅 ID (NIP 代碼) ，另一種用於企業編號 (Regon 代碼) 。

1. 去 **組織管理** > **全球通訊錄** > **註冊類型** > **註冊類型**。
2. 在操作窗格上，選擇 **新的** 為增值稅 ID 創建註冊類型。
3. 在裡面 **輸入註冊類型詳細資訊** 對話框，在 **姓名** 欄位，輸入新註冊類型的名稱。 例如，輸入 **NIP**。
4. 在裡面 **國家/地區** 欄位，選擇 **POL**。
5. 選取 **建立**。
6. 在操作窗格上，選擇 **新的** 為企業編號創建註冊類型。
7. 在裡面 **輸入註冊類型詳細資訊** 對話框，在 **姓名** 欄位，輸入新註冊類型的名稱。 例如，輸入 **Regon**。
8. 在裡面 **國家/地區** 欄位，選擇 **POL**。
9. 選取 **建立**。

### <a name="match-the-registration-types-with-registration-categories"></a>將註冊類型與註冊類別匹配

1. 去 **組織管理** > **全球通訊錄** > **註冊類型** > **註冊類別**。
2. 在操作窗格上，選擇 **新的** 在您創建的每個註冊類型和註冊類別之間創建鏈接。

    - 對於增值稅 ID (NIP 代碼) 的註冊類型，選擇 **增值稅號** 註冊類別。
    - 企業號 (Regon code) 的註冊類型選擇 **企業 ID (COID)** 註冊類別。

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>為您的公司設置增值稅號和企業編號

1. 前往 **組織管理**  >  **組織**  >  **法人實體**。
2. 在網格中，選擇您的公司。
3. 在動作窗格上，選擇 **註冊識別碼**。
4. 選取 **註冊識別碼** FastTab 上的 **新增**。
5. 在裡面 **註冊類型** 欄位中，選擇您之前創建的註冊類型之一。
6. 根據您在上一步中選擇的註冊類型，輸入您公司的增值稅 ID (NIP 代碼) 或企業編號 (Regon 代碼) 。
7. 對您之前創建的其他註冊類型重複步驟 4 到 6。

## <a name="set-up-a-company-address"></a>設定公司地址

1. 前往 **組織管理**  >  **組織**  >  **法人實體**。
2. 在網格中，選擇您的公司。
3. 請在 **地址** 索引標籤上選取 **編輯**。
4. 在裡面 **編輯地址** 對話框，在 **郵編/郵政編碼** 欄位，選擇您公司的郵政編碼。
5. 在裡面 **街道** 欄位，輸入您的地址。
6. 在 **城市** 欄位中選擇您的程式。

## <a name="set-up-foreign-trade-parameters"></a>設置外貿參數

1. 前往 **稅務** > **設置** > **外貿參數**。
2. 在 **電子報告** FastTab，在 **文件格式映射** 欄位，在 **Intrastat** 索引標籤選擇 **Intrastat (PL)**。
3. 在 **報告格式映射** 欄位，選擇 **Intrastat 報告**。
4. 在裡面 **商品代碼層次結構** FastTab，在 **類別層次結構** 欄位，選擇 **內部統計**。
5. 在 **交易代碼** 欄位中，選擇房產轉讓的交易代碼。 您將此代碼用於產生實際或計劃的財產轉移以補償 (財務或其他) 的交易。 您還可以使用它進行更正。 波蘭的公司使用兩位數的交易代碼。
6. 在 **信用票據** 欄位中，選擇退貨的交易代碼。
7. 在 **國家/地區財產** 索引標籤上的 **國家/地區** 欄位中，列出與貴公司有業務往來的所有國家或地區。 對於屬於歐盟的每個國家，在 **國家/地區類型** 欄位，選擇 **歐盟**，以便國家/地區出現在您的 Intrastat 報告中。 針對波蘭地區，在 **國家/地區** 類型中，選擇 **國內**。
8. 在 **代理人** 索引標籤，在 **代理人** FastTab，在 **銷售稅** 部分，在 **免稅編號** 欄位，輸入 **420000** 指示 Intrastat 聲明所針對的單位代碼。
9. 在 **連絡人** 索引標籤上，輸入提交聲明的人的姓名、電話號碼、傳真號碼和電子郵件地址。
10. 在 **編號規則** 索引標籤，在 **編號順序代碼** 欄位為 **XML 文件編號** 參考，指定一個最多有九個字符的非連續數字序列。 該欄位用於自動生成一個值 **聲明標識符** Intrastat 報告中的欄位。

## <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>為 Intrastat 聲明設置產品參數

1. 前往 **產品資訊管理** > **產品** > **已發佈的產品**。
2. 在網格中選擇一個產品。
3. 在 **外貿** FastTab，在 **內部統計** 部分，在 **商品** 欄位，選擇適當的商品代碼。 商品名稱將印在 **商品說明** Intrastat 報告中的欄位。
4. 在裡面 **起源** 部分，在 **國家/地區** 欄位，選擇產品的原產國家或地區。
5. 在 **管理庫存** FastTab 的 **淨重** 欄位中，輸入產品的重量 (以公斤為單位)。

## <a name="set-up-compression-of-intrastat"></a>設定 Intrastat 的壓縮

-   前往 **稅務** > **設置** > **外貿** > **內部統計的壓縮**，並選擇在匯總 Intrastat 資訊時應比較的欄位。 對於波蘭內部統計，選擇以下欄位：

    - 商品
    - 交易代碼
    - 原產地國家/地區
    - 運輸
    - 交貨條件
    - 寄件者國家/地區
    - 國家/地區
    - 修正
    - 免稅編號
    - 方向
    - 發票

## <a name="set-up-the-transport-method-and-delivery-terms"></a>設置運輸方式和交貨條款

1.  設定傳輸代碼。

    1. 去 **稅** > **設置** > **外貿** > **傳輸方式**。
    2. 在動作窗格上，選擇 **新建**。
    3. 在裡面 **運輸** 欄位，輸入唯一代碼。 波蘭公司使用單位數的傳輸代碼。

2.  設定交貨 Intrastat 代碼。

    1. 去 **採購和採購** > **設置** > **分配** > **遞送條款**。
    2. 在網格中，選擇交貨條款集。
    3. 在 **一般** FastTab 的 **Intrastat** 代碼欄位中，輸入獨特代碼。

## <a name="intrastat-transfer"></a>Intrastat 轉移

在 **Intrastat** 頁面中，您可以選擇 **轉移** 從您的銷售訂單、普通發票、採購訂單、供應商發票、供應商產品收據、項目發票和轉移訂單中自動傳輸有關社區內貿易的資訊。 只有將歐盟國家作為目的地國家或地區或託運的文件才會被轉移。

您也可以通過選擇手動輸入交易 **新的** 在操作窗格上。

### <a name="generate-an-intrastat-report"></a>產生 Intrastat 報表

1. 進入 **稅務** > **申報** > **外貿** > **Intrastat**。
2. 在動作窗格上，選擇 **輸出** &gt; **報告**。
3. 在裡面 **內部統計報告** 對話框中，設置以下欄位。

    | 欄位 | 描述 |
    |-------------------------|-------------------------|
    | 開始日期 | 選取報表的開始日期。 |
    | 產生檔案 | 將此選項設定為 **是**，為您的 Intrastat 報告生成 xml 文件。 |
    | 檔案名稱 | 輸入 xml 檔案名稱。 |
    | 產生報表 | 將此選項設定為 **是**，為您的 Intrastat 報告生成 xlsx 檔案。 |
    | 報表檔案名稱 | 輸入 xlsx 檔案名稱。 |
    | 方向 | 選擇 **到達** 獲取有關社區內到達的報告。</br>選擇 **派遣** 獲取有關社區內調度的報告。 |
    | 聲明識別碼 | 文檔 ID 會自動生成並且可以更新。 |
    | 申報類型 | 選擇 **宣言** 原始聲明。</br>選擇 **聲明更正 - 替換** 對於旨在完全取代現有的、先前提交的原始或更正聲明的更正聲明。 |
    | 文件創建城市 | 輸入應列印的值 **米耶斯科沃斯克** Intrastat 聲明中的欄位。 |
    | 文件創建日期 | 輸入應列印的值 **Deklaracja Data** Intrastat 聲明中的欄位。 |
    | 文件編號 | 輸入應列印的值 **Numer** Intrastat 聲明中的欄位。 |
    | 文件版本 | 輸入應列印的值 **Wersja** Intrastat 聲明中的欄位。 |

4. 選擇 **確定**，並檢閱生成的報告。

## <a name="example"></a>範例 

此示例顯示如何使用 Intrastat 過帳到達和發貨 **DEMF** 法人實體。

### <a name="preliminary-setup"></a>初步設置

匯入以下 ER 配置的最新版本：

   - 內部統計模型
   - Intrastat 報表
   - Intrastat (PL)

### <a name="set-up-a-company-address"></a>設定公司地址

1. 去 **組織管理** > **全球通訊錄** > **地址** > **地址設置**。
2. 請在 **城市** 索引標籤上選取 **新增**。
3. 在裡面 **國家/地區** 欄位，選擇 **POL**。
4. 在 **城市** 欄位中，輸入 **Warsaw**。
5. 在 **郵編/郵政編碼** 索引標籤上，選取 **新建**。
6. 在裡面 **國家/地區** 欄位，選擇 **POL**。
7. 在 **城市** 欄位中，選擇 **Warsaw**。
8. 在 **郵編/郵政編碼** 欄位中，輸入 **00-844**。
9. 去 **組織管理** > **組織** > **法人實體**，並選擇 **DEMF** 法人實體。
10. 請在 **地址** FastTab 上選取 **編輯**。
11. 在裡面 **國家/地區** 欄位，選擇 **POL**。
12. 在 **郵編/郵政編碼** 欄位中，選擇 **31-111**。
13. 在裡面 **街道** 欄位，輸入 **Statystyczna 22/1**。
14. 在 **城市** 欄位中，選擇 **Warsaw**。
15. 選擇 **確定**。

## <a name="set-up-a-vat-id-and-an-enterprise-number-code-for-your-company"></a>為您的公司設置增值稅號和企業編號代碼

### <a name="create-registration-types-for-company-codes"></a>為公司代碼創建註冊類型

1. 去 **組織管理** > **全球通訊錄** > **註冊類型** > **註冊類型**。
2. 在操作窗格上，選擇 **新的** 為增值稅 ID (NIP 代碼) 創建註冊類型。
3. 在裡面 **輸入註冊類型詳細資訊** 對話框，在 **姓名** 欄位，輸入 **NIP**。
4. 在裡面 **國家/地區** 欄位，選擇 **POL**。
5. 選取 **建立**。
6. 在操作窗格上，選擇 **新的** 為企業編號 (Regon 代碼) 創建註冊類型。
7. 在裡面 **輸入註冊類型詳細資訊** 對話框，在 **姓名** 欄位，輸入 **Regon**。
8. 在裡面 **國家/地區** 欄位，選擇 **POL**。
9. 選取 **建立**。

### <a name="match-the-registration-types-with-registration-categories"></a>將註冊類型與註冊類別匹配

1. 去 **組織管理** > **全球通訊錄** > **註冊類型** > **註冊類別**。
2. 在操作窗格上，選擇 **新的** 在您創建的每個註冊類型和註冊類別之間創建鏈接。

    - 對於 **NIP** 的註冊類型，選擇 **增值稅號** 註冊類別。
    - 對於 **Regon** 的註冊類型，選擇 **企業識別碼 (COID)** 註冊類別。

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>為您的公司設置增值稅號和企業編號

1. 前往 **組織管理**  >  **組織**  >  **法人實體**。
2. 在格線中，選擇 **DEMF**。
3. 在動作窗格上，選擇 **註冊識別碼**。
4. 選取 **註冊識別碼** FastTab 上的 **新增**。
5. 在 **註冊類型** 欄位中，選取 **NIP**。
6. 在 **註冊編號** 欄位中，輸入 **1234567890**。
7. 選取 **新增**。
8. 在 **註冊類型** 欄位中，選取 **Regon**。
9. 在 **註冊編號** 欄位中，輸入 **12345678901234**。

### <a name="set-up-a-number-sequence-code"></a>設置編號規則代碼

1. 前往 **組織管理** > **編號序列** > **編號序列**。
2. 在動作窗格上的 **編號序列** 索引標籤上的 **新增** 群組中，選取 **編號序列**。
3. 在 **鑑別** FastTab，在 **編號順序代碼** 欄位，輸入 **XML\_文件**。
4. 在 **範圍參數** FastTab 上，在 **範圍** 欄位中，選擇 **公司**。
5. 在 **公司** 欄位中，選擇 **DEMF**。
6. 在 **細分市場** FastTab，在 **長度** 欄位為 **字母數字** 段，輸入 **4**。
7. 在 **一般的** FastTab，在 **設置** 部分，設置 **連續** 選項 **否**。
8. 在裡面 **號碼分配** 部分，在 **最大的** 欄位，輸入 **9999**。

### <a name="set-up-foreign-trade-parameters"></a>設置外貿參數

1. 進入 **稅收** > **設置** > **外貿** > **外貿參數**。
2. 在 **Intrastat** 索引標籤，在 **一般** 的 FastTab，在 **交易** **代碼** 欄位，選擇 **11**。
3. 在 **電子報告** FastTab，在 **文件格式映射** 欄位，選擇 **Intrastat (PL)**。
4. 在 **報告格式映射** 欄位，選擇 **Intrastat 報告**。
5. 在裡面 **商品代碼層次結構** FastTab，在 **類別層次結構** 欄位，選擇 **內部統計**。
6. 在 **國家/地區屬性** 索引標籤，選擇 **新的**。
7. 在裡面 **合作夥伴國家/地區** 欄位，選擇 **POL**。 **國家/地區** 類型，選擇 **國內**。
8. 在裡面 **合作夥伴國家/地區** 欄位，選擇 **DEU**。 **國家/地區** 類型，選擇 **EU**。
9. 在 **代理程式** 索引標籤上，在 **代理程式** FastTab 上，在 **銷售稅務** 部分，在 **免稅號** 欄位中，輸入 **420000**。
10. 在 **接觸** 索引標籤，在 **姓名** 欄位，輸入 **馬尼什·喬普拉**。
11. 在 **電話** 欄位中，輸入 **425-555-5068**。
12. 在 **傳真號碼** 欄位中，輸入 **425-555-5049**。
13. 在 **電子郵件** 欄位中，輸入 **manishc@contoso。com**。
14. 在 **編號規則** 索引標籤，在 **編號順序代碼** 欄位為 **XML 文件編號** 參考，選擇 **XML\_文件**。

### <a name="set-up-product-information"></a>設定產品資訊

1. 前往 **產品資訊管理** > **產品** > **已發佈** 的 **產品**。
2. 在格線中，選擇 **D0001**。
3. 在 **外貿** FastTab，在 **Intrasta** 部分，在 **商品** 欄位，選擇 **100 200 30**。
4. 在 **管理庫存** 快速索引標籤，在 **重量測量值** 部分，在 **淨重** 欄位，輸入 **2**。
5. 在動作窗格上，選擇 **儲存**。
6. 在格線中，選擇 **D0003**。
7. 在 **外貿** FastTab，在 **Intrasta** 部分，在 **商品** 欄位，選擇 **100 200 30**。
8. 在裡面 **起源** 部分，在 **國家/地區** 欄位，選擇 **德國**。
9. 在 **管理庫存** 快速索引標籤，在 **重量測量值** 部分，在 **淨重** 欄位，輸入 **5**。
10. 在動作窗格上，選擇 **儲存**。

### <a name="change-the-site-address"></a>更改網站地址

1. 前往 **倉庫管理** > **設定** > **倉庫** > **站點**。
2. 在格線中，選擇 **1**。
3. 請在 **地址** FastTab 上選取 **編輯**。
4. 在下拉式對話方塊中，在 **編輯地址** 名稱欄位中，輸入 **國家/地區** 欄位，選擇 **POL**。
5. 選擇 **確定**。

### <a name="set-up-a-transport-method"></a>設定運輸方式

1. 建立運輸模式。

    1. 去 **稅** > **設置** > **外貿** > **傳輸方式**。
    2. 在動作窗格上，選擇 **新建**。
    3. 在 **傳輸** 欄位中，輸入 **3**。
    4. 在 **描述** 欄位中，輸入 **陸運**。

2. 為交貨方式指定新的運輸方式。 通過這種方式，您可以設置在選擇相應的交付方式時用於運輸方式的預設值。

    1. 去 **採購和採購** > **設置** > **分配** > **遞送模式**。
    2. 在格線中，選擇 **10**。
    3. 在 **傳輸** FastTab，在 **NGP** 欄位，選擇 **3**。

3. 為客戶選擇預設的交貨方式。

    1. 前往 **應收帳款** > **客戶** > **所有客戶**。
    2. 在格線中，選擇 **DE-016**。
    3. 在 **發票和交付** FastTab，在送貨部分，在 **交貨方式** 欄位，選擇 **10**。

4. 為廠商選擇預設的交貨方式。

    1. 進入 **應付帳款** > **供應商** > **所有供應商**。
    2. 在格線中，選擇 **DE-001**。
    3. 在 **發票和交付** FastTab，在送貨部分，在 **交貨方式** 欄位，選擇 **10**。

### <a name="set-up-codes-for-terms-of-delivery"></a>設置交貨條款代碼

1. 為交貨條款設置 Intrastat 代碼。

    1. 去 **採購和採購** > **設置** > **分配** > **遞送條款**。
    2. 在格線中，選擇 **CIF**。
    3. 在 **一般** FastTab 的 **Intrastat 代碼** 欄位中，輸入 **CIF**。

2. 為客戶選擇預設的交貨條款。

    1. 前往 **應收帳款** > **客戶** > **所有客戶**。
    2. 在格線中，選擇 **DE-016**。
    3. 在 **發票和交付** FastTab，在送貨部分，在 **交貨條款** 欄位，選擇 **CIF**。

3. 為廠商選擇預設的交貨條款。

    1. 進入 **應付帳款** > **供應商** > **所有供應商**。
    2. 在格線中，選擇 **DE-001**。
    3. 在 **發票和交付** FastTab，在送貨部分，在 **交貨條款** 欄位，選擇 **CIF**。

### <a name="verify-an-eu-customers-tax-exempt-number-code"></a>驗證歐盟客戶的免稅號碼代碼

1. 前往 **應收帳款** > **客戶** > **所有客戶**。
2. 在格線中，選擇 **DE-016**。
3. 在 **發票和交貨** FastTab，在 **銷售稅** 部分，在 **免稅編號** 欄位，選擇 **DE9012**。

### <a name="create-a-sales-order-with-an-eu-customer"></a>與歐盟客戶創建銷售訂單

1. 前往 **應收帳款** > **訂單** > **所有銷售訂單**。
2. 在動作窗格上，選擇 **新建**。
3. 在 **建立銷售訂單** 對話方塊，在 **客戶** FastTab，在 **客戶帳戶** 的 **客戶** 區塊欄位選取 **DE-016**。
4. 在 **一般** 的 FastTab，在 **存儲尺寸** 部分，在 **地點** 欄位，選擇 **1**。
5. 請在 **倉庫** 欄位，選取 **11**。
6. 在 **地址** 索引標籤，驗證 **地址** 欄位設置為 **Teichgasse 12, 基爾，24103, DEU**，因為客戶來自德國。
7. 選擇 **確定**。
8. 在 **標題** 索引標籤，在 **送貨** FastTab，驗證 **交貨條件** 欄位設置為 **到岸價**, 和 **交貨方式** 欄位設置為 **10**。
9. 在 **行** 索引標籤上，在 **銷售訂單行** FastTab，在 **項目編號** 欄位，選擇 **D0001**。 然後，在 **數量** 欄位中，輸入 **8**。
10. 在 **線路詳情** FastTab，在 **外貿** 索引標籤，驗證 **交易代碼** 欄位設置為 **11**，這 **商品** 欄位設置為 **100 200 30**, 和 **原產國/地區** 欄位設置為 **波蘭**。
11. 在動作窗格上，選擇 **儲存**。
12. 在動作窗格的 **發票** 索引標籤上，在 **產生** 群組中選取 **發票**。
13. 在裡面 **過帳發票** 對話框，在 **參數** 快速索引標籤，在 **範圍** 部分，在 **數量** 欄位，選擇 **全部**。
14. 在 **設置** FastTab，在 **銷售日期** 欄位，選擇 **10/18/2021** (2021 年 10 月 18 日)。
15. 選擇 **確定** 以過帳發票。

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>將交易轉移到 Intrastat 日記帳並查看結果

1. 進入 **稅務** > **申報** > **外貿** > **Intrastat**。
2. 在動作窗格上，選取 **傳輸**。
3. 在裡面 **Intrastat (傳輸)** 對話框，在 **參數** 區塊設定 **客戶發票** 選項 **是的**。
4. 選取 **篩選**。
5. 在裡面 **內部統計過濾器** 對話框，在 **範圍** 索引標籤，選擇第一行，並驗證 **場地** 欄位設置為 **日期**。
6. 在裡面 **標準** 欄位，選擇當前日期。
7. 選擇 **確定**，以關閉 **Intrastat 篩選** 對話框。
8. 選擇 **OK** 關閉 **Intrastat (傳輸)** 對話框，然後查看結果。 該行代表您之前創建的銷售訂單。

    ![代表 Intrastat 頁面上的銷售訂單的行](media/intrastat_pl_1.png)

9. 選擇交易行，然後選擇 **一般** 的索引標籤以查看更多詳細資訊。

    ![Intrastat 頁面的常規索引標籤上的銷售訂單詳細資訊](media/intrastat_pl_2.png)

10. 在動作窗格上，選擇 **輸出**  >  **報告**。
11. 在 **Intrastat 報告** 對話框，在 **參數** FastTab，在 **日期** 部分，在 **來源日期** 欄位，選擇當月的第一天。
12. 在裡面 **匯出** **選項** 部分，設置 **生成檔案** 選項 **是的**。 然後，在 **檔案名稱** 欄位中，輸入必要名稱。
13. 將 **產生報表** 選項設為 **是**。 然後，在 **報告檔案名稱** 欄位中，輸入必要名稱。
14. 在 **方向** 欄位中，選擇 **Dispatches**。
15. 在裡面 **文件格式映射** 部分，驗證 **申報類型** 欄位設置為 **宣言**。
16. 在裡面 **文件創建城市** 欄位，輸入 **克拉科夫**。
17. 在裡面 **文件創建日期** 欄位，選擇 **2021 年 10 月 19 日** (2021 年 10 月 19 日) 。
18. 在 **文件編號** 欄位中，輸入 **11**。
19. 在 **文件版本** 欄位中，輸入 **22**。
20. 選擇 **好的**，並查看生成的 XML 格式的報告。 下表顯示了示例報告中的值。

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>欄位名稱</strong></p>
    </td>
    <td>
    <p><strong>欄位說明</strong></p>
    </td>
    <td>
    <p><strong>值</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>有關文件的資訊</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja 資料</p>
    </td>
    <td>
    <p>單據的建立日期。</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>創建文件的城市。</p>
    </td>
    <td>
    <p>Krakow</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>項目總數。</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>總統計值。</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>總發票值。</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>加州大學</p>
    </td>
    <td>
    <p>單位代碼。</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>聲明的類型。</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>文件版本。</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>文件編號。</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="330">
    <p>參考月份。</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="330">
    <p>參考年分。</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>類型</p>
    </td>
    <td width="330">
    <p>報告方向。</p>
    </td>
    <td>
    <p>W</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="330">
    <p>聲明識別碼。</p>
    </td>
    <td>
    <p>21ISTDEMF-0001</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>有關公司的資訊</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="330">
    <p>公司所在城市。</p>
    </td>
    <td>
    <p>Warsaw</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="330">
    <p>公司的 Regon 代碼。</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>公司的 NIP 代碼。</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>公司的 ZIP/郵政代碼。</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>公司所在街道。</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>公司名稱。</p>
    </td>
    <td>
    <p>Contoso 娛樂系統德國</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>關於商品的資訊</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>統計值。</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>發票值。</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>淨質量。</p>
    </td>
    <td>
    <p>16</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>IdKontrahenta</p>
    </td>
    <td>
    <p>客戶增值稅編號。</p>
    </td>
    <td>
    <p>DE9012</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>商品碼。</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>交易代碼。</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>交貨方式的條款。</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>發送/目的地國家或地區的代碼。</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>商品的描述。</p>
    </td>
    <td>
    <p>硬體</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>品項數。</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>連絡資訊</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>電子郵件</p>
    </td>
    <td>
    <p>提交者的電子郵件地址。</p>
    </td>
    <td>
    <p>manishc@contoso。com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>提交者的傳真號碼。</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>提交者的電話號碼。</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>提交者的姓名。</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

21. 查看生成的 Excel 格式的報告。

    ![Intrastat 發貨報告](media/intrastat_pl_3.png)

### <a name="create-a-purchase-order"></a>建立採購訂單

1. 請前往 **應付帳款** > **訂購單** > **所有訂購單**。
2. 在動作窗格上，選擇 **新建**。
3. 在 **建立訂購單** 對話方塊的 **廠商帳戶** 上，於廠商帳戶欄位選擇 **DE-001**。
4. 請在 **站點** 欄位，選擇 **1**。
5. 請在 **倉庫** 欄位，選取 **11**。
6. 選擇 **確定**。
7. 在 **標題** 索引標籤，在 **送貨** FastTab，驗證 **交貨條件** 欄位設置為 **10**，並且 **交貨條款** 欄位設定為 **CIF**。
8. 在 **行** 索引標籤上，在 **購買訂單行** 快速索引標籤，在 **項目編號** 欄位，選擇 **D0003**。 然後，在 **數量** 欄位中，輸入 **6**。
9. 在 **線路詳情** FastTab，在 **外貿** 索引標籤，驗證 **交易代碼** 設置為 **11**，**傳輸** 欄位設置為 **3**，此 **商品** 欄位設置為 **100 200 30**，和原產 **國家/地區** 欄位設置為 **DEU**。
10. 在動作窗格的 **採購** 索引標籤上，在 **動作** 群組中選取 **確認**。
11. 在動作窗格的 **發票** 索引標籤上，在 **產生** 群組中選取 **發票**。
12. 在操作窗格中，選擇 **預設來源**，然後在 **明細預設數量** 欄位中，選擇 **訂購數量**。 然後選取 **確定**。
13. 在 **供應商發票抬頭** 快速索引標籤，在 **發票識別** 部分，在 **數字** 欄位，輸入 **00010**。
14. 在裡面 **發票日期** 部分，在 **發票日期** 欄位，選擇目前日期。 該日期將用於 Intrastat 轉賬。
15. 在裡面 **接收文件日期** 欄位，選擇 **2021 年 10 月 18 日** (2021 年 10 月 18 日) 。
16. 在動作窗格上，選擇 **過帳** 發票。

### <a name="create-an-intrastat-declaration-for-arrivals"></a>為到達創建 Intrastat 申報

1. 進入 **稅務** > **申報** > **外貿** > **Intrastat**。
2. 在動作窗格上，選取 **傳輸**。
3. 在裡面 **Intrastat (轉讓)** 對話框，設置 **廠商發票** 選項 **是的**。
4. 選擇 **好的** 轉移交易，並查看 Intrastat 日記帳。

    ![代表 Intrastat 頁面上的購買訂單的行](media/intrastat_pl_4.png)

5. 查看有關資訊 **一般的** 採購訂單的索引標籤。

    ![Intrastat 頁面的常規索引標籤上的購買訂單詳細資訊](media/intrastat_pl_5.png)

6. 在動作窗格上，選擇 **輸出**  >  **報告**。
7. 在 **Intrastat 報告** 對話框，在 **參數** FastTab，在 **日期** 部分，在 **來源日期** 欄位，選擇當月的第一天。
8. 在裡面 **匯出** **選項** 部分，設置 **生成檔案** 選項 **是的**。 然後，在 **檔案名稱** 欄位中，輸入必要名稱。
9. 將 **產生報表** 選項設為 **是**。 然後，在 **報告檔案名稱** 欄位中，輸入必要名稱。
10. 在 **方向** 欄位中，選擇 **Arrivals**。
11. 在裡面 **文件格式映射** 部分，驗證 **申報類型** 欄位設置為 **宣言**。
12. 在裡面 **文件創建城市** 欄位，輸入 **克拉科夫**。
13. 在裡面 **文件創建日期** 欄位，選擇 **2021 年 10 月 19 日** (2021 年 10 月 19 日) 。
14. 在 **文件編號** 欄位中，輸入 **11**。
15. 在 **文件版本** 欄位中，輸入 **22**。
16. 選擇 **好的**，並查看生成的 XML 格式的報告。 下表顯示了示例報告中的值。

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>欄位名稱</strong></p>
    </td>
    <td>
    <p><strong>欄位說明</strong></p>
    </td>
    <td>
    <p><strong>值</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>有關文件的資訊</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja 資料</p>
    </td>
    <td>
    <p>單據的建立日期。</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>創建文件的城市。</p>
    </td>
    <td>
    <p>Krakow</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>項目總數。</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>總統計值。</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>總發票值。</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>單位代碼。</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>聲明的類型。</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>文件版本。</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>文件編號。</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="332">
    <p>參考月份。</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="332">
    <p>參考年分。</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>類型</p>
    </td>
    <td width="332">
    <p>報告方向。</p>
    </td>
    <td>
    <p>P</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="332">
    <p>聲明識別碼。</p>
    </td>
    <td>
    <p>21ISTDEMF-0002</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>有關公司的資訊</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="332">
    <p>公司所在城市。</p>
    </td>
    <td>
    <p>Warsaw</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="332">
    <p>公司的 Regon 代碼。</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>公司的 NIP 代碼。</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>公司的 ZIP/郵政代碼。</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>公司所在街道。</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>公司名稱。</p>
    </td>
    <td>
    <p>Contoso 娛樂系統德國</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>關於商品的資訊</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>統計值。</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>發票值。</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>淨質量。</p>
    </td>
    <td>
    <p>30</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzenia</p>
    </td>
    <td>
    <p>原產國或地區的代碼。</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>羅扎伊運輸公司</p>
    </td>
    <td>
    <p>運輸模式代碼。</p>
    </td>
    <td>
    <p>3</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>商品碼。</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>交易代碼。</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>交貨方式的條款。</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>發送/目的地國家或地區的代碼。</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>商品的描述。</p>
    </td>
    <td>
    <p>硬體</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>品項數。</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>連絡資訊</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>電子郵件</p>
    </td>
    <td>
    <p>提交者的電子郵件地址。</p>
    </td>
    <td>
    <p>manishc@contoso。com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>提交者的傳真號碼。</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>提交者的電話號碼。</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>提交者的姓名。</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

17. 查看生成的 Excel 格式的報告。

    ![入境統計報告](media/intrastat_pl_6.png)
