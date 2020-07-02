---
ms.openlocfilehash: 87dc93ece10eaedbfbabddb5f857d0bcd12e05c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615696"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a><span data-ttu-id="f680f-101">System.Net.ServicePointManager 및 System.Net.Security.SslStream에서는 Tls 1.0, 1.1 및 1.2 프로토콜만 지원됨</span><span class="sxs-lookup"><span data-stu-id="f680f-101">Only Tls 1.0, 1.1 and 1.2 protocols supported in System.Net.ServicePointManager and System.Net.Security.SslStream</span></span>

#### <a name="details"></a><span data-ttu-id="f680f-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f680f-102">Details</span></span>

<span data-ttu-id="f680f-103">.NET Framework 4.6부터 <xref:System.Net.ServicePointManager> 및 <xref:System.Net.Security.SslStream> 클래스에서 Tls1.0, Tls1.1 또는 Tls1.2 프로토콜 중 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f680f-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager> and <xref:System.Net.Security.SslStream> classes are only allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="f680f-104">SSL3.0 프로토콜 및 RC4 암호화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f680f-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f680f-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f680f-105">Suggestion</span></span>

<span data-ttu-id="f680f-106">권장되는 완화 방법은 Tls1.0, Tls1.1 또는 Tls1.2로 서버 쪽 앱을 업그레이드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f680f-106">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="f680f-107">이 작업이 불가능하거나 클라이언트 앱이 손상된 경우 <xref:System.AppContext?displayProperty=fullName> 클래스를 사용하여 다음 두 방법 중 하나로 이 기능을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f680f-107">If this is not feasible, or if client apps are broken, the <xref:System.AppContext?displayProperty=fullName> class can be used to opt out of this feature in either of two ways:</span></span>

- <span data-ttu-id="f680f-108">[여기](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46)에 설명된 대로 <xref:System.AppContext?displayProperty=fullName>에서 compat 스위치를 프로그래밍 방식으로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f680f-108">By programmatically setting compat switches on the <xref:System.AppContext?displayProperty=fullName>, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="f680f-109">다음 줄을 app.config 파일의 `<runtime>` 섹션에 추가</span><span class="sxs-lookup"><span data-stu-id="f680f-109">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>
```

| <span data-ttu-id="f680f-110">이름</span><span class="sxs-lookup"><span data-stu-id="f680f-110">Name</span></span>    | <span data-ttu-id="f680f-111">값</span><span class="sxs-lookup"><span data-stu-id="f680f-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f680f-112">Scope</span><span class="sxs-lookup"><span data-stu-id="f680f-112">Scope</span></span>   | <span data-ttu-id="f680f-113">부</span><span class="sxs-lookup"><span data-stu-id="f680f-113">Minor</span></span>       |
| <span data-ttu-id="f680f-114">버전</span><span class="sxs-lookup"><span data-stu-id="f680f-114">Version</span></span> | <span data-ttu-id="f680f-115">4.6</span><span class="sxs-lookup"><span data-stu-id="f680f-115">4.6</span></span>         |
| <span data-ttu-id="f680f-116">형식</span><span class="sxs-lookup"><span data-stu-id="f680f-116">Type</span></span>    | <span data-ttu-id="f680f-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="f680f-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f680f-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f680f-118">Affected APIs</span></span>

- <xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType>
