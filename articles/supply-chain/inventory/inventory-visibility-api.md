---
title: 庫存能見度公用 API
description: 本主題介紹庫存能見度提供的公用 API。
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f74bb4bd4ed66520c04261bd9f82faad7775817e
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449835"
---
# <a name="inventory-visibility-public-apis"></a>庫存能見度公用 API

[!include [banner](../includes/banner.md)]


本主題介紹庫存能見度提供的公用 API。

庫存能見度增益集的公用 REST API 提供了數個用於整合的特定端點。 它支援四種主要的互動類型：

- 從外部系統將現有庫存變更過帳到增益集
- 從外部系統設定或覆寫增益集中的現有庫存量
- 從外部系統將現有保留事件過帳到增益集
- 從外部系統查詢目前的現有數量

下表列出了目前可用的 API。

| 路徑 | 方法 | 描述 |
|---|---|---|
| /api/environment/{environmentId}/onhand | 張貼 | [建立一個現有變更事件](#create-one-onhand-change-event) |
| /api/environment/{environmentId}/onhand/bulk | 張貼 | [建立多個變更事件](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | 張貼 | [設定/覆寫現有數量](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | 張貼 | [建立一個保留事件](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | 張貼 | [建立多個保留事件](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/indexquery | 張貼 | [使用 post 方式查詢](#query-with-post-method) |
| /api/environment/{environmentId}/onhand | Get | [使用 get 方式查詢](#query-with-get-method) |

Microsoft 提供了一個立即可用的 *Postman* 要求集合。 您可以透過使用以下共用連結，將此集合匯入您的 *Postman* 軟體：<https://www.getpostman.com/collections/90bd57f36a789e1f8d4c>。

> [!NOTE]
> 路徑的 {environmentId} 部分是 Microsoft Dynamics Lifecycle Services (LCS) 中的環境識別碼。
> 
> 批量 API 最多可為每個要求傳回 512 條記錄。

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>根據您的 Lifecycle Services 環境尋找端點

庫存能見度的微服務部署在多個地理位置和多個區域的 Microsoft Azure Service Fabric 上。 目前沒有可以自動將您的請求重新導向到對應地理位置和區域的中心端點。 因此，您必須使用以下模式將一些資訊組合到 URL 中：

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

在 Microsoft Dynamics Lifecycle Services (LCS) 環境中可以找到地區的簡短名稱。 下表列出了目前可用的區域。

| Azure 區域        | 區域簡短名稱 |
| ------------------- | ----------------- |
| 澳洲東部      | eau               |
| 澳洲東南部 | seau              |
| 加拿大中部      | cca               |
| 加拿大東部         | eca               |
| 北歐        | neu               |
| 西歐         | weu               |
| 美國東部             | eus               |
| 美國西部             | wus               |
| 英國南部            | suk               |
| 英國西部             | wuk               |
| 東日本          | ejp               |
| 西日本          | wjp               |
| 巴西南部        | sbr               |
| 美國中南部    | scus              |

島嶼編號是 LCS 環境在 Service Fabric 上部署的位置。 目前沒有辦法從使用者端取得這些資訊。

Microsoft 已在 Power Apps 中建置了使用者介面 (UI)，以便您可以取得微服務的完整端點。 有關詳細資訊，請參閱[尋找服務端點](inventory-visibility-configuration.md#get-service-endpoint)。

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>驗證

平台安全性權杖用於調用庫存能見度公用 API。 因此，您必須透過使用您的 Azure AD 應用程式產生一個 _Azure Active Directory (Azure AD) 權杖_。 然後您必須使用 Azure AD 權杖以從安全服務取得 _存取權杖_。

Microsoft 提供了一個立即可用的 *Postman* 取得權杖集合。 您可以透過使用以下共用連結，將此集合匯入您的 *Postman* 軟體：<https://www.getpostman.com/collections/496645018f96b3f0455e>。

若要取得安全服務權杖，請執行以下步驟。

1. 登入到 Azure 入口網站，並使用它來尋找您 Dynamics 365 Supply Chain Management 應用程式的 `clientId` 和 `clientSecret` 值。
1. 透過提交具有以下屬性的 HTTP 要求擷取一個 Azure AD 權杖 (`aadToken`)：

   - **URL：**`https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
   - **方法：**`GET`
   - **本文內容 (表單資料)：**

     | 機碼           | 值                                |
     | ------------- | ------------------------------------ |
     | client_id     | ${aadAppId}                          |
     | client_secret | ${aadAppSecret}                      |
     | grant_type    | client_credentials                   |
     | 資源      | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |

   您應該會收到一個 Azure AD 權杖 (`aadToken`) 作為回應。 其應該會類似於以下範例。

   ```json
   {
       "token_type": "Bearer",
       "expires_in": "3599",
       "ext_expires_in": "3599",
       "expires_on": "1610466645",
       "not_before": "1610462745",
       "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
       "access_token": "eyJ0eX...8WQ"
   }
   ```

1. 制訂類似於以下範例的 JavaScript 物件標記法 (JSON) 請求。

   ```json
   {
       "grant_type": "client_credentials",
       "client_assertion_type": "aad_app",
       "client_assertion": "{Your_AADToken}",
       "scope": "https://inventoryservice.operations365.dynamics.com/.default",
       "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
       "context_type": "finops-env"
   }
   ```

   請注意以下幾點：

   - `client_assertion` 值必須是您在前一步驟中收到的 Azure AD 權杖 (`aadToken`)。
   - `context` 值必須是要部署增益集位置的 LCS 環境識別碼。
   - 設定所有其他值，如範例中所示。

1. 透過提交具有以下屬性的 HTTP 要求擷取一個存取權杖 (`access_token`)：

   - **URL：**`https://securityservice.operations365.dynamics.com/token`
   - **方法：**`POST`
   - **HTTP 標頭：** 包括 API 版本。 (金鑰是 `Api-Version`，且值為 `1.0`。)
   - **本文內容：** 包括您在上一步中建立的 JSON 請求。

   您應該會收到一個存取權杖 (`access_token`) 作為回應。 您必須使用此權杖作為持有人權杖來呼叫庫存能見度 API。 範例如下。

   ```json
   {
       "access_token": "{Returned_Token}",
       "token_type": "bearer",
       "expires_in": 3600
   }
   ```

> [!IMPORTANT]
> 當您使用 *Postman* 要求集合以呼叫庫存能見度公用 API 時，您必須為每個要求新增一個持有人權杖。 如要尋找您的持有人權杖，請在請求 URL 下選擇 **授權** 索引標籤，選擇 **持有人權杖** 類型，然後複製在上一步中擷取的存取權杖。 在本主題的後續小節中，`$access_token` 將用於表示在最後一步驟中取得的權杖。

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>建立現有變更事件

有兩個 API 會用於建立現有變更事件：

- 建立一筆記錄：`/api/environment/{environmentId}/onhand`
- 建立多筆記錄：`/api/environment/{environmentId}/onhand/bulk`

下表總結了 JSON 本文中每個欄位的含義。

| 欄位 ID | 描述 |
|---|---|
| `id` | 特定變更事件的唯一識別碼。 此識別碼用於確保，如果在過帳期間與服務的通訊失敗，則重新提交相同的事件不會在系統中被計算兩次。 |
| `organizationId` | 連結到事件的組織識別碼。 此值對應到 Supply Chain Management 中的組織或資料區域識別碼。 |
| `productId` | 產品識別碼。 |
| `quantities` | 現有數量必須更改的數量。 例如，如果將 10 本新書新增到層架，則此值將是 `quantities:{ shelf:{ received: 10 }}`。 如果三本書從層架移除或出售，此值將為 `quantities:{ shelf:{ sold: 3 }}`。 |
| `dimensionDataSource` | 過帳變更事件和查詢中使用維度的資料來源。 如果您指定資料來源，則可以使用於自指定資料來源的自訂維度。 庫存能見度可以使用維度設定將自訂維度對應到一般預設維度。 如果 `dimensionDataSource` 值未指定，您只能在您的查詢中使用一般的[基本維度](inventory-visibility-configuration.md#data-source-configuration-dimension)。 |
| `dimensions` | 動態鍵值對。 這些值對應到 Supply Chain Management 中的部分維度。 但是，您也可以新增自訂維度 (例如，_來源_) 以指示事件是來自 Supply Chain Management 還是來自外部系統。 |

> [!NOTE]
> `SiteId` 和 `LocationId` 參數構成了[分割區設定](inventory-visibility-configuration.md#partition-configuration)。 因此，在您建立現有數量變更事件、設定或覆寫現有數量或建立保留事件時，您必須在維度中指定它們。

### <a name="create-one-on-hand-change-event"></a><a name="create-one-onhand-change-event"></a>建立一個現有變更事件

此 API 建立了單一現有變更事件。

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # Optional
        dimensions: {
            [key:string]: string,
        },
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
    }
```

以下範例顯示樣本本文內容。 在此樣本中，您為 *T 恤* 產品過帳了一筆變更事件。 此事件來自銷售點 (POS) 系統，客戶已將一件紅色 T 恤退回您的商店。 此事件將增加 1 件 *T 恤* 產品數量。

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "PosMachineId": "0001",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

以下範例顯示無 `dimensionDataSource` 的樣本本文內容。 在此情況下，`dimensions` 將為[基本維度](inventory-visibility-configuration.md#data-source-configuration-dimension)。 如果 `dimensionDataSource` 已設定，`dimensions` 可為資料來源維度或基本維度。

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>建立多個變更事件

此 API 可同時建立多筆記錄。 此 API 與[單一事件 API](#create-one-onhand-change-event) 唯一的不同，僅有 `Path` 和 `Body` 的值。 對於此 API，`Body` 提供了記錄陣列。 最大記錄數為 512，這代表現有變更大量 API 一次可以支援最多 512 筆變更事件。

```txt
Path:
    /api/environment/{environmentId}/onhand/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
        ...
    ]
```

以下範例顯示樣本本文內容。

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "Pants",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>設定/覆寫現有數量

_設定現有_ API 會覆寫指定產品的目前資料。

```txt
Path:
    /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifiedDateTimeUTC: datetime,
        },
        ...
    ]
```

以下範例顯示樣本本文內容。 此 API 的行為，與在本主題前面的[建立現有變更事件](#create-onhand-change-event)小節中描述的 API 行為不同。 在此樣本中，*T 恤* 產品數量將設為 1。

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
             "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId": "0001"
        },
        "quantities": {
            "pos": {
                "inbound": 1
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>建立保留事件

如要使用 *保留* API，您必須打開保留功能並完成保留設定。 如需更多詳細資訊，請參閱[保留設定 (選用)](inventory-visibility-configuration.md#reservation-configuration)。

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>建立一個保留事件

可以針對不同的資料來源設定進行保留。 如要設定這種類型的保留，首先請在 `dimensionDataSource` 參數指定資料來源。 然後，在 `dimensions` 參數中，根據目標資料來源中的維度設定指定維度。

在您呼叫保留 API 時，您可以透過指定要求本文中的 `ifCheckAvailForReserv` 布林值來控制保留驗證。 `True` 的值表示需要驗證，而 `False` 的值表示不需要驗證。 預設值為 `True`。

如果您要取消保留或取消保留指定的庫存數量，請將數量設為負值，然後將 `ifCheckAvailForReserv` 參數設為 `False` 以略過驗證。

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string,
        dimensions: {
            [key:string]: string,
        },
        quantityDataSource: string, # optional
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
        modifier: string,
        quantity: number,
        ifCheckAvailForReserv: boolean,
    }
```

以下範例顯示樣本本文內容。

```json
{
    "id": "reserve-0",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softreservordered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    }
}
```

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>建立多個保留事件

此 API 是[單一事件 API](#create-one-reservation-event) 的大量版本。

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifier: string,
            quantity: number,
            ifCheckAvailForReserv: boolean,
        },
        ...
    ]
```

## <a name="query-on-hand"></a>查詢現有

使用 _查詢現有_ API 以擷取您產品的目前庫存資料。 該 API 目前支援透過 `ProductID` 值查詢多達 100 項個別品項。 每個查詢中也可以指定多項 `SiteID` 和 `LocationID`。 最大限制定義為 `NumOf(SiteID) * NumOf(LocationID) <= 100`。

### <a name="query-by-using-the-post-method"></a><a name="query-with-post-method"></a>使用 post 方式查詢

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

在此要求的本文部分，`dimensionDataSource` 仍然是一個選用參數。 如果沒有設定，則 `filters` 將視為 *基本維度*。 `filters` 有四個必填欄位：`organizationId`、`productId`、`siteId`，和 `locationId`。

- `organizationId` 應該只包含一個值，但它仍然是一個陣列。
- `productId` 可以包含一或多個值。 如果是空陣列，則所有產品將退回。
- `siteId` 和 `locationId` 用於在庫存能見度中進行資料分割。 您可以在 *查詢現有* 要求中指定多個 `siteId` 和 `locationId` 值。 在目前版本中，您必須同時指定 `siteId` 和 `locationId` 值。

`groupByValues` 參數應遵循您的索引製作設定。 如需詳細資訊，請參閱[產品索引階層設定](./inventory-visibility-configuration.md#index-configuration)。

`returnNegative` 參數會控制結果是否包含負項目。

以下範例顯示樣本本文內容。

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "LocationId": ["11"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

以下範例展示如何查詢特定站點和位置中的所有產品。

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>使用 get 方式查詢

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

此處是一個樣本 get URL。 此 get 要求與之前提供的 post 樣本完全相同。

```txt
/api/environment/{environmentId}/onhand?organizationId=usmf&productId=T-shirt&SiteId=1&LocationId=11&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
