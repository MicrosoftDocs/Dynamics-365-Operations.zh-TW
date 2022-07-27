---
title: 創建新的運輸管理引擎
description: 本主題介紹如何在 Dynamics 365 Supply Chain Management 創建新的運輸管理引擎。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSGenericEngine, TMSRateEngine, TMSMileageEngine, TMSEngineParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 51661
ms.assetid: 0473acef-755e-4b42-acf5-5e5aa902dc0e
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88661b6a974e2bd60f78e38d49a08d3290008b8b
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2021
ms.locfileid: "8449391"
---
# <a name="create-a-new-transportation-management-engine"></a>創建新的運輸管理引擎

[!include [banner](../includes/banner.md)]

本主題介紹如何在 Dynamics 365 Supply Chain Management 創建新的運輸管理引擎。 

運輸管理 (TMS) 引擎定義運輸管理中，產生和處理運輸費率的邏輯。 Supply Chain Management 提供了幾種不同的引擎類型，可以計算不同的參數，例如﹔費率、運輸時間以及運輸過程中要穿越的區域數量。 本文說明如何使用 Microsoft Visual Studio 開發環境與 Supply Chain Management 開發工具，一起創建和部署新的 TMS 引擎，然後如何在作業中設定引擎。 如需有關引擎的詳細資料，請參閱[運輸管理引擎](transportation-management-engines.md)。

## <a name="create-a-new-tms-engine"></a>建立新的 TMS 引擎

本節說明如何創建 TMS 引擎實作類別庫，以及如何在 Supply Chain Management 模型中引用。

1. 若要部署新引擎，您必須有一個包含引擎的模型。 在 **Dynamics 365** &gt; **模型管理** 功能表，按一下 **創建模型**，以創建一個新模型。 在 **創建模型** 精靈的第一頁，將模型命名為 **TMSEngines**。 

   [![創建模型。](./media/012.png)](./media/012.png)

2. 在下一頁上，選擇 **創建封裝**。 

   [![創建一個新的封裝。](./media/021.png)](./media/021.png)

3. 在下一頁上，選擇參考的 **ApplicationSuite** 模型。 (**ApplicationPlatform** 模型是預選的。) 

   [![選擇要參考的模型。](./media/032.png)](./media/032.png)

4. 在下一頁上，按一下 **完成** 確認創建新模型。 

   [![完成模型創建。](./media/042.png)](./media/042.png)

5. 在一個新的解決方案中，創建一個新的 Supply Chain Management 項目，並將其命名 **TMSThirdParty**。 在項目屬性中，將項目的模型設定為 **TMSEngines**。
6. 新增一個新的 C\# 類別庫到您的解決方案中，並為其命名為 **ThirdPartyTMSEngines**。
7. 在 ThirdPartyTMSEngines 項目中，添加 Supply Chain Management 特定組件的參考：
   -   啟用參考 X++ 類型的應用程式組件。 可以在以下位置找到這些組件。 \[封裝根目錄\]是放置所有已部署組件的位置路徑，例如 C：\\Packages。

        ```xpp
        [Packages root]\ApplicationPlatform\bin\Dynamics.AX.ApplicationPlatform.dll
        [Packages root]\ApplicationFoundation\bin\Dynamics.AX.ApplicationFoundation.dll
        [Packages root]\ApplicationSuite\bin\Dynamics.AX.ApplicationSuite.dll
        ```
        
   -   啟用訪問數據、LINQ 和輔助功能的架構組件。 所有組件都可以在\[封裝根目錄\]\\ bin 中找到。

        ```xpp 
        Microsoft.Dynamics.ApplicationPlatform.Environment.dll
        Microsoft.Dynamics.AX.Data.Core.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.AdoNet.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Msil.dll
        Microsoft.Dynamics.AX.Server.Core.dll
        Microsoft.Dynamics.AX.Xpp.AxShared.dll
        Microsoft.Dynamics.AX.Xpp.Support.dll
        ```

   -   核心 TMS 組件 (包含引擎) 和 TMS 基本組件 (包含協助程式、常數、資料傳輸類別定義等)。 可以在以下位置找到這些組件。

        ```xpp
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.dll
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.Base.dll
        ```
8. 重新命名在 ThirdPartyTMSEngines 項目中自動生成於 **SampleRatingEngine** 的 C\# 類別。
9. 實作引擎。 因為在此範例中，我們正在創建費率引擎，所以我們沿用費率引擎的基本類別。 基本類別實作大部分的費率引擎介面 (**TMSFwkIRateEngine**)。 我們只需要實作費率方法。 為了保持範例簡單，我們為此方法註冊一個費率為 100 的硬式編碼。 您可以創建實作任何引擎介面的引擎，例如 **TMSFwkIAccessorialEngine**。 所有引擎介面都在 X++ 中定義。

    ```xpp
    namespace ThirdPartyTMSEngines
    {
        using Dynamics.AX.Application;
        using Microsoft.Dynamics.Ax.Tms.Base.Data;
        using Microsoft.Dynamics.Ax.Tms.Base.Utility;
        using Microsoft.Dynamics.Ax.Tms.Bll;
        using System.Xml.Linq;
        public class SampleRatingEngine : BaseRateEngine
        {
            public override RatingDto rate(TmsTransactionFacade transactionFacade, XElement shipment, TMSRateMasterCode rateMasterCode)
            {
               XElement re = shipment.RetrieveOrCreateRatingEntity(this.RatingDto);
               re.AddRate(TmsRateType.Rate, 100);
               return this.RatingDto;
            }
        }
    }
    ```

10. 組建解決方案。
11. 將新的參考添加到 TMSThirdParty 項目中。 參考應指向 ThirdPartyTMSEngines 項目。 完成後，您的解決方案應如下所示。 

    [![解決方案包括對 TMSThirdParty 項目的參考。](./media/052.png)](./media/052.png)

12. 組建解決方案。 驗證新資料庫是否出現在 Application Explorer 中的 **參考** 節點。 

    [![Application Explorer 的參考節點中的新資料庫。](./media/061.png)](./media/061.png)

## <a name="deploy-the-tms-engine-as-a-package"></a>將 TMS 引擎作為封裝部署

部署第三方 TMS 引擎的方法，是通過封裝部署。 此方法建議用於生產環境。 在開發環境中，您可以按照下一節「Supply Chain Management 中設定 TMS 引擎」的說明，手動複製組件。 若要將引擎作為封裝部署，請遵循以下步驟。

1. 在 **Dynamics 365** &gt; **部署** 功能表，按一下<strong>創建部署封裝</strong>。
2. 在 **創建部署封裝** 對話框中，選擇 TMSEngines 模型，然後輸入要儲存封裝檔案的路徑。 

   [![選擇 TMSEngines 模型。](./media/071.png)](./media/071.png)

3. 現在，您可以將封裝部屬到目標環境。 相關教學課程，請參閱[安裝部屬封裝 ](../../fin-ops-core/dev-itpro/deployment/install-deployable-package.md)。

## <a name="set-up-the-tms-engine-in-supply-chain-management"></a>在 Supply Chain Management 中設置 TMS 引擎

本節說明如何設置 Supply Chain Management 以使用 TMS 引擎，並如何將我們已建立的新引擎應用至費率查詢。 本節中的範例使用 USMF 示範資料公司。

1. 按照「創建新的 TMS 引擎」部分中的說明創建新引擎。
2. 組建您的解決方案。
3. 將產生的結果組件，複製到 Supply Chain Management 伺服器的二進位位置，\[AOSWebRoot\]bin。 **附註：** 此步驟僅與開發環境有關。 在實際執行環境中，您應該通過部署封裝進行部署。 有關說明，請參閱上一節「將 TMS 引擎作為封裝部屬」。
4. 在 Supply Chain Management 中，**費率引擎** 的頁面上，創建一個新的費率引擎。 引擎應該指向由引擎類別建立和您實施的引擎類別，所產生的引擎組件。 

   [![在費率引擎頁面上，創建一個新的費率引擎。](./media/081.png)](./media/081.png)

5. 使用樣本費率引擎，創建一個運輸承運人。 因為我們的引擎不使用任何數據，所以您不必指派費率主數據。 

   [![創建新的運輸承運人。](./media/092.png)](./media/092.png)

6. 在 **費率路線 Workbench** 頁面，按一下 **費率商店**。 您應該從 SampleCarrier 看到 100.00 的費率，如以下螢幕擷取畫面所示。 在此範例中，我們對從 24 倉庫到 US-004 客戶的路線進行費率查詢。 但是，由於費率是硬式編碼，因此您始終看到的是 100.00 費率。

   [![費率路線 Workbench。](./media/101.png)](./media/101.png)

## <a name="tips-and-tricks"></a>技巧和竅門

- 如果您正在使用 Supply Chain Management 的開發工具，對於將新項目添加到您的解決方案中會很有用。 如果將此項目設置為啟動項目並啟偵錯工作階段，則可以在相同的偵錯工作階段中，同時偵錯 X++ 和 C\# 中的代碼。
- 每次更改並重新編譯您的 ThirdPartyTMSEngines 項目時，您必須手動將生成的組件複製到二進制位置，或通過封裝進行部署。 否則，您可能會使用過時的組件運行。
- 在 Supply Chain Management 中執行 TMS 操作後，網路信息服務 (IIS) 工作進程可能會鎖定 ThirdPartyTMSEngines 組件，因此無法更新該組件。 在這種情況下，重新啟動 w3svc 流程。

### <a name="whitepaper"></a>技術白皮書

如需更多資訊，請下載以下技術白皮書 (為支持 AX2012 而編寫，但仍適用於 Dynamics 365 Supply Chain Management)

- [實施和部署運輸管理引擎](https://download.microsoft.com/download/b/5/f/b5ff8fef-3918-4c1d-92d5-b67eb0971684/ImplementingAndDeployingTransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]