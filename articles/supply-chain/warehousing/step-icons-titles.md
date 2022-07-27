---
title: 為 Warehouse Management 行動應用程式指派步驟圖示和標題
description: 本主題描述如何為 Warehouse Management 行動應用程式的新工作流程或自訂工作流程指派步驟圖示和標題。
author: Mirzaab
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a687c26cacc0dbdaf0091b2d26277864553ca1bf
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449976"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a>為 Warehouse Management 行動應用程式指派步驟圖示和標題

[!include [banner](../includes/banner.md)]

本主題描述如何為 Warehouse Management 行動應用程式的新工作流程或自訂工作流程指派步驟圖示和步驟標題。

下圖顯示 Warehouse Management 行動應用程式中步驟圖示和標題的顯示方式。

![Warehouse Management 行動應用程式中的步驟圖示和步驟標題範例。](media/step-icon-example.png "Warehouse Management 行動應用程式中的步驟圖示和步驟標題範例")

## <a name="turn-this-feature-on-or-off"></a>開啟或關閉這項功能

若要使用此主題中描述的功能，您的系統必須開啟 *新版倉庫應用程式的使用者設定、圖示和步驟標題*。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以前往 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區並搜尋 *新版倉庫應用程式的使用者設定、圖示和步驟標題* 功能，然後開啟或關閉此功能。

## <a name="standard-step-ids-classes-and-icons"></a>標準步驟識別碼、類別和圖示

工作流程中的每個步驟都由一個步驟識別碼識別，每個步驟識別碼都有一個對應的步驟類別。 在每個步驟類別中指定步驟圖示和標題。

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a>步驟識別碼和步驟類別

下表列出了目前可用的每個步驟識別碼，以及它對應的步驟類別。 主要輸入欄位的控制項名稱用作步驟識別碼。

有關顯示如何使用這些步驟識別碼和類別的範例，請參閱本主題後面[範例：為自訂流程指派步驟圖示和標題](#example) 一節中 `WHSMobileAppStepInfoBuilder.stepId()` 方法的實踐。

| 步驟識別碼 | 步驟類別 |
|-|-|
| BatchDisposition | WHSMobileAppStepBatchDisposition |
| Carrier | WHSMobileAppStepCarrier |
| CatchWeight | WHSMobileAppStepCatchWeight |
| CatchWeightQtyOutboundWeight | WHSMobileAppStepCatchWeight |
| CatchWeightTag | WHSMobileAppStepCatchWeightTag |
| CatchWeightTagWeight | WHSMobileAppStepCatchWeightTagWeight |
| ChangeWarehouseSuccess | WHSMobileAppStepChangeWarehouseSuccess |
| CheckDigit | WHSMobileAppStepCheckDigit |
| ClusterId | WHSMobileAppStepClusterId |
| ClusterPickQtyVerification | WHSMobileAppStepQtyVerification |
| ClusterPosition | WHSMobileAppStepClusterPosition |
| ConfigId | WHSMobileAppStepConfigId |
| Confirmation | WHSMobileAppStepConfirmation |
| ConsolidateFromLicensePlateId | WHSMobileAppStepConsolidateFromLicensePlateId |
| ConsolidateLPConfirmation | WHSMobileAppStepConsolidateLPConfirmation |
| ConsolidateToLicensePlateId | WHSMobileAppStepConsolidateToLicensePlateId |
| ContainerType | WHSMobileAppStepContainerType |
| CountingReasonCode | WHSMobileAppStepCountingReasonCode |
| CycleCountingAddLPOrFinish | WHSMobileAppStepCycleCountingAddLPOrFinish |
| CycleCountQty1 | WHSMobileAppStepCycleCountQty |
| CycleCountQty2 | WHSMobileAppStepCycleCountQty |
| CycleCountQty3 | WHSMobileAppStepCycleCountQty |
| CycleCountQty4 | WHSMobileAppStepCycleCountQty |
| Disposition | WHSMobileAppStepDisposition |
| DriverCheckInConfirmation | WHSMobileAppStepDriverCheckInConfirmation |
| DriverCheckInId | WHSMobileAppStepDriverCheckInId |
| DriverCheckOutConfirmation | WHSMobileAppStepDriverCheckOutConfirmation |
| DriverCheckOutId | WHSMobileAppStepDriverCheckOutId |
| ExpDate | WHSMobileAppStepExpDate |
| FromBatchDisposition | WHSMobileAppStepFromBatchDisposition |
| FromInventoryStatus | WHSMobileAppStepInventoryStatusFrom |
| FullQty | WHSMobileAppStepFullQty |
| InboundPut | WHSMobileAppStepInboundPut |
| InventBatchId | WHSMobileAppStepBatch |
| InventColorId | WHSMobileAppStepInventColorId |
| InventLocation | WHSMobileAppStepInventLocation |
| InventLocationId | WHSMobileAppStepWarehouse |
| InventSerialId | WHSMobileAppStepInventSerialId |
| InventSizeId | WHSMobileAppStepInventSizeId |
| InventStatusId | WHSMobileAppStepInventStatus |
| InventStyleId | WHSMobileAppStepInventStyleId |
| InventVersionId | WHSMobileAppStepInventVersionId |
| ItemId | WHSMobileAppStepItem |
| ITMContainerID | ITMMobileAppStepContainerId |
| ITMShipmentID | ITMMobileAppStepShipmentId |
| KanbanCardId | WHSMobileAppStepKanbanCard |
| KanbanCardToEmpty | WHSMobileAppStepKanbanCardToEmpty |
| KanbanOrCardId | WHSMobileAppStepKanbanCard |
| LicensePlateId | WHSMobileAppStepLicensePlate |
| LoadId | WHSMobileAppStepLoadId |
| LocationLicensePlatePosition | WHSMobileAppStepLocationLicensePlatePosition |
| LocOrLP | WHSMobileAppStepLocOrLP |
| LocOrLP_From | WHSMobileAppStepLocOrLPFrom |
| LocOrLP_To | WHSMobileAppStepLocOrLPTo |
| LocOrLPCheck | WHSMobileAppStepLocOrLPCheck |
| LocVerification | WHSMobileAppStepLocVerification |
| LPAdjustIn | WHSMobileAppStepLPAdjustIn |
| LPBreakChildLP | WHSMobileAppStepLPBreakChildLP |
| LPBreakParentLP | WHSMobileAppStepLPBreakParentLP |
| LPBuildChildLP | WHSMobileAppStepLPBuildChildLP |
| LPBuildParentLP | WHSMobileAppStepLPBuildParentLP |
| LPVerification | WHSMobileAppStepLPVerification |
| MergeContainerId | WHSMobileAppStepMergeContainerId |
| MixedLPLineNum | WHSMobileAppStepMixedLPLineNum |
| MobileDeviceQueueMessageCollectionIdentifierId | WHSMobileAppStepSelectOrder |
| MovementConfirmCancel | WHSMobileAppStepMovementConfirmCancel |
| NewCaptureWeight | WHSMobileAppStepCatchWeight |
| NewQty | WHSMobileAppStepNewQty |
| OutboundCatchWeightTag | WHSMobileAppStepCatchWeightTag |
| OutboundPut | WHSMobileAppStepOutboundPut |
| OutboundWeight | WHSMobileAppStepCatchWeight |
| OverridePutNewLocation | WHSMobileAppStepOverridePutNewLocation |
| PieceByPieceConfirmation | WHSMobileAppStepQtyVerification |
| POLineNum | WHSMobileAppStepPOLineNum |
| PONum | WHSMobileAppStepPONum |
| PositionFull | WHSMobileAppStepPositionFull |
| PositionFullQty | WHSMobileAppStepPositionFullQty |
| Potency | WHSMobileAppStepPotency |
| PrinterName | WHSMobileAppStepPrinterName |
| ProdId | WHSMobileAppStepProdId |
| ProdLastPalletConfirmation | WHSMobileAppStepProdLastPalletConfirmation |
| ProductConfirmation | WHSMobileAppStepProductConfirmation |
| ProductionScrapConfirmation | WHSMobileAppStepProductionScrapConfirmation |
| Put | WHSMobileAppStepPut |
| PutawayClusterId | WHSMobileAppStepPutawayClusterId |
| Qty | WHSMobileAppStepQty |
| QtyAdjust | WHSMobileAppStepQtyAdjust |
| QtyShort | WHSMobileAppStepQtyShort |
| QtyToConsume | WHSMobileAppStepQtyToConsume |
| QtyToPick | WHSMobileAppStepQtyToPick |
| QtyToPut | WHSMobileAppStepQtyToPut |
| QtyToScrap | WHSMobileAppStepQtyToScrap |
| QtyVerification | WHSMobileAppStepQtyVerification |
| QtyWithScanningLimit | WHSMobileAppStepQtyAdjust |
| ReasonString | WHSMobileAppStepReasonString |
| RecvLocationId | WHSMobileAppStepRecvLocationId |
| RemoveContainerId | WHSMobileAppStepRemoveContainerId |
| ReprintLabelConfirmation | WHSMobileAppStepReprintLabelConfirmation |
| RMANum | WHSMobileAppStepRMANum |
| ShortPickReason | WHSMobileAppStepShortPickReason |
| SortConOrLP | WHSMobileAppStepSortConOrLP |
| SortLicensePlateId | WHSMobileAppStepSortLicensePlateId |
| SortPositionId | WHSMobileAppStepSortPositionId |
| SortVerification | WHSMobileAppStepSortVerification |
| StartLocationId | WHSMobileAppStepStartLocationId |
| StartProdOrderConfirmation | WHSMobileAppStepStartProdOrderConfirmation |
| TargetLicensePlateId | WHSMobileAppStepTargetLicensePlateId |
| TOLineNum | WHSMobileAppStepTOLineNum |
| ToLocation | WHSMobileAppStepToLocation |
| TONum | WHSMobileAppStepTONum |
| ToWarehouse | WHSMobileAppStepWarehouseTo |
| TransportLoadId | WHSMobileAppStepTransportLoadId |
| WaveLabelId | WHSMobileAppStepWaveLabelId |
| WaveLblQty | WHSMobileAppStepWaveLblQty |
| Weight | WHSMobileAppStepWeight |
| WeightToConsume | WHSMobileAppStepWeightToConsume |
| WHSAdjustmentType | WHSMobileAppStepWHSAdjustmentType |
| WHSReceivingException | WHSMobileAppStepWHSReceivingException |
| WHSWorkException | WHSMobileAppStepWHSWorkException |
| WHSWorkLicensePlateId | WHSMobileAppStepWorkLicensePlateId |
| WMSLocationId | WHSMobileAppStepLocation |
| WorkId | WHSMobileAppStepWorkId |
| WorkIdToCancel | WHSMobileAppStepWorkIdToCancel |
| WorkLPIdPutawayCluster | WHSMobileAppStepWorkLPIdPutawayCluster |
| WorkPoolId | WHSMobileAppStepWorkPoolId |
| ZoneId | WHSMobileAppStepZoneId |

### <a name="available-step-icons"></a><a name="step-icons"></a>可用的步驟圖示

系統包括標準步驟圖示的集合，您也可以將其用於自訂步驟。 目前無法上傳自訂步驟圖示。 因此，您必須從標準步驟圖示中選擇。

下表顯示目前可用的每個標準步驟圖示及其名稱。

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="關於步驟圖示"><br>關於</td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="新增牌照或品項步驟圖示"><br>AddLpOrItem</td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="批次處置步驟圖示"><br>BatchDisposition</td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="承運人步驟圖示"><br>Carrier</td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="實秤重量標籤步驟圖示"><br>CatchWeightTag</td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="實秤重量標籤重量步驟圖示"><br>CatchWeightTagWeight</td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="檢查數字步驟圖示"><br>CheckDigit</td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="簽入或簽出識別碼步驟圖示"><br>CheckInOutId</td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="下層牌照步驟圖示"><br>ChildLP</td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="叢集識別碼步驟圖示"><br>ClusterId</td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="叢集位置識別碼步驟圖示"><br>ClusterPosition</td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="組態識別碼步驟圖示"><br>ConfigId</td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="已配置的欄位步驟圖示"><br>ConfiguredField</td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Con 或 LP 步驟圖示"><br>ConOrLP</td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="從牌照識別碼步驟圖示合併"><br>ConsolidateFromLicensePlateID</td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="合併到牌照識別碼步驟圖示"><br>ConsolidateToLicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="集裝箱類型步驟圖示"><br>ContainerType</td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="計數步驟圖示"><br>Counting</td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="計數原因代碼步驟圖示"><br>CountingReasonCode</td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="原產國代碼步驟圖示"><br>CountryOfOrigin</td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="處置步驟圖示"><br>Disposition</td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="完成步驟圖示"><br>完成</td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="駕駛員簽入確認步驟圖示"><br>DriverCheckInConfirmation</td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="駕駛員簽入識別碼步驟圖示"><br>DriverCheckInId</td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="駕駛員簽出識別碼步驟圖示"><br>DriverCheckOutId</td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="到期日步驟圖示"><br>ExpDate</td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="欄位步驟圖示"><br>欄位</td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="開始批次處置步驟圖示"><br>FromBatchDisposition</td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="開始庫存狀態步驟圖示"><br>FromInventoryStatus</td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="識別碼屬性步驟圖示"><br>IdAttribute</td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="庫存批次識別碼步驟圖示"><br>InventBatchID</td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="庫存色彩識別碼步驟圖示"><br>InventColorID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="庫存位置識別碼步驟圖示"><br>InventLocation</td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="庫存序號識別碼步驟圖示"><br>InventSerialID</td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="庫存尺寸識別碼步驟圖示"><br>InventSizeID</td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="庫存狀態識別碼步驟圖示"><br>InventStatusID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="庫存樣式識別碼步驟圖示"><br>InventStyleID</td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="庫存版本識別碼步驟圖示"><br>InventVersionID</td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="品項識別碼步驟圖示"><br>ItemID</td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="ITM 集裝箱識別碼步驟圖示"><br>ITMContainerID</td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="ITM 裝運識別碼步驟圖示"><br>ITMShipmentID</td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="看板卡識別碼步驟圖示"><br>KanbanCardID</td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="看板或卡片識別碼步驟圖示"><br>KanbanOrCardID</td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="牌照識別碼步驟圖示"><br>LicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="位置識別碼步驟圖示"><br>LoadId</td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="位置牌照位置步驟圖示"><br>LocationLicensePlatePosition</td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="位置或牌照步驟圖示"><br>LocOrLP</td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="位置或牌照檢查步驟圖示"><br>LocOrLPCheck</td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="步驟圖示中的位置或牌照"><br>LocOrLPFrom</td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="位置或牌照到步驟圖示"><br>LocOrLPTo</td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="長流程完成步驟圖示"><br>LongProcessCompleted</td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="LP 打破上層 LP 步驟圖示"><br>LPBreakParentLP</td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="合併集裝箱識別碼步驟圖示"><br>MergeContainerId</td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="混合牌照行號步驟圖示"><br>MixedLPLineNum</td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="出庫重量步驟圖示"><br>OutboundWeight</td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="負責人步驟圖示"><br>負責人</td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="上層牌照步驟圖示"><br>ParentLP</td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="請確認步驟圖示"><br>PleaseConfirm</td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="訂購單行號步驟圖示"><br>POLineNum</td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="訂購單號步驟圖示"><br>PONum</td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="位置已滿步驟圖標"><br>PositionFull</td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="效力步驟圖示"><br>Potency</td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="印表機名稱步驟圖示"><br>PrinterName</td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="產品識別碼步驟圖示"><br>ProdId</td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="產品確認步驟圖示"><br>ProductConfirmation</td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="放置步驟圖示"><br>Put</td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="入庫叢集識別碼步驟圖示"><br>PutawayClusterId</td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="數量步驟圖示"><br>Qty</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="數量調整步驟圖示"><br>QtyAdjustIn</td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="數量短缺圖示"><br>QtyShort</td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="消耗數量步驟圖示"><br>QtyToConsume</td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="放置數量步驟圖示"><br>QtyToPut</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="報廢數量步驟圖示"><br>QtyToScrap</td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="數量確認步驟圖示"><br>QuantityConfirmation</td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="報告為已完成的結束作業步驟圖示"><br>RAFEndJob</td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="接收位置識別碼步驟圖示"><br>RecvLocationID</td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="移除集裝箱識別碼步驟圖示"><br>RemoveContainerID</td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="RMA 編號步驟圖示"><br>RMANum</td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="選擇訂單步驟圖示"><br>SelectOrder</td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="揀料短缺原因步驟圖示"><br>ShortPickReason</td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="排序位置識別碼步驟圖示"><br>SortPositionId</td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="目標牌照識別碼步驟圖示"><br>TargetLicensePlateId</td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="收件行號步驟圖示"><br>ToLineNum</td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="收件位置步驟圖示"><br>ToLocation</td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="收件號碼步驟圖示"><br>ToNum</td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="收件倉庫步驟圖示"><br>ToWarehouse</td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="傳輸負載識別碼步驟圖示"><br>TransportLoadId</td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="廠商批次識別碼步驟圖示"><br>VendBatchId</td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="波次標籤識別碼步驟圖示"><br>WaveLabelId</td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="波次標籤數量步驟圖示"><br>WaveLblQty</td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="重量步驟圖示"><br>重量</td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="消耗重量步驟圖示"><br>WeightToConsume</td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="WHS 調整步驟圖示"><br>WHSAdjustmentType</td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="WHS 接收例外狀況步驟圖示"><br>WHSReceivingException</td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="WMS 位置識別碼步驟圖示"><br>WMSLocationID</td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="工作識別碼步驟圖示"><br>WorkId</td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="要取消的工作識別碼步驟圖示"><br>WorkIdToCancel</td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="工作牌照識別碼步驟圖示"><br>WorkLicensePlateId</td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="工作牌照識別碼放置叢集步驟圖示"><br>WorkLPIDPutawayCluster</td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="工作池識別碼步驟圖示"><br>WorkPoolID</td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="區域識別碼步驟圖示"><br>ZoneID</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a>範例：為自訂流程指派步驟圖示和標題

此範例說明如何為自訂工作流程設定步驟圖示和標題。 該案例基於自訂工作流程的範例建置，該範例在以下部落格文章中進行了更詳細的介紹和探索：[自訂倉儲行動應用程式](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app)。 工作流程按以下方式運作：

1. 應用程式會顯示一個頁面，提示工作人員提供集裝箱識別碼 (例如，透過掃描條碼)。
1. 如果集裝箱識別碼有效，應用程式會打開一個新頁面，提示工作人員輸入重量。 (如果集裝箱識別碼無效，則工作人員將返回到第一頁。)
1. 當工作人員輸入有效重量時，系統會儲存重量，工作人員將返回到第一頁。

下圖顯示了此工作流程。

![工作流程圖。](media/step-icons-example-task-flow.png "工作流程圖")

### <a name="create-a-step-class-for-the-container-input-page"></a>為集裝箱輸入頁面建立步驟類別

工作人員可在集裝箱輸入頁面掃描或輸入集裝箱識別碼。

![集裝箱輸入頁面。](media/step-icons-example-container-input.png "集裝箱輸入頁面")

在集裝箱輸入頁面，輸入欄位的控制項名稱為 `ContainerId`。 因為這個控制項名稱不在[步驟識別碼清單](#step-ids-classes)中，所以您將找不到基於它的現有步驟。 因此，您必須建立一個代表該步驟的步驟類別。 範例如下。

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

步驟圖示的識別碼儲存在 `defaultStepIcon` 類別成員中，步驟標題儲存在 `defaultStepTitle` 類別成員中。

若要指派步驟圖示，請將 `defaultStepIcon` 設定為本主題前面[可用步驟圖示](#step-icons)一節中列出的圖示識別碼之一。

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a>為重量輸入使用標准或自訂步驟圖示和標題

工作人員可在重量輸入頁面輸入重量。

![重量輸入頁面。](media/step-icons-example-weight-input.png "重量輸入頁面")

在重量輸入頁面，輸入欄位的控制項名稱為 `Weight` (在[步驟識別碼清單](#step-ids-classes)中)。 因此，如果您可以接受在 `WHSMobileAppStepWeight` 類別中定義的步驟圖示和標題，則無須為此步驟進行任何變更。

但是，如果您希望在此步驟使用不同的圖示或標題，可以覆寫建立器類別中的 `stepId()` 方法或 `stepInfo()` 方法。 每個工作流程都有自己的步驟資訊建立器。

#### <a name="override-the-stepid-method"></a>覆寫 stepId() 方法

以下範例顯示可以透過覆寫 `stepId()` 方法來修改建立器類別的方法。

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

然後為 `NewWeight` 步驟建立步驟類別。 該代碼應類似於本主題前面顯示的 `ContainerId` 範例的代碼。

#### <a name="override-the-stepinfo-method"></a>覆寫 stepInfo() 方法

以下範例顯示可以透過覆寫 `stepInfo()` 方法來修改建立器類別的方法。

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

然後構建 `WHSMobileAppStepInfo` 物件，並直接設定圖示和/或標題。

## <a name="additional-resources"></a>其他資源

- [安裝並連線 Warehouse Management 行動應用程式](install-configure-warehouse-management-app.md)
- [行動裝置使用者設定](mobile-device-user-settings.md)
