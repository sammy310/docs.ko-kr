---
ms.openlocfilehash: 78faa5f4008b41bac75c94ce09a58c8227e5b485
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614671"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a><span data-ttu-id="a2adc-101">CurrentCulture 및 CurrentUICulture가 작업에 걸쳐 전달됨</span><span class="sxs-lookup"><span data-stu-id="a2adc-101">CurrentCulture and CurrentUICulture flow across tasks</span></span>

#### <a name="details"></a><span data-ttu-id="a2adc-102">설명</span><span class="sxs-lookup"><span data-stu-id="a2adc-102">Details</span></span>

<span data-ttu-id="a2adc-103">.NET Framework 4.6부터 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>은 스레드의 <xref:System.Threading.ExecutionContext?displayProperty=fullName>에 저장되며 비동기 작업을 통해 전달됩니다. 즉, <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>의 변경은 이후 비동기적으로 실행되는 작업에서 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2adc-103">Beginning in the .NET Framework 4.6, <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> are stored in the thread's <xref:System.Threading.ExecutionContext?displayProperty=fullName>, which flows across asynchronous operations.This means that changes to <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> will be reflected in tasks which are later run asynchronously.</span></span> <span data-ttu-id="a2adc-104">이는 모든 비동기 작업에서 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>을 다시 설정하는 이전 .NET Framework 버전의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a2adc-104">This is different from the behavior of previous .NET Framework versions (which would reset <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> in all asynchronous tasks).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a2adc-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a2adc-105">Suggestion</span></span>

<span data-ttu-id="a2adc-106">이 변경의 영향을 받는 앱은 비동기 작업에서 원하는 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>을 첫 번째 작업으로 명확하게 설정하여 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2adc-106">Apps affected by this change may work around it by explicitly setting the desired <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> as the first operation in an async Task.</span></span> <span data-ttu-id="a2adc-107">또는 다음 호환성 스위치를 설정하여 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>을 전달하지 않는 이전 동작을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2adc-107">Alternatively, the old behavior (of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) may be opted into by setting the following compatibility switch:</span></span>

```csharp
AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);
```

<span data-ttu-id="a2adc-108">이 문제는 .NET Framework 4.6.2의 WPF에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a2adc-108">This issue has been fixed by WPF in .NET Framework 4.6.2.</span></span> <span data-ttu-id="a2adc-109">또한 [KB 3139549](https://support.microsoft.com/kb/3139549)를 통해 .NET Frameworks 4.6, 4.6.1에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a2adc-109">It has also been fixed in .NET Frameworks 4.6, 4.6.1 through [KB 3139549](https://support.microsoft.com/kb/3139549).</span></span> <span data-ttu-id="a2adc-110">.NET Framework 4.6 이상을 대상으로 하는 애플리케이션은 디스패처 작업 전반에 걸쳐 WPF 애플리케이션(<xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>)에서 올바른 동작을 자동으로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="a2adc-110">Applications targeting .NET Framework 4.6 or later will automatically get the right behavior in WPF applications - <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) would be preserved across Dispatcher operations.</span></span>

| <span data-ttu-id="a2adc-111">이름</span><span class="sxs-lookup"><span data-stu-id="a2adc-111">Name</span></span>    | <span data-ttu-id="a2adc-112">값</span><span class="sxs-lookup"><span data-stu-id="a2adc-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a2adc-113">Scope</span><span class="sxs-lookup"><span data-stu-id="a2adc-113">Scope</span></span>   | <span data-ttu-id="a2adc-114">부</span><span class="sxs-lookup"><span data-stu-id="a2adc-114">Minor</span></span>       |
| <span data-ttu-id="a2adc-115">버전</span><span class="sxs-lookup"><span data-stu-id="a2adc-115">Version</span></span> | <span data-ttu-id="a2adc-116">4.6</span><span class="sxs-lookup"><span data-stu-id="a2adc-116">4.6</span></span>         |
| <span data-ttu-id="a2adc-117">형식</span><span class="sxs-lookup"><span data-stu-id="a2adc-117">Type</span></span>    | <span data-ttu-id="a2adc-118">대상 변경</span><span class="sxs-lookup"><span data-stu-id="a2adc-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a2adc-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a2adc-119">Affected APIs</span></span>

- <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType>
