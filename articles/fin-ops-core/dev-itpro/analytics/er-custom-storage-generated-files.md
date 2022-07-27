---
title: 為產生的文件指定自訂儲存位置
description: 本主題說明如何擴展由電子報告 (ER) 格式產生的文件的儲存位置清單。
author: NickSelin
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 337e760f28161721d886c7bbec09b5ff8dbfad45
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8460546"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a>為產生的文件指定自訂儲存位置

[!include[banner](../includes/banner.md)]

電子報告 (ER) 架構的應用程式程式編寫介面 (API) 允許您擴展 ER 格式產生的文件的儲存位置清單。 本主題說明如何透過將建立 ER 目的地的工作委託給預設目的地工廠然後實現具有自己的目的地邏輯的自訂類來為產生的文件新增自訂儲存位置。

## <a name="prerequisites"></a>先決條件

部署支援持續構建的拓撲。 如需相關資訊，請參閱[部署支援持續構建和測試自動化的拓撲](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation)。 對於以下其中一個角色，您必須有權存取此拓撲：

- 電子報表開發人員
- 電子報表函數
- 系統管理員

您還必須有權存取此拓撲的開發環境。

本主題中的所有工作都可以在 **USMF** 公司中完成。

## <a name="import-the-fixed-asset-roll-forward-er-format"></a>匯入固定資產推延 ER 格式

若要產生您計畫為其新增自訂儲存位置的文件，請將 **固定資產推延** ER 格式設定[匯入](er-download-configurations-global-repo.md)現行拓撲。

![設定存放庫頁面。](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a>執行固定資產推延報表

1. 進入 **固定資產**\>**查詢和報告**\>**交易報告**\>**固定資產推延**。
2. 在 **起始日期** 欄位中，輸入 **1/1/2017** (2017 年 1 月 1 日)。
3. 在 **結束日期** 欄位中，輸入 **1/31/2017** (2017 年 1 月 31 日)。
4. 在 **貨幣欄位** 中，選取 **記帳貨幣**。
5. 在 **格式對應** 欄位，選取 **固定資產推延**。
6. 選取 **確定**。

![固定資產推延報表的執行階段對話方塊。](./media/er-custom-storage-generated-files-runtime-dialog.png)

在 Microsoft Excel 中，查看已產生且可供下載的輸出文件。 此行為是未設定[目的地](electronic-reporting-destinations.md)的 ER 格式的[預設行為](electronic-reporting-destinations.md#default-behavior)，並且在互動模式下執行。

## <a name="review-the-source-code"></a>查看原始程式碼

查看 `AssetRollForwardService` 類的 `generateReportByGER()` 方法的代碼。 請注意，`Run()` 方法可用於調用 ER 架構並產生 **固定資產推延** 報告。

```xpp
class AssetRollForwardService extends SysOperationServiceBase
{
    public const str ERFormatModelName = 'Fixed assets';
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'AssetRollForward';

    /// <summary>
    /// Generates report by general electronic reporting
    /// </summary>
    /// <param name = "_contract">The Asset Period Statement contract</param>
    public void generateReportByGER(AssetRollForwardContract _contract)
    {
        ERFormatMappingId   formatMappingId;
        AssetRollForwardDP  dataProvider;
        AssetRollForwardTmp assetRollForwardTmp;
        Query               query;

        query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
        dataProvider = AssetRollForwardDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

        if (assetRollForwardTmp)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                // Call ER to generate the report.
                ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName)
                    .withParameter(parameters)
                    .withFileDestination(_contract.getFileDestination())
                    .run();
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

## <a name="modify-the-source-code"></a>修改原始程式碼

1. 在您的 Visual Studio 專案，新增一個新類 (在這個範例中為 `AssetRollForwardDestination`)，並編寫代碼來實施您的自訂已產生 **固定資產推延** 報告的目的地。

    - `new()` 方法旨在獲取原始 ER 目的地對象和應用程式邏輯驅動的參數，該參數指定應儲存產生的報告的自訂位置。 在此範例中，自訂位置是執行應用程式物件伺服器 (AOS) 服務的伺服器，其本地檔案系統的資料夾名稱。
    - `saveFile()` 方法旨在將產生的文件儲存到執行 AOS 服務的伺服器的本地檔案系統的資料夾中。

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;

    /// <summary>
    /// Destination class for <c>AssetRollForwardDestinationFactory</c> that stores a generated report.
    /// </summary>
    public class AssetRollForwardDestination implements ERIFileDestination
    {
        private ERIFileDestination originDestination;
        private str TargetFolder;

        /// <summary>
        /// Creates a stream for new file.
        /// </summary>
        /// <param name = "_fileName">Name of a new file.</param>
        /// <returns>Stream for new file.</returns>
        public System.IO.Stream newFileStream(System.String _fileName)
        {
            return originDestination.newFileStream(_fileName);
        }

        /// <summary>
        /// Saves file in destination.
        /// </summary>
        /// <param name = "_stream">A stream to save.</param>
        /// <param name = "_fileName">A file name.</param>
        /// <returns>Saved stream.</returns>
        public System.IO.Stream saveFile(System.IO.Stream _stream, System.String _fileName)
        {
            _stream.Seek(0, System.IO.SeekOrigin::Begin);
            using (var localStream = System.IO.File::OpenWrite(TargetFolder + _fileName))
            {
                _stream.CopyTo(localStream);
            }
            return _stream;
        }

        /// <summary>
        /// Constructs destination for fixed asset roll forward report.
        /// </summary>
        /// <param name = "_originDestination">The original destination.</param>
        /// <param name = "_TargetFoder">The folder to store a report that's being created.</param>
        /// <returns>The fixed asset roll forward destination.</returns>
        public static AssetRollForwardDestination construct(ERIFileDestination _originDestination, str _TargetFoder)
        {
            return new AssetRollForwardDestination(_originDestination, _TargetFoder);
        }

        protected void new(ERIFileDestination _originDestination, str _TargetFoder)
        {
            originDestination = _originDestination;
            TargetFolder = _TargetFoder;
        }
    }
    ```

2. 在您的 Visual Studio 專案中，新增一個新類別 (在此範例中為 `AssetRollForwardDestinationFactory`)，並編寫代碼來設定一個自訂目的地工廠，將目的地的建立委託給預設目的地工廠，並使用您自己的目的地包裝一個檔案目的地。

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    using Microsoft.Dynamics365.LocalizationFramework.Format.FileGeneration;

    /// <summary>
    /// Destination factory for using <c>AssetRollForwardDestinationFactory</c>.
    /// </summary>
    public class AssetRollForwardDestinationFactory implements ERIFileDestinationFactory, ERIFileDestinationFactoryPostProcessor
    {
        private ERIFileDestinationFactory originDestinationFactory;
        private str TargetFolder;

        /// <summary>
        /// Creates file destination for print management.
        /// </summary>
        /// <param name = "_fileDestination">A default file destination.</param>
        /// <param name = "_identification">An identification strategy.</param>
        /// <param name = "_rootContext">A root context.</param>
        /// <param name = "_root">A root element.</param>
        /// <returns>A file destination.</returns>
        public ERIDataDrivenFileDestination createPrintMgmtDestination(
            ERIFileDestination _fileDestination,
            ERIObjectIdentificationStrategy _identification,
            ERTextFormatDataContext _rootContext,
            ERTextFormatIFileComponent _root)
        {
            ERIDataDrivenFileDestination dataDrivenDestination = originDestinationFactory.createPrintMgmtDestination(
                _fileDestination,
                _identification,
                _rootContext,
                _root);

            IFileDestinationHost fileDestinationHost = dataDrivenDestination as IFileDestinationHost;
            if (fileDestinationHost)
            {
                fileDestinationHost.FileDestination = AssetRollForwardDestination::construct(
                    fileDestinationHost.get_FileDestination(),
                    TargetFolder);
            }

            return dataDrivenDestination;
        }

        /// <summary>
        /// Constructs the fixed asset roll forward destination factory.
        /// </summary>
        /// <param name = "_originDestinationFactory">The original destination.</param>
        /// <param name = "_TargetFolder">The string containing a folder name that corresponds to the report, that's being created.</param>
        /// <returns>The destination factory for the fixed asset roll forward report.</returns>
        public static AssetRollForwardDestinationFactory construct(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            AssetRollForwardDestinationFactory destinationFactory = new AssetRollForwardDestinationFactory(_originDestinationFactory, _TargetFolder);

            ERIFileDestinationFactoryPostProcessorsHost factoryPostProcessing = ERCast::asObject(destinationFactory.originDestinationFactory) as ERIFileDestinationFactoryPostProcessorsHost;

            if (factoryPostProcessing)
            {
                factoryPostProcessing.addDestinationPostProcessor(destinationFactory);
            }
            return destinationFactory;
        }

        public ERIFileDestination processDestinationAfterCreation(ERIFileDestination _sourceDestination)
        {
            return AssetRollForwardDestination::construct(_sourceDestination, TargetFolder);
        }

        protected void new(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            originDestinationFactory = _originDestinationFactory;
            TargetFolder = _TargetFolder;
        }
    }
    ```

3. 修改現有的 `AssetRollForwardService` 類別，並編寫代碼為報表執行器設定自訂目的地工廠。 請注意，當構建自訂目的地工廠時，將傳遞指定目的地資料夾的應用程式驅動參數。 這樣，該目的地資料夾用於儲存產生的檔案。

    > [!NOTE] 
    > 確保指定的資料夾 (在本範例中為 **C:\\0**) 存在於執行 AOS 服務的伺服器的本地檔案系統中。 否則，會在執行階段引發[DirectoryNotFoundException](/dotnet/api/system.io.directorynotfoundexception)例外狀況。

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    /// <summary>
    /// The electronic reporting service class for fixed asset roll forward report
    /// </summary>
    class AssetRollForwardService extends SysOperationServiceBase
    {
        public const str ERFormatModelName = 'Fixed assets';
        public const str ERModelDataSourceName = 'model';
        public const str DefaultExportedFileName = 'AssetRollForward';

        /// <summary>
        /// Generates report by general electronic reporting
        /// </summary>
        /// <param name = "_contract">The Asset Period Statement contract</param>
        public void generateReportByGER(AssetRollForwardContract _contract)
        {
            ERFormatMappingId   formatMappingId;
            AssetRollForwardDP  dataProvider;
            AssetRollForwardTmp assetRollForwardTmp;
            Query               query;

            query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
            dataProvider = AssetRollForwardDP::construct();
            formatMappingId = _contract.parmFormatMapping();
            assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

            if (assetRollForwardTmp)
            {
                try
                {
                    ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                        .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                        .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                    // Call ER to generate the report.
                    ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());

                    ERIFileDestinationFactoryHost factoryHost = ERCast::asObject(formatMappingRun) as ERIFileDestinationFactoryHost;
                    if (factoryHost)
                    {
                        ERIFileDestinationFactory fileDestinationFactory = factoryHost.getFileDestinationFactory();
                        factoryHost.setFileDestinationFactory(AssetRollForwardDestinationFactory::construct(fileDestinationFactory, @'c:\0\'));
                        formatMappingRun.run();
                    }
                }
                catch
                {
                    // An error occurred while exporting data.
                    error("@SYP4861341");
                }
            }
            else
            {
                // There is no data available.
                info("@SYS300117");
            }
        }
    }
    ```

4. 重建您的專案。

## <a name="re-run-the-fixed-asset-roll-forward-report"></a>重新執行固定資產推延報表

1. 進入 **固定資產**\>**查詢和報告**\>**交易報告**\>**固定資產推延**。
2. 在 **起始日期** 欄位中，輸入 **1/1/2017**。
3. 在 **結束日期** 欄位中，輸入 **1/31/2017**。
4. 在 **貨幣欄位** 中，選取 **記帳貨幣**。
5. 在 **格式對應** 欄位，選取 **固定資產推延**。
6. 選取 **確定**。
7. 瀏覽本地 **C:\\0** 資料夾以找到產生的檔案。

> [!NOTE]
> 由於本例中的 `AssetRollForwardDestination` 物件中沒有使用 `originDestination` 物件，因此 ER 格式[目的地](electronic-reporting-destinations.md)的設定將在執行階段被忽略。

## <a name="additional-resources"></a>其他資源

- [電子報表 (ER) 目的地](electronic-reporting-destinations.md)
- [可擴展性首頁](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]