---
title: 稅金計算概觀
description: 本主題說明稅金計算功能的整體範圍和功能。
author: wangchen
ms.date: 03/02/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a02767e4a90fa6b7414c796d66e758afe0501cf5
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2022
ms.locfileid: "8451737"
---
# <a name="tax-calculation-overview"></a>稅金計算概觀

[!include [banner](../includes/banner.md)]

稅金計算是一項能讓 Global Tax Engine 自動化和簡化稅金判定和計算流程的超伸縮多租戶服務。  Tax Engine完全可以組態。 可以組態的元素包括但不限於課稅資料模型、稅籍代碼、稅金適用性矩陣、稅金計算公式。  Tax Engine在 Microsoft Azure 核心服務平台上執行，提供現代技術和指數型伸縮性。

稅金計算與 Dynamics 365 Finance 和 Dynamics 365 Supply Chain Management 整合。 最後它也整合 Dynamics 365 Project Operations、Dynamics 365 Commerce，以及其他第一方和第三方應用程式。

> [!IMPORTANT]
> 當您啟用稅金計算功能時，某些相關資料操作可能會在資料中心執行，而此資料中心並不維護您的服務資料。 在啟用稅金計算功能之前審查[條款和條件](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md)。 您的隱私對我們很重要。 若要了解更多，請閱讀我們的[隱私聲明](https://go.microsoft.com/fwlink/?LinkId=521839)。

稅金計算是以微服務為基礎的 Tax Engine，提供指數型伸縮性，能幫助您執行下列任務：

- 透過強化版的判定機制自動判定正確的銷售稅群組、分項銷售稅群組和稅籍代碼。
- 支援一間法人實體使用多個稅籍編號，並且自動判定課稅交易上的正確稅籍編號。
- 支援轉單的稅金判定、計算、過帳和結算。
- 為您的特定業務需求定義可配置的稅金計算公式和條件。
- 在法人實體之間共享稅金判定和計算解決方案，以節省維護心力並避免錯誤。
- 支援客戶和供應商稅籍編號判定。
- 支援清單代碼判定。
- 支援稅金管轄等級的稅金計算參數。

若要使用稅金計算功能，請在 Microsoft Dynamics Lifecycle Services 從您的專案安裝稅金計算增益集。 接著在[Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) 設定，並在 Finance 和 Supply Chain Management 啟用稅金計算功能。 有關詳細資訊，請參閱[開始稅金服務](global-get-started-with-tax-calculation-service.md)。

## <a name="availability"></a>可用性

自版本 10.0.21 起，所有客戶皆可在實際執行環境使用稅金計算功能。

新功能將繼續提供。 時常查看最新的發行版本計劃，以了解支援功能的涵蓋範圍和範疇。

稅金計算部署的 Azure 地理位置如下。 將根據客戶需求基礎新增更多 Azure 地理位置。

- 亞太地區
- 澳洲
- 加拿大
- 歐洲
- 日本
- 瑞士
- 英國
- 美國

> [!NOTE]
> 稅金計算功能不支援 Dynamics 365 的早期版本，例如 Dynamics AX 2012 或 Dynamics 365 的本部佈署。

## <a name="versions"></a>版本
我們建議您使用符合您的 Finance 或 Supply Chain Management 版本的版本匯入和設定您的稅金計算組態。

| Finance 或 Supply Chain Management 版本 | 稅金組態版本               |
| --------------- | --------------------------------------- |
| 10.0.18         | 稅金組態 - 歐洲 30.12.82     |
| 10.0.19         | 稅金計算組態 36.38.193 |
| 10.0.20         | 稅金計算組態 40.43.208 |
| 10.0.21         | 稅金計算組態 40.48.215 |
| 10.0.22         | 稅金計算組態 40.48.215 |
| 10.0.23         | 稅金計算組態 40.50.221 |
| 10.0.24         | 稅金計算組態 40.50.225 |
| 10.0.25         | 稅金計算組態 40.50.225 |
| 10.0.26         | 稅金計算組態 40.54.234 |


## <a name="data-flow"></a>資料流

這是稅金計算的資料流流程的輪廓。 

1. 在 RCS 檢視和匯入課稅文件模型組態和模型映射組態。 如果您必須為進階方案延伸組態，請參閱[在稅金配置中新增資料欄位](tax-service-add-data-fields-tax-configurations.md)。
2. 在 RCS 建立或維護稅金功能。 您可以使用稅金功能維護稅率和稅金適用性規則。
3. 稅金功能設定完成後，將稅金配置和稅金功能從 RCS 發佈到全域儲存庫。
4. 請在 Finance 選取要用於特定法人實體的稅金功能設定版本。
5. 請在 Finance 和 Supply Chain Management 照常操作交易。 當需要進行稅金計算時，客戶將從交易收集資訊，例如銷售訂單或採購訂單，並將這些資訊打包成酬載。 接著將傳送計算稅金的請求。
6. 收到客戶的稅金計算請求後，計算完成。 接著將稅金計算結果傳回客戶。
7. Dynamics 365 用戶收到稅金計算結果並在銷售稅頁呈現。

## <a name="supported-transactions"></a>支援的交易

可藉由交易啟用稅金計算。 

10.0.21 版本支援的交易如下： 

- 銷售

    - 銷售報價
    - 銷售訂單
    - 確認
    - 揀料清單
    - 裝箱單
    - 銷售發票
    - 信用票據
    - 退貨單
    - 抬頭雜項收費
    - 行項雜項收費

- 購買

    - 採購訂單
    - 確認
    - 收據清單
    - 產品收據
    - 採購發票
    - 抬頭雜項收費
    - 行項雜項收費
    - 信用票據
    - 退貨單
    - 採購徵用
    - 採購徵用行項雜費收費
    - 索取報價
    - 索取報價單抬頭雜項收費
    - 索取報價單行項雜項收費

- 庫存

    - 轉單 - 出貨
    - 轉單 - 收貨

10.0.23 版本支援的交易如下： 

- 任意文字發票

10.0.26 版本支援的交易如下： 

- 普通日記帳
- 供應商發票日記帳

## <a name="supported-countriesregions"></a>支援的國家/地區

可藉由法人實體啟用稅金計算。 

版本 10.0.21 支援法人主要地址所屬的國家/地區：

- 奧地利
- 比利時
- 丹麥
- 愛沙尼亞
- 芬蘭
- 法國
- 德國
- 匈牙利
- 冰島
- 義大利
- 拉脫維亞
- 立陶宛
- 荷蘭
- 挪威
- 波蘭
- 瑞典
- 瑞士
- 英國
- 美國

版本 10.0.22 支援法人主要地址所屬的國家/地區：

- 澳洲
- 巴林
- 加拿大
- 埃及
- 香港特別行政區
- 科威特
- 紐西蘭
- 阿曼
- 卡達
- 沙烏地阿拉伯
- 南非
- 阿拉伯聯合大公國

版本 10.0.23 支援法人主要地址所屬的國家/地區：

- 泰國
- 日本
- 馬來西亞
- 新加坡

版本 10.0.24 支援法人主要地址所屬的國家/地區：

- 墨西哥

版本 10.0.26 支援法人主要地址所屬的國家/地區：

- 中國
- 捷克共和國
- 西班牙

## <a name="related-resources"></a>相關資源

[開始使用稅金服務](./global-get-started-with-tax-calculation-service.md)

[多個增值稅註冊編號](./emea-multiple-vat-registration-numbers.md)

[轉單的稅金功能支援](./tasks/tax-feature-support-for-transfer-order.md)

[如何在稅金服務中建立擴充功能](./tax-service-add-data-fields-tax-integration-by-extension.md)
