---
title: 最佳化 Dataverse 虛擬資料表查詢
description: Dataverse 虛擬資料表查詢的最佳化和故障排除的效能
author: andreabichsel
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1857d2e35e369bcd0c8f02a059a307f31da8b3b9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452355"
---
# <a name="optimize-dataverse-virtual-table-queries"></a>最佳化 Dataverse 虛擬資料表查詢


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>問題

### <a name="overview"></a>概觀

使用 Dataverse 虛擬資料表開發與其他 Dynamics 365 Human Resources 資料連接的虛擬資料表整合時，您可能會經歷針對虛擬資料表查詢的效能問題。 各種用戶端或介面之間會發生查詢執行速度緩慢的情況。 例如，您可能會經歷的問題與場合如下：

- 透過 Dataverse Web API 查詢虛擬資料表時
- 針對虛擬資料表建立 Power App 時
- 在虛擬資料表上建立 Power BI 報告時

所有這些介面都有可能面臨效能問題。

搭配人力資源 Dataverse 虛擬資料表的效能緩慢其中一項原因是與資料表的[導覽屬性](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties) 有關的虛擬資料表外部索引欄位。 針對虛擬資料表建立導覽屬性時，外部索引欄位會自動新增到資料表，代表相關虛擬資料表裡，鍵欄位的鍵值。 例如，**_mshr_fk_person_id_value** 欄位新增到 **mshr_hcmworkerbaseentity** 實體，外部索引鍵屬於取自 **mshr_dirpersonity** 實體。 由於資料表維護這些外部索引鍵欄位值方式緣故，取值會對虛擬資料表查詢效能產生負面影響。

### <a name="potential-symptoms"></a>潛伏徵兆

您可能會看到這種影響的範例是針對背景工作角色的查詢 (**mshr_hcmworker 實體**) 或基礎背景工作角色 (**mshr_hcmworkerbaseentity**) 實體。 您可能會看到效能問題出現幾種不同方式的表現：

- **查詢執行緩慢**：針對虛擬資料表的查詢可能會傳回預期的結果，但完成查詢的執行時間會比預期的長。
- **查詢逾時**：查詢可能會逾時並傳回錯誤如下："獲得權杖呼叫財務和營運，但財務和營運傳回 InternalServerError 類型的錯誤。"
- **意外錯誤**：查詢可能傳回錯誤類型 400，隨附訊息如下："發生意外錯誤。"

  ![HcmWorkerBaseEntity 上的錯誤類型 400。](./media/HcmWorkerBaseEntityErrorType400.png)

- **節流**：查詢可能過度使用伺服器資源，並月受到節流限制。 此時，查詢傳回錯誤如下："獲得權杖呼叫財務和營運，但財務和營運傳回類型 429 的錯誤。" 更多人力資源節流的資訊，請參閱[節流常見問答集](./hr-admin-integration-throttling-faq.md)。

  ![HcmWorkerBaseEntity 上的錯誤類型 429。](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a>解決方法

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a>限制納入資料查詢的欄位數

最有可能改善虛擬資料表查詢效能的其中一項方法是限制查詢中選取的欄位數。 最佳化查詢效能的一般指導是將查詢傳回的欄位數限制在只納入您需要的屬性。 這對於虛擬資料表的外部索引鍵欄位更是如此。 如果整合或報表不需要外部索引鍵欄位值，則建構查詢以只選取您需要的欄位為主，不包括外部索引鍵欄位。

#### <a name="selecting-columns-in-an-odata-query"></a>在 OData 查詢中選取欄位

透過 Dataverse Web API 查詢虛擬資料表時，您可以藉由 **$選取** 系統查詢選項和定義您需要傳回結果的欄位，限制納入查詢的欄位數。 為了將效能提高到最大，我們從查詢排除外部索引鍵欄位 (那些含有 **_mshr_FK_** 前綴字的欄位)。

例如，針對 **mshr_hcmworkerbaseentity** 實體的查詢將只包括 **$選取** 查詢選項子句的欄位，不包括外部索引鍵值。 對於包括所有資料表欄位的查詢而言，這提供明顯的效能。

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

限制選取欄位數的建議也適用在使用 **$展開** 查詢選項，透過導覽屬性擴大查詢範圍到相關的虛擬資料表。 例如，下列查詢包括欄位從 **mshr_dirpersonity** 實體展開的 **mshr_hcmworkerbaseentity** 實體欄位。 請注意，**$選取** 查詢選項也包括在 **$展開** 查詢選項子句以內。

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

當使用這套 **$選取** 查詢選項在 **$展開** 查詢選項子句內的檢索資料方法時，當實體之間的導覽屬性是多對一關係時，您通常會看到改善幅度更大的效能。 展開一對多關係時，您可能不會看到查詢執行時間同樣減少的情況。 更多 Dataverse 虛擬資料表關係定義的資訊，請參閱[資料表關係](/powerapps/maker/data-platform/create-edit-entity-relationships)。

更多使用 Dataverse Web API 的 **$選取** 和 **$展開** 系統查詢選項資訊，請參閱[使用查詢檢索相關實體記錄](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query)。

#### <a name="selecting-columns-in-power-bi"></a>選取 Power BI 欄位

如果您按照 Dataverse 虛擬資料表建構 Power BI 報表時經歷上述任何緩慢效能的情況，您可以藉由從報表資料表選取欄位排除外部索引鍵欄位改善效能。 例如，如果您正在使用 Power BI Desktop 按照 **mshr_hcmworkerbaseentity** 實體建立報表，您可以使用下列步驟選取您希望納入報表查詢的欄位。

1. 請在 Power BI Desktop 的動作功能區上，從 **取得資料** 下拉式清單選取 **更多...**。
2. 請在 **取得資料** 視窗的搜尋方塊內輸入 **Common Data Service**、選取 **Common Data Service** 連接器，然後選取 **連線**。
3. 請在 Common Data Service 視窗的 **伺服器網址** 欄位，輸入您的 Dataverse 環境組織 URl，然後選取 **確定**。
  
   ![輸入您的 Dataverse 環境 URl。](./media/PowerBIDataverseURLSetup.png)
  
4. 請在導覽器視窗展開 **實體** 節點。
5. 請在搜尋方塊輸入 **mshr_hcmworkerbaseentity**，然後選取實體。
6. 請選取 **轉換資料**。
7. 請在 Power Query 編輯器視窗中選取 **進階編輯器**。
8. 請在 **進階編輯器** 視窗中，將查詢更新為如下方的外觀，並按照需求新增或移除陣列裡的任何欄位。

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![請在進階編輯器中更新 Power Query 編輯器查詢功能。](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. 選取 **完成**。

   > [!NOTE]
   > 如果之前在更新之前從查詢收到類型 429 的錯誤，您可能需要等待重試期才能重新整理查詢，以便順利完成。

10. 點選 Power Query 編輯器操作功能區上的 **關閉和套用**。

接著您就可以開始根據從虛擬資料表選取的欄位建構您的 Power BI 報表。

#### <a name="selecting-columns-in-power-apps"></a>選取 Power Apps 欄位

與 Dataverse Web API 查詢和Power BI 類似，您可以藉由從您的 App 排除相關資料表欄位，根據 Dataverse 虛擬資料表改善 Power Apps 的查詢效能。 如果相關資料表的任何欄列已經新增到頁面，那麼為了獲取資料而建造的要求 URL 將包括相關資料表的外部索引鍵屬性。 如同上述的[在 OData 查詢中選取欄位](#selecting-columns-in-power-apps)範例，藉由額外的資料查閱功能降低效能。

若要處理這部份，您可以驗證您的 Power App 中，任何資料表單上是否一直不包括相關資料表的資料欄位。

1. 請在樹狀視圖窗格中選取螢幕資料表單。
2. 請在 **屬性** 窗格中的 **欄位** 屬性上選取 **編輯**。
3. 請在 **資料** 窗格中驗證選取欄位都不是資料來源的虛擬資料表欄位。

例如，如果 App 頁面包括的其中一個資料欄位參考另一個資料表，例如 **ThisItem.Worker.Name**，其中 **背景工作角色** 是相關資料表，則取得資料的效能可能會降低。

您可以使用 [Power Apps 監視器](/powerapps/maker/monitor-overview) 確保只有您需要的欄位才會納入查詢範圍取得 Power App 的資料。 您可以檢視專為 getRows 操作建構的 URL，確保您為 App 選取的欄位將最適合檢索資料。

![使用 Power Apps 監視器分析 getData 操作。](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a>篩選資料查詢

另一種改善查詢執行效能的方法是限制查詢結果傳回的記錄筆數。 您可以藉由篩選結果做到這一點，確保您只會收到您需要的記錄。

請參閱[篩選結果](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results)了解更多篩選查詢資料的資訊。

### <a name="limiting-the-page-size-of-the-query"></a>限制查詢的頁面大小

如果您正在處理大型資料集合，您可以藉由新增 `odata.maxpagesize` 偏好標頭到資料查詢將查詢結果分成數頁。

更多分頁資訊，請參閱[指明頁面傳回的實體數目](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page)。

## <a name="see-also"></a>也請參閱

- [配置 Dataverse 虛擬資料表](hr-admin-integration-common-data-service-virtual-entities.md)
- [人力資源虛擬資料表常見問答集](hr-admin-virtual-entity-faq.md)
- [節流常見問答集](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
