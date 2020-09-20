---
ms.openlocfilehash: 85488de561a2298f2ff4009ec78b9a6e294053f3
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598166"
---
### <a name="threadabort-is-obsolete"></a><span data-ttu-id="7ac48-101">Thread.Abort는 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="7ac48-101">Thread.Abort is obsolete</span></span>

<span data-ttu-id="7ac48-102"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> API는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-102">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="7ac48-103">해당 메서드가 호출되는 경우 .NET 5.0 이상 버전을 대상으로 하는 프로젝트에서는 컴파일 시간 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-103">Projects that target .NET 5.0 or a later version will encounter compile-time warnings if these methods are called.</span></span> <span data-ttu-id="7ac48-104">경고를 제거하면 런타임에 <xref:System.PlatformNotSupportedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-104">If you suppress the warnings, a <xref:System.PlatformNotSupportedException> will be thrown at run time.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7ac48-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="7ac48-105">Change description</span></span>

<span data-ttu-id="7ac48-106">이전에는 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 호출이 컴파일 시간 경고가 생성되지 않았지만 해당 메서드는 런타임에 <xref:System.PlatformNotSupportedException>을 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-106">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="7ac48-107">.NET 5.0부터 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>는 경고로 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-107">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="7ac48-108">해당 메서드를 호출하면 컴파일러 경고 `SYSLIB0006`이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-108">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="7ac48-109">메서드의 구현은 변경되지 않으며 계속해서 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-109">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7ac48-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7ac48-110">Reason for change</span></span>

<span data-ttu-id="7ac48-111"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>가 .NET Framework를 제외한 모든 .NET 구현에서 항상 <xref:System.PlatformNotSupportedException>을 throw하는 것을 고려하여 메서드가 호출된 위치로 주의를 끌기 위해 <xref:System.ObsoleteAttribute>가 메서드에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-111">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7ac48-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7ac48-112">Version introduced</span></span>

<span data-ttu-id="7ac48-113">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="7ac48-113">5.0 RC 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7ac48-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7ac48-114">Recommended action</span></span>

- <span data-ttu-id="7ac48-115"><xref:System.Threading.CancellationToken>을 사용하여 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>를 호출하는 대신 작업 단위 처리를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-115">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7ac48-116">다음 예제에서는 <xref:System.Threading.CancellationToken>합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-116">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

  ```csharp
  void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
  {
      if (QueryIsMoreWorkPending())
      {
          // If the CancellationToken is marked as "needs to cancel",
          // this will throw the appropriate exception.
          cancellationToken.ThrowIfCancellationRequested();

          WorkItem work = DequeueWorkItem();
          ProcessWorkItem(work);
      }
  }
  ```

  <span data-ttu-id="7ac48-117">자세한 내용은 [관리형 스레드의 취소](../../../../docs/standard/threading/cancellation-in-managed-threads.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ac48-117">For more information, see [Cancellation in managed threads](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="7ac48-118">컴파일 시간 경고를 제거하려면 경고 코드 `SYSLIB0006`을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-118">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="7ac48-119">경고 코드는 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>와 관련되며 경고 코드를 제거해도 코드에서 다른 사용 중지 경고는 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-119">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="7ac48-120">그러나 경고를 제거하는 대신 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 호출을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-120">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="7ac48-121">프로젝트 파일에서도 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac48-121">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="7ac48-122">범주</span><span class="sxs-lookup"><span data-stu-id="7ac48-122">Category</span></span>

- <span data-ttu-id="7ac48-123">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="7ac48-123">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7ac48-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7ac48-124">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
