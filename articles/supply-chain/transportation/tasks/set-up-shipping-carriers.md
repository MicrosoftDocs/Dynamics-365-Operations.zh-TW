---
title: 設定裝運承運人
description: 本主題介紹如何設定裝運承運人並定義服務、裝運模式、運輸招標、裝運限制和運費等詳細資料。
author: Henrikan
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e9bc4fefb6aabc0b93d4d96f5930590ef99235b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448035"
---
# <a name="set-up-shipping-carriers"></a>設定裝運承運人

[!include [banner](../../includes/banner.md)]

本主題介紹如何設定裝運承運人並定義服務、裝運模式、運輸招標、裝運限制和運費等詳細資料。 運輸協調員可以將裝運承運人指派給入庫或出庫負載。


## <a name="create-a-new-shipping-carrier"></a>建立新的裝運承運人
1. 移至 **瀏覽窗格 > 模組 > 運輸管理 > 設定 > 承運人 > 裝運承運人**。
2. 在動作窗格上，選擇 **新增**。
3. 在 **裝運承運人** 欄位中，輸入一個值。
4. 在 **名稱** 欄位中，輸入一個值。
5. 在 **模式** 欄位中，從下拉式功能表中選擇一個選項。

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>填入裝運承運人的一般資訊
1. 切換 **概觀** 區段的擴充功能。
2. 選取或取消選取 **使用中裝運承運人** 核取方塊。
3. 在 **廠商帳戶** 欄位中，從下拉式功能表中選擇一個選項。 選擇要將裝運承運人指派到的廠商帳戶。  
4. 在 **運輸招標類型** 欄位，選擇一個選項。 選擇 **手動** 以使用運輸招標頁面，或選擇 **EDI** 以使用電子資料交換 (EDI) 更新招標。  
5. 選取或取消選取 **使用中承運評等** 核取方塊。

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>為承運人建立必要的服務
1. 切換 **服務** 區段的擴充功能。
2. 選取 **新增**。
3. 在 **承運人服務** 欄位中，輸入一個值。
4. 在 **名稱** 欄位中，輸入一個值。
5. 在 **運輸模式** 欄位中，從下拉式功能表中選擇一個選項。

## <a name="set-up-the-address-for-the-carrier-optional"></a>設定承運人地址 (選填)
1. 切換 **地址** 區段的擴充。
2. 選取 **新增**。
3. 在 **名稱或描述** 欄位中，輸入一個值。
4. 在 **國家/地區** 欄位中，從下拉式功能表中選擇一個選項。
5. 在 **郵遞區號** 欄位中，從下拉式功能表中選擇一個選項。
6. 在 **街道** 欄位中，輸入一個值。
7. 選取 **確定**。

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>為承運人設定評等設定檔
1. 切換 **評等設定檔** 區段的擴充。
2. 選取 **新增**。
3. 在 **評等設定檔** 欄位中，輸入一個值。
4. 在 **名稱** 欄位中，輸入一個值。
5. 在 **站點** 欄位中，從下拉式功能表中選擇一個選項。
6. 在 **倉庫** 欄位中，從下拉式功能表中選擇一個選項。
7. 在 **費率引擎** 欄位中，從下拉式功能表中選擇一個選項。 根據合約，選擇符合您與承運人訂定的費率引擎。  
8. 在 **費率主板** 欄位中，從下拉式功能表中選擇一個選項。
9. 在 **運輸時間引擎** 欄位中，從下拉式功能表中選擇一個選項。
10. 選取 **儲存**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]