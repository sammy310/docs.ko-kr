---
ms.openlocfilehash: fabbc9a51f61a703ce97db50ab251e7a13ffe348
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144485"
---
### <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="edf3f-101">CounterSet.CreateCounterSetInstance는 인스턴스가 이미 있는 경우 이제 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="edf3f-101">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="edf3f-102">.NET 5.0부터 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType>은 카운터 집합이 이미 있는 경우 <xref:System.ArgumentException> 대신 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="edf3f-102">Starting in .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

#### <a name="change-description"></a><span data-ttu-id="edf3f-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="edf3f-103">Change description</span></span>

<span data-ttu-id="edf3f-104">.NET Framework 및 .NET Core 1.0~3.1에서 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출하여 카운터 집합의 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edf3f-104">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="edf3f-105">그러나 카운터 집합이 이미 있는 경우 메서드는 <xref:System.ArgumentException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="edf3f-105">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="edf3f-106">.NET 5.0 이상 버전에서 <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출하고 카운터 집합이 있으면 <xref:System.InvalidOperationException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="edf3f-106">In .NET 5.0 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="edf3f-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="edf3f-107">Version introduced</span></span>

<span data-ttu-id="edf3f-108">5.0 미리 보기 5</span><span class="sxs-lookup"><span data-stu-id="edf3f-108">5.0 Preview 5</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="edf3f-109">권장 조치</span><span class="sxs-lookup"><span data-stu-id="edf3f-109">Recommended action</span></span>

<span data-ttu-id="edf3f-110"><xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>를 호출할 때 앱에서 <xref:System.ArgumentException> 예외를 catch하는 경우 <xref:System.InvalidOperationException> 예외도 catch하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="edf3f-110">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="edf3f-111"><xref:System.ArgumentException> 예외를 catch하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edf3f-111">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

#### <a name="category"></a><span data-ttu-id="edf3f-112">범주</span><span class="sxs-lookup"><span data-stu-id="edf3f-112">Category</span></span>

<span data-ttu-id="edf3f-113">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="edf3f-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="edf3f-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="edf3f-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
