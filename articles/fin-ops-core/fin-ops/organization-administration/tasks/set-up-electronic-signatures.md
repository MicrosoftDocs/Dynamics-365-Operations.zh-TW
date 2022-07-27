---
title: 設定電子簽名
description: 使用此程序設定電子簽名。
author: maertenm
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4075e47013bb6a3f42cb07f88df121cef8688463cab25c4a734c5363106ace4c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460316"
---
# <a name="set-up-electronic-signatures"></a>設定電子簽名

[!include [banner](../../includes/banner.md)]

使用此程序設定電子簽名。 電子簽名確認即將開始或核准計算過程的人的身份。 用來建立此程序的示範資料公司為 DAT。


## <a name="enable-the-electronic-signature-configuration-key"></a>啟用電子簽名設定金鑰
1. 前往系統管理 > 設定 > 授權設定。
2. 在樹狀結構中，展開「管理」。
    * 驗證是否選中了電子簽名核取方塊。  
    * 如果未選中電子簽名核取方塊，則必須啟用維護模式。 透過從 Lifecycle Services 執行維護作業或在本機使用 Deployment.Setup 工具，可以在此環境中啟用維護模式。  
3. 關閉頁面。

## <a name="set-up-electronic-signature-parameters"></a>設定電子簽名參數
1. 前往組織管理 > 設定 > 電子簽名 > 電子簽名參數。
2. 點選編輯。
3. 在通知欄位中輸入值。
    * 輸入請求籤名時簽名者將收到的通知。 您可以輸入任何文字。 通常，此文字會告訴使用者以電子方式簽署文件代表著什麼。  
    * 如果您想輸入其他語言的通知文字，請點選翻譯按鈕。  
4. 點選儲存。
5. 關閉頁面。

## <a name="set-up-reason-codes-for-electronic-signatures"></a>設定電子簽名的原因代碼
1. 前往組織管理 > 設定 > 電子簽名 > 電子簽名原因代碼。
2. 點選新增。
    * 您必須在使用電子簽名之前設定原因代碼。 簽署文件時需要有效的原因代碼。     簽名者選取一個原因代碼來指示電子簽名的目的。 例如，原因代碼可用於表示法律核准。  
3. 在原因代碼欄位中，輸入一個值。
4. 在描述欄位中，輸入一個值。
    * 如果需要，輸入其他原因代碼。  
5. 點選儲存。
6. 關閉頁面。

## <a name="require-electronic-signatures-for-existing-processes"></a>現有流程需要電子簽名
1. 前往組織管理 > 設定 > 電子簽名 > 電子簽名要求。
2. 在清單中，尋找並選取所需的記錄。
    * 選取需要電子簽名的流程。  
3. 選中或清除需要簽名核取方塊。
    * 對需要電子簽名的每個流程重複這些步驟。  
4. 點選儲存。

## <a name="create-a-custom-requirement-for-electronic-signatures"></a>建立電子簽名的自訂要求
1. 點選新增。
2. 選中或清除需要簽名核取方塊。
3. 在名稱欄位中，輸入需要電子簽名的流程的名稱。
4. 在資料表名稱欄位中，點選下拉式按鈕以打開查詢。
5. 在清單中，找到並選取儲存必須簽名之資料的資料表。
6. 在清單中，點選所選資料列中的連結。
7. 在欄位名稱欄位中，點選下拉式按鈕以打開查詢。
8. 在清單中，查詢並選取要監控的表中的欄位。
9. 在清單中，點選所選資料列中的連結。
    * 指定何時需要簽名。     如果在欄位中的資料更改時需要簽名，請選取始終。     選取僅當僅在某些條件下需要簽名時。 如果選取僅，還必須選取以下選項之一：插入記錄時、更新記錄時或刪除記錄時。  
10. 點選儲存。
11. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]