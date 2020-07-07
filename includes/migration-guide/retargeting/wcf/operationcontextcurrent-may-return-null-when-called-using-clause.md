---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614755"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a><span data-ttu-id="efb55-101">OperationContext.Current는 using 절에서 호출될 때 null을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-101">OperationContext.Current may return null when called in a using clause</span></span>

#### <a name="details"></a><span data-ttu-id="efb55-102">설명</span><span class="sxs-lookup"><span data-stu-id="efb55-102">Details</span></span>

<span data-ttu-id="efb55-103">다음 조건이 모두 참인 경우 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>이 `null`를 반환하고 <xref:System.NullReferenceException>이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-103"><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> may return `null` and a <xref:System.NullReferenceException> may result if all of the following conditions are true:</span></span>

- <span data-ttu-id="efb55-104"><xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>을 반환하는 메서드에서 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> 속성 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-104">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property in a method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>
- <span data-ttu-id="efb55-105"><xref:System.ServiceModel.OperationContextScope> 개체는 `using` 절에서 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-105">You instantiate the <xref:System.ServiceModel.OperationContextScope> object in a `using` clause.</span></span>
- <span data-ttu-id="efb55-106">`using statement` 내의 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> 속성 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-106">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property within the `using statement`.</span></span> <span data-ttu-id="efb55-107">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="efb55-107">For example:</span></span>

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a><span data-ttu-id="efb55-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="efb55-108">Suggestion</span></span>

<span data-ttu-id="efb55-109">이 문제를 해결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-109">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="efb55-110">다음과 같이 코드를 수정하여 새로운 `null` <xref:System.ServiceModel.OperationContext.Current%2A> 이외의 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-110">Modify your code as follows to instantiate a new non- `null` <xref:System.ServiceModel.OperationContext.Current%2A> object:</span></span>

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- <span data-ttu-id="efb55-111">.NET Framework 4.6.2의 최신 업데이트를 설치하거나 이후 버전의 .NET Framework로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-111">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="efb55-112">이렇게 하면 <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>에서 <xref:System.Threading.ExecutionContext>의 흐름이 비활성화되고 .NET Framework 4.6.1 및 이전 버전에서 WCF 애플리케이션의 동작이 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-112">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> and restores the behavior of WCF applications in the .NET Framework 4.6.1 and earlier versions.</span></span> <span data-ttu-id="efb55-113">이 동작은 구성할 수 있습니다. 구성 파일에 다음 앱 설정을 추가하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-113">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    <span data-ttu-id="efb55-114">이러한 변경은 바람직하지 않으며 애플리케이션이 작업 컨텍스트 간에 흐르는 실행 컨텍스트에 의존하는 경우 다음과 같이 해당 흐름을 활성화할수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb55-114">If this change is undesirable and your application depends on execution context flowing between operation contexts, you can enable its flow as follows:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| <span data-ttu-id="efb55-115">이름</span><span class="sxs-lookup"><span data-stu-id="efb55-115">Name</span></span>    | <span data-ttu-id="efb55-116">값</span><span class="sxs-lookup"><span data-stu-id="efb55-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="efb55-117">Scope</span><span class="sxs-lookup"><span data-stu-id="efb55-117">Scope</span></span>   | <span data-ttu-id="efb55-118">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="efb55-118">Edge</span></span>        |
| <span data-ttu-id="efb55-119">버전</span><span class="sxs-lookup"><span data-stu-id="efb55-119">Version</span></span> | <span data-ttu-id="efb55-120">4.6.2</span><span class="sxs-lookup"><span data-stu-id="efb55-120">4.6.2</span></span>       |
| <span data-ttu-id="efb55-121">형식</span><span class="sxs-lookup"><span data-stu-id="efb55-121">Type</span></span>    | <span data-ttu-id="efb55-122">대상 변경</span><span class="sxs-lookup"><span data-stu-id="efb55-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="efb55-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="efb55-123">Affected APIs</span></span>

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>
