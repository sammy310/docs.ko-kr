---
title: SYSLIB0004 경고
description: 컴파일 시간 경고 SYSLIB0004를 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: f48fd8915a13f9f99b091eca895dcd74a8f18907
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440726"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a><span data-ttu-id="0c803-103">SYSLIB0004: CER(제약이 있는 실행 영역) 기능이 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="0c803-103">SYSLIB0004: The constrained execution region (CER) feature is not supported</span></span>

<span data-ttu-id="0c803-104">[CER(제약이 있는 실행 영역)](../../framework/performance/constrained-execution-regions.md) 기능은 .NET Framework 에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-104">The [Constrained execution regions (CER)](../../framework/performance/constrained-execution-regions.md) feature is supported only in .NET Framework.</span></span> <span data-ttu-id="0c803-105">따라서 다양한 CER 관련 API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-105">As such, various CER-related APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="0c803-106">이러한 API를 사용하면 컴파일 시간에 `SYSLIB0004` 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-106">Using these APIs generates warning `SYSLIB0004` at compile time.</span></span>

<span data-ttu-id="0c803-107">다음은 사용되지 않는 CER 관련 API입니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-107">The following CER-related APIs are obsolete:</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="0c803-108">해결 방법</span><span class="sxs-lookup"><span data-stu-id="0c803-108">Workarounds</span></span>

- <span data-ttu-id="0c803-109">메서드에 CER 특성을 적용한 경우 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-109">If you have applied a CER attribute to a method, remove the attribute.</span></span> <span data-ttu-id="0c803-110">이러한 특성은 .NET 5.0 이상 버전에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-110">These attributes have no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  // REMOVE the attribute below.
  [ReliabilityContract(Consistency.WillNotCorruptState, Cer.Success)]
  public void DoSomething()
  {
  }

  // REMOVE the attribute below.
  [PrePrepareMethod]
  public void DoSomething()
  {
  }
  ```

- <span data-ttu-id="0c803-111">`RuntimeHelpers.ProbeForSufficientStack` 또는 `RuntimeHelpers.PrepareContractedDelegate`를 호출하는 경우 호출을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-111">If you are calling `RuntimeHelpers.ProbeForSufficientStack` or `RuntimeHelpers.PrepareContractedDelegate`, remove the call.</span></span> <span data-ttu-id="0c803-112">이러한 호출은 .NET 5.0 이상 버전에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-112">These calls have no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  public void DoSomething()
  {
      // REMOVE the call below.
      RuntimeHelpers.ProbeForSufficientStack();

      // (Remainder of your method logic here.)
  }
  ```

- <span data-ttu-id="0c803-113">`RuntimeHelpers.PrepareConstrainedRegions`를 호출하는 경우 호출을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-113">If you are calling `RuntimeHelpers.PrepareConstrainedRegions`, remove the call.</span></span> <span data-ttu-id="0c803-114">이 호출은 .NET 5.0 이상 버전에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-114">This call has no effect in .NET 5.0 and later versions.</span></span>

  ```csharp
  public void DoSomething_Old()
  {
      // REMOVE the call below.
      RuntimeHelpers.PrepareConstrainedRegions();
      try
      {
          // try code
      }
      finally
      {
          // cleanup code
      }
  }

  public void DoSomething_Corrected()
  {
      // There is no call to PrepareConstrainedRegions. It's a normal try / finally block.

      try
      {
          // try code
      }
      finally
      {
          // cleanup code
      }
  }
  ```

- <span data-ttu-id="0c803-115">`RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup`을 호출하는 경우 호출을 표준 _try/catch/finally_ 블록으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0c803-115">If you are calling `RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup`, replace the call with a standard _try / catch / finally_ block.</span></span>

  ```csharp
  // The sample below produces warning SYSLIB0004.
  public void DoSomething_Old()
  {
      RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(MyTryCode, MyCleanupCode, null);
  }
  public void MyTryCode(object state) { /* try code */ }
  public void MyCleanupCode(object state, bool exceptionThrown) { /* cleanup code */ }

  // The corrected sample below does not produce warning SYSLIB0004.
  public void DoSomething_Corrected()
  {
      try
      {
          // try code
      }
      catch (Exception ex)
      {
          // exception handling code
      }
      finally
      {
          // cleanup code
      }
  }
  ```

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="0c803-116">추가 정보</span><span class="sxs-lookup"><span data-stu-id="0c803-116">See also</span></span>

- [<span data-ttu-id="0c803-117">제약이 있는 실행 영역</span><span class="sxs-lookup"><span data-stu-id="0c803-117">Constrained execution regions</span></span>](../../framework/performance/constrained-execution-regions.md)
