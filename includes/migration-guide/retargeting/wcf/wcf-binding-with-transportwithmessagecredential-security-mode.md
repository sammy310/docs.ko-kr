---
ms.openlocfilehash: 0e949cbdeda99dd7b94e919b903a21171a57f527
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614731"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a><span data-ttu-id="01af2-101">TransportWithMessageCredential 보안 모드로 WCF 바인딩</span><span class="sxs-lookup"><span data-stu-id="01af2-101">WCF binding with the TransportWithMessageCredential security mode</span></span>

#### <a name="details"></a><span data-ttu-id="01af2-102">설명</span><span class="sxs-lookup"><span data-stu-id="01af2-102">Details</span></span>

<span data-ttu-id="01af2-103">.NET Framework 4.6.1부터는 TransportWithMessageCredential 보안 모드를 사용하는 WCF 바인딩이 비대칭 보안 키의 헤더에 대해 서명되지 않은 &quot;to&quot; 헤더가 있는 메시지를 받도록 설정할 수 있습니다. 기본적으로 서명되지 않은 &quot;to&quot; 헤더는 .NET Framework 4.6.1에서 계속 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="01af2-103">Beginning in the .NET Framework 4.6.1, WCF binding that uses the TransportWithMessageCredential security mode can be set up to receive messages with unsigned &quot;to&quot; headers for asymmetric security keys.By default, unsigned &quot;to&quot; headers will continue to be rejected in .NET Framework 4.6.1.</span></span> <span data-ttu-id="01af2-104">애플리케이션이 Switch.System.ServiceModel.AllowUnsignedToHeader 구성 스위치를 사용하여 이 새로운 작업 모드를 옵트인하는 경우에만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01af2-104">They will only be accepted if an application opts into this new mode of operation using the Switch.System.ServiceModel.AllowUnsignedToHeader configuration switch.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="01af2-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="01af2-105">Suggestion</span></span>

<span data-ttu-id="01af2-106">이 기능은 옵트인 기능이기 때문에 기존 앱의 동작에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01af2-106">Because this is an opt-in feature, it should not affect the behavior of existing apps.</span></span><br/><span data-ttu-id="01af2-107">새 동작을 사용할지 여부를 제어하려면 다음 구성 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01af2-107">To control whether the new behavior is used or not, use the following configuration setting:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />
</runtime>
```

| <span data-ttu-id="01af2-108">이름</span><span class="sxs-lookup"><span data-stu-id="01af2-108">Name</span></span>    | <span data-ttu-id="01af2-109">값</span><span class="sxs-lookup"><span data-stu-id="01af2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="01af2-110">Scope</span><span class="sxs-lookup"><span data-stu-id="01af2-110">Scope</span></span>   | <span data-ttu-id="01af2-111">투명</span><span class="sxs-lookup"><span data-stu-id="01af2-111">Transparent</span></span> |
| <span data-ttu-id="01af2-112">버전</span><span class="sxs-lookup"><span data-stu-id="01af2-112">Version</span></span> | <span data-ttu-id="01af2-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="01af2-113">4.6.1</span></span>       |
| <span data-ttu-id="01af2-114">형식</span><span class="sxs-lookup"><span data-stu-id="01af2-114">Type</span></span>    | <span data-ttu-id="01af2-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="01af2-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="01af2-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="01af2-116">Affected APIs</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
