---
title: SYSLIB0004 경고
description: 컴파일 시간 경고 SYSLIB0004를 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: ba7cd8a890a89000b241d286c9d8069ba1398849
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333130"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a><span data-ttu-id="e3e80-103">SYSLIB0004: CER(제약이 있는 실행 영역) 기능이 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="e3e80-103">SYSLIB0004: The constrained execution region (CER) feature is not supported</span></span>

<span data-ttu-id="e3e80-104">[CER(제약이 있는 실행 영역)](../../framework/performance/constrained-execution-regions.md) 기능은 .NET Framework 에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e80-104">The [Constrained execution regions (CER)](../../framework/performance/constrained-execution-regions.md) feature is supported only in .NET Framework.</span></span> <span data-ttu-id="e3e80-105">따라서 다양한 CER 관련 API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e80-105">As such, various CER-related APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="e3e80-106">이러한 API를 사용하면 컴파일 시간에 `SYSLIB0004` 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e80-106">Using these APIs generates warning `SYSLIB0004` at compile time.</span></span>

<span data-ttu-id="e3e80-107">다음은 사용되지 않는 CER 관련 API입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e80-107">The following CER-related APIs are obsolete:</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="e3e80-108">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e3e80-108">See also</span></span>

- [<span data-ttu-id="e3e80-109">제약이 있는 실행 영역</span><span class="sxs-lookup"><span data-stu-id="e3e80-109">Constrained execution regions</span></span>](../../framework/performance/constrained-execution-regions.md)
