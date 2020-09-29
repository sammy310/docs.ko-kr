---
ms.openlocfilehash: 9f5f238e3d4222af1da3a1713e1b3e65de6e6f49
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "91025266"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="93098-101">WCF PipeConnection.GetHashAlgorithm은 이제 SHA256을 사용</span><span class="sxs-lookup"><span data-stu-id="93098-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="93098-102">설명</span><span class="sxs-lookup"><span data-stu-id="93098-102">Details</span></span>

<span data-ttu-id="93098-103">.NET Framework 4.7.1부터 Windows Communication Foundation은 명명 된 파이프에 대한 임의 이름을 생성하기 위해 SHA256 해시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93098-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="93098-104">.NET Framework 4.7 및 이전 버전에서는 SHA1 해시를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="93098-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="93098-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="93098-105">Suggestion</span></span>

<span data-ttu-id="93098-106">.NET Framework 4.7.1 이상에서 이러한 변경 내용과의 호환성 문제가 발생하면 app.config 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93098-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="93098-107">Name</span><span class="sxs-lookup"><span data-stu-id="93098-107">Name</span></span>    | <span data-ttu-id="93098-108">값</span><span class="sxs-lookup"><span data-stu-id="93098-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="93098-109">Scope</span><span class="sxs-lookup"><span data-stu-id="93098-109">Scope</span></span>   | <span data-ttu-id="93098-110">부</span><span class="sxs-lookup"><span data-stu-id="93098-110">Minor</span></span>   |
| <span data-ttu-id="93098-111">버전</span><span class="sxs-lookup"><span data-stu-id="93098-111">Version</span></span> | <span data-ttu-id="93098-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="93098-112">4.7.1</span></span>   |
| <span data-ttu-id="93098-113">형식</span><span class="sxs-lookup"><span data-stu-id="93098-113">Type</span></span>    | <span data-ttu-id="93098-114">런타임</span><span class="sxs-lookup"><span data-stu-id="93098-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="93098-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="93098-115">Affected APIs</span></span>

<span data-ttu-id="93098-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93098-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
