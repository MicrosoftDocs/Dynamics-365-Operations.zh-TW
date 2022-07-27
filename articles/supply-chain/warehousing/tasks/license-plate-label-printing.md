---
title: 啟用牌照標籤列印
description: 本主題說明，銷售撿貨工作程序中，從庫存挑選最後一項品項之後，如何啟用自動列印序列貨櫃代碼 (SSCC) 標籤。
author: perlynne
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b3895961f1f682a3fd06800a83a497afaf2fa65
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447792"
---
# <a name="enable-license-plate-label-printing"></a>啟用牌照標籤列印

[!include [banner](../../includes/banner.md)]

本主題說明，銷售撿貨工作程序中，從庫存挑選最後一項品項之後，如何啟用自動列印序列貨櫃代碼 (SSCC) 標籤。 您可以在 USMF 示範資料公司中執行此程序。 如果您使用自己的資料執行，則需要設定牌照編號序列。 開始此任務之前，您需要設定標籤印表機。 前往組織管理 > 設定 > 網路印表機。 在動作窗格上，按一下選項，然後按一下下載文件路由代理安裝程式按鈕。 執行安裝程式，並確保繼續程序之前，將網路印表機設定為使用中。


## <a name="set-up-the-gs1-company-prefix"></a>設定 GS1 公司前置詞
1. 請前往 **瀏覽窗格中 > 模組 > 倉庫管理 > 設定 > 倉庫管理參數**。
2. 在 **GS1 公司前置詞** 欄位中，輸入 7 個數字作為 GS1 公司的編號。
3. 選擇 **儲存**。
4. 關閉頁面。

## <a name="setup-the-sscc-license-plate-number-sequence"></a>設定 SSCC 牌照號碼順序
1. 前往 **功能窗格 > 模組 > 組織管理 > 編號序列 > 編號序列**。
2. 在 **區域** 欄位中，選擇選項。
3. 在 **參考** 欄位中，選擇選項。
4. 在 **公司** 欄位中，輸入一個值。
5. 展開 **區段** 部分。
6. 選擇 **編輯**。
7. 在 **區段** 資料表中，選擇第一列
8. 選擇 **移除**。
9. 選擇 **移除**。
10. 選擇 **儲存**。
11. 關閉頁面。

## <a name="create-the-document-route-layout"></a>建立文件路由配置
1. 前往 **功能窗格 > 模組 > 倉庫管理 > 設定 > 文件路由 > 文件路由配置**。 啟用 SSCC 配置。  
2. 選擇 **新增**。
3. 在 **配置識別碼** 欄位中，輸入一個值。
4. 在 **描述** 欄位中，輸入一個值。
5. 選擇 **插入文本末尾**。
6. 選擇 **儲存**。
7. 關閉頁面。

## <a name="set-up-the-document-routing"></a>設定文件路由
1. 前往 **功能窗格 > 模組 > 倉庫管理 > 設定 > 文件路由 > 文件路由**。
2. 在 **工單類型** 欄位中，選擇一個選項。
3. 選擇 **新增**。
4. 在 **Warehouse** 欄位中輸入值。
5. 在 **名稱** 欄位中，輸入一個值。
6. 選擇 **新增**。
7. 在 **配置識別碼** 欄位中，輸入或選擇一個值。
8. 在 **名稱** 欄位中，輸入要使用的印表機名稱。
9. 選擇 **儲存**。
10. 關閉頁面。

## <a name="create-mobile-device-menu"></a>建立行動裝置功能表
1. 前往 **功能窗格 > 模組 > 倉庫管理 > 設定 > 行動裝置 > 行動裝置功能表項目**。
2. 選擇 **新增**。
3. 在 **功能表項目名稱** 欄位中，輸入一個值。
4. 在 **標題** 欄位中，輸入一個值。
5. 在 **模式** 欄位中，選擇一個選項。
6. 在 **使用現有工作** 欄位中選取 **是**。
7. 在 **一般牌照** 欄位中選擇 **是**。
8. 展開 **工作類別** 區段。
9. 選擇 **新增**。
10. 在 **工作類別識別碼** 欄位中，輸入一個值。
11. 選擇 **儲存**。
12. 關閉頁面。
13. 前往 **功能窗格 > 模組 > 倉庫管理 > 設定 > 行動裝置 > 行動裝置功能表**。
14. 在樹狀圖中，選擇您剛建立的功能表項目。
15. 選擇 **編輯**。
16. 選擇箭頭，將功能表項目新增至功能表。
17. 選擇 **儲存**。
18. 關閉頁面。

## <a name="update-a-work-template"></a>更新工作範本
1. 前往 **導航窗格 > 模組 > 倉庫管理 > 設定 > 工作 > 工作範本**。
2. 選擇 **編輯**。
3. 選擇 **新增**。
4. 在 **工作類型** 欄位中，選擇 **列印**。
5. 在 **工作類別識別碼** 欄位中，輸入或選擇一個值。
6. 選擇 **上移**。
7. 選擇 **儲存**。
8. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]