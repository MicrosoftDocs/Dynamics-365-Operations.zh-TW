---
title: 驗證
description: 本文提供有關搭配 Microsoft Dynamics 365 Human Resources 資料應用程式程式化介面 (API) 驗證的概觀資訊。
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3396f0ae6d089f43c39f318dc9d92a88a7db3d7c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452667"
---
# <a name="authentication"></a>驗證


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本文提供有關搭配 Microsoft Dynamics 365 Human Resources 資料應用程式程式化介面 (API) 驗證的概觀資訊。

## <a name="overview"></a>概觀

人力資源資料 API 是 OData 落實的表現。 更多資訊，請參閱[開放資料協議 (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md)。

在 API 服務您的應用程式要求之前，您的應用程式必須以授權呼叫程式形式驗證。

## <a name="fundamentals"></a>基礎知識

若要呼叫資料 API，您的應用程式必須先從 Microsoft 識別平台取得存取權杖。 存取權杖包含有關您的應用程式資訊以及它必須呼叫 Human Resources 中的資源權限。

### <a name="access-token"></a>存取權杖

Microsoft 識別平台核發的存取權丈是 base64 編碼的 JavaScript Object Notation (JSON) Web Tokens (JWT)。 它們包含用來驗證呼叫者，並且確定呼叫者有正確權限執行要求操作的資料 API 資訊 (以及安全獲得 Microsoft 識別平台保障的其他 Web API)。 呼叫期間，您可以不透明方式對待存取權杖。 您應該始終在安全通道上傳輸存取權杖，例如傳輸層安全 (TLS) 和超文字安全傳輸協議 (HTTPS)。

以下是 Microsoft 識別平台核發的存取權杖範例。

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

若要呼叫資料 API，您將存取權杖以持有人權杖附在 HTTP 要求的授權標頭。 範例如下。

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a>使用 Azure 入口網站註冊新應用程式

1. 使用工作或學校帳戶，或個人 Microsoft 帳戶登入 [Microsoft Azure 入口網站](https://portal.azure.com)。

2. 如果您的帳戶給您多名租用戶的存取權，請在右上角選取您的帳戶，然後將您的入口網站工作階段設定為您希望的 Azure Active Directory(Azure AD) 租用戶。

3. 請在左側窗格選取 **Azure Active Directory** 服務，然後選取 **應用程式註冊\>新註冊**。

4. 當 **註冊應用程式** 頁面出現時，輸入您的應用程式註冊資訊：

    - **姓名**：輸入將顯示給應用程式使用者，有意義的應用程式名稱。
    - **支援的帳戶類型**：選取您的應用程式應支援的帳戶類型。

        | 支援的帳戶類型 | 描述 |
        |-------------------------|-------------|
        | 僅限組織目錄的帳戶 | 如果您正在建構業務線應用程式，請選取此選項。 除非您在目錄註冊應用程式，否則此選項無法使用。<p>此選項已測繪到 **Azure AD 限單租用戶**。</p><p>除非您在目錄以外的位置註冊應用程式，否則此選項為預設選項。 此時預設選項是 **Azure AD 多租用戶和個人 Microsoft 帳戶**。</p> |
        | 任何組織目錄的帳戶 | 選取此選項確定所有商業和教育客戶。<p>此選項已測繪到 **Azure AD 限多租用戶**。</p><p>如果您將應用程式註冊為 **Azure AD 限單租用戶**，您可以使用 **驗證** 刀片更新為 **Azure AD 限多租戶**，然後回到 **Azure AD 限單租戶**。</p> |
        | 任何組織目錄中的帳戶和個人 Microsoft 帳戶 | 選取此選項確定最廣泛的客群。<p>本選項已測繪 **Azure AD 多租用戶和個人 Microsoft 帳戶**。</p><p>如果您將應用程式註冊為 **Azure AD 多租用戶和個人 Microsoft 帳戶**，您無法在使用者界面 (UI) 更改此項設定。 相反地，您必須使用應用程式資訊清單編輯器更改支援的帳戶類型。</p> |

    - **重新導向 URI (可選)** – 選取您正在建構的應用程式類型：**網路** 或 **公共用戶端 (行動和桌面)**。 然後輸入應用程式重新導向 URI (或回覆 URL)。

        - Web 應用程式方面，請提供應用程式的基本 URL。 例如，`http://localhost:31544` 可能是在本機機器執行的 Web 應用程式 URL。 接著使用者使用此 URL 登入 Web 用戶端應用程式。
        - 公共用戶端應用程式方面，請提供 Azure AD 用來傳回權杖回應的 URI。 請輸入您的應用程式專屬值，例如 `myapp://auth`。

        若要查看 Web 應用程式或本機應用程式特定範例，請參閱 [Microsoft 識別平台 (前身為開發人員專用的 Azure Active Directory) 快速入門](/azure/active-directory/develop/#quickstarts)。

5. 請在 **API 權限** 下方選取 **新增權限**。 接著請在 **敝組織使用 API** 索引標籤搜尋 **Dynamics 365 Human Resources**，並新增 **使用者\_冒名頂替** 權限到您的應用程式。 人力資源的應用程式識別碼是 f9be0c49-aa22-4ec6-911a-c5da515226ff。 請使用此識別碼確保您已經選擇正確的應用程式。

6. 請選取 **註冊**。

   [![在 Azure 入口網站註冊新 App。](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)

Azure AD 指派唯一的應用程式識別碼 (用戶端識別碼) 到您的應用程式，並將您帶往您的應用程式 **概觀** 頁面。 若要新增更多功能到的應用程式，您可以選取其他配置選項，例如品牌選項和證書及機密選項。

## <a name="retrieving-an-access-token"></a>檢索存取權杖

檢索存取權杖呼叫人力資源資料 API 的具體方式將取決於您用來開發用戶端應用程式的技術。 例如，您可能在[使用第三方公用程式測試](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (例如  Postman)、開發 C# 控制台應用程式或 Web 服務，或建構 javascript/TypeScript 用戶端。

用戶端應用程式 C# 範例：
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

一旦您已經檢索到存取權杖，您將在驗證標頭以持有人權杖形式，連同您傳到資料 API 的各項要求一起傳遞權杖 ，如上所述。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
