---
ms.openlocfilehash: 8aff4b1aa329d6fdfebf3b62e9279e9dfe5de0a4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606481"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a><span data-ttu-id="ff6da-101">ServicePointManager.SecurityProtocol의 기본값은 SecurityProtocolType.System.Default임</span><span class="sxs-lookup"><span data-stu-id="ff6da-101">Default value of ServicePointManager.SecurityProtocol is SecurityProtocolType.System.Default</span></span>

#### <a name="details"></a><span data-ttu-id="ff6da-102">설명</span><span class="sxs-lookup"><span data-stu-id="ff6da-102">Details</span></span>

<span data-ttu-id="ff6da-103">.NET Framework 4.7을 대상으로 하는 앱부터 <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 속성의 기본값은 <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff6da-103">Starting with apps that target the .NET Framework 4.7, the default value of the <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> property is <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ff6da-104">이 변경으로 SslStream을 기반으로 하는 .NET Framework 네트워킹 API(예: FTP, HTTPS 및 SMTP)가 .NET Framework에서 정의한 하드 코드된 값을 사용하는 대신 운영 체제에서 기본 보안 프로토콜을 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff6da-104">This change allows .NET Framework networking APIs based on SslStream (such as FTP, HTTPS, and SMTP) to inherit the default security protocols from the operating system instead of using hard-coded values defined by the .NET Framework.</span></span> <span data-ttu-id="ff6da-105">기본값은 운영 체제 및 시스템 관리자가 수행하는 사용자 정의 구성에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ff6da-105">The default varies by operating system and any custom configuration performed by the system administrator.</span></span> <span data-ttu-id="ff6da-106">각 버전의 Windows 운영 체제에서 기본 SChannel 프로토콜에 대한 자세한 내용은 [TLS/SSL의 프로토콜(Schannel SSP)](/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff6da-106">For information on the default SChannel protocol in each version of the Windows operating system, see [Protocols in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-).</span></span></p><span data-ttu-id="ff6da-107">이전 버전의 .NET Framework를 대상으로 하는 애플리케이션의 경우 <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 속성의 기본값은 대상으로 하는 .NET Framework의 버전에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ff6da-107">For applications that target an earlier version of the .NET Framework, the default value of the <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> property depends on the version of the .NET Framework targeted.</span></span> <span data-ttu-id="ff6da-108">자세한 내용은 [.NET Framework 4.5.2에서 4.6으로 마이그레이션을 위해 대상 변경의 네트워킹 섹션](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff6da-108">See the [Networking section of Retargeting Changes for Migration from .NET Framework 4.5.2 to 4.6](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking) for more information.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ff6da-109">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ff6da-109">Suggestion</span></span>

<span data-ttu-id="ff6da-110">이 변경은 .NET Framework 4.7 이상 버전을 대상으로 하는 애플리케이션에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff6da-110">This change affects applications that target the .NET Framework 4.7 or later versions.</span></span> <span data-ttu-id="ff6da-111">시스템 기본값에 의존하는 대신 정의된 프로토콜을 사용하려는 경우 <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 속성의 값을 명시적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff6da-111">If you prefer to use a defined protocol rather than relying on the system default, you can explicitly set the value of the <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ff6da-112">이 변경을 원치 않을 경우 애플리케이션 구성 파일의 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 구성 설정을 추가하여 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff6da-112">If this change is undesirable, you can opt out of it by adding a configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="ff6da-113">다음 예제에서는 `<runtime>` 섹션 및 `Switch.System.Net.DontEnableSystemDefaultTlsVersions` 옵트아웃 스위치를 모두 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff6da-113">The following example shows both the `<runtime>` section and the `Switch.System.Net.DontEnableSystemDefaultTlsVersions` opt-out switch:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSystemDefaultTlsVersions=true" />
</runtime>
```

| <span data-ttu-id="ff6da-114">이름</span><span class="sxs-lookup"><span data-stu-id="ff6da-114">Name</span></span>    | <span data-ttu-id="ff6da-115">값</span><span class="sxs-lookup"><span data-stu-id="ff6da-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ff6da-116">Scope</span><span class="sxs-lookup"><span data-stu-id="ff6da-116">Scope</span></span>   | <span data-ttu-id="ff6da-117">부</span><span class="sxs-lookup"><span data-stu-id="ff6da-117">Minor</span></span>       |
| <span data-ttu-id="ff6da-118">버전</span><span class="sxs-lookup"><span data-stu-id="ff6da-118">Version</span></span> | <span data-ttu-id="ff6da-119">4.7</span><span class="sxs-lookup"><span data-stu-id="ff6da-119">4.7</span></span>         |
| <span data-ttu-id="ff6da-120">형식</span><span class="sxs-lookup"><span data-stu-id="ff6da-120">Type</span></span>    | <span data-ttu-id="ff6da-121">대상 변경</span><span class="sxs-lookup"><span data-stu-id="ff6da-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="ff6da-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ff6da-122">Affected APIs</span></span>

- <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>
