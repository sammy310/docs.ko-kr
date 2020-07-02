---
ms.openlocfilehash: dd7d3e445772e4b5ec148576ccd1374d56e251bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614782"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a><span data-ttu-id="c0f21-101">재진입 서비스를 사용할 때 교착 상태가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f21-101">Deadlock may result when using Reentrant services</span></span>

#### <a name="details"></a><span data-ttu-id="c0f21-102">설명</span><span class="sxs-lookup"><span data-stu-id="c0f21-102">Details</span></span>

<span data-ttu-id="c0f21-103">교착 상태가 발생하면 재진입 서비스의 인스턴스가 한번에 하나의 실행 스레드로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0f21-103">A deadlock may result in a Reentrant service, which restricts instances of the service to one thread of execution at a time.</span></span> <span data-ttu-id="c0f21-104">이 문제가 발생하기 쉬운 서비스는 코드에 다음과 같은 <xref:System.ServiceModel.ServiceBehaviorAttribute>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f21-104">Services prone to encounter this problem will have the following <xref:System.ServiceModel.ServiceBehaviorAttribute> in their code:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a><span data-ttu-id="c0f21-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c0f21-105">Suggestion</span></span>

<span data-ttu-id="c0f21-106">이 문제를 해결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f21-106">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="c0f21-107">서비스의 동시성 모드를 <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> 또는 &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f21-107">Set the service's concurrency mode to <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> or &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;.</span></span> <span data-ttu-id="c0f21-108">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="c0f21-108">For example:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- <span data-ttu-id="c0f21-109">.NET Framework 4.6.2의 최신 업데이트를 설치하거나 이후 버전의 .NET Framework로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f21-109">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="c0f21-110">이렇게 하면 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>에서 <xref:System.Threading.ExecutionContext>의 흐름이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0f21-110">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c0f21-111">이 동작은 구성할 수 있습니다. 구성 파일에 다음 앱 설정을 추가하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f21-111">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

<span data-ttu-id="c0f21-112">`Switch.System.ServiceModel.DisableOperationContextAsyncFlow`의 값은 재진입 서비스에 대해 `false`로 설정하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0f21-112">The value of `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` should never be set to `false` for Reentrant services.</span></span>

| <span data-ttu-id="c0f21-113">이름</span><span class="sxs-lookup"><span data-stu-id="c0f21-113">Name</span></span>    | <span data-ttu-id="c0f21-114">값</span><span class="sxs-lookup"><span data-stu-id="c0f21-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c0f21-115">Scope</span><span class="sxs-lookup"><span data-stu-id="c0f21-115">Scope</span></span>   | <span data-ttu-id="c0f21-116">부</span><span class="sxs-lookup"><span data-stu-id="c0f21-116">Minor</span></span>       |
| <span data-ttu-id="c0f21-117">버전</span><span class="sxs-lookup"><span data-stu-id="c0f21-117">Version</span></span> | <span data-ttu-id="c0f21-118">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c0f21-118">4.6.2</span></span>       |
| <span data-ttu-id="c0f21-119">형식</span><span class="sxs-lookup"><span data-stu-id="c0f21-119">Type</span></span>    | <span data-ttu-id="c0f21-120">대상 변경</span><span class="sxs-lookup"><span data-stu-id="c0f21-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c0f21-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c0f21-121">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
