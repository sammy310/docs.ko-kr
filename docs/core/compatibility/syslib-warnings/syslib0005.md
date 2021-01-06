---
title: SYSLIB0005 경고
description: 컴파일 시간 경고 SYSLIB0005를 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 1263a4d327c735268f77ed56bdcea6a4cbed4bfa
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596369"
---
# <a name="syslib0005-the-global-assembly-cache-gac-is-not-supported"></a><span data-ttu-id="26da6-103">SYSLIB0005: GAC(전역 어셈블리 캐시)가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="26da6-103">SYSLIB0005: The global assembly cache (GAC) is not supported</span></span>

<span data-ttu-id="26da6-104">.NET Core 및 .NET 5.0 이상 버전에서는 .NET Framework에 있었던 GAC(전역 어셈블리 캐시) 개념이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="26da6-104">.NET Core and .NET 5.0 and later versions eliminate the concept of the global assembly cache (GAC) that was present in .NET Framework.</span></span> <span data-ttu-id="26da6-105">개발자가 이러한 API를 사용하지 않도록 하기 위해 .NET 5.0부터 일부 GAC 관련 API는 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26da6-105">To help steer developers away from these APIs, some GAC-related APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="26da6-106">이러한 API를 사용하면 컴파일 시간에 `SYSLIB0005` 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="26da6-106">Using these APIs generates warning `SYSLIB0005` at compile time.</span></span>

<span data-ttu-id="26da6-107">다음은 사용되지 않는 것으로 표시되는 GAC 관련 API입니다.</span><span class="sxs-lookup"><span data-stu-id="26da6-107">The following GAC-related APIs are marked obsolete:</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType>

  <span data-ttu-id="26da6-108">라이브러리와 앱은 런타임 동작에 대한 결정을 내릴 때 <xref:System.Reflection.Assembly.GlobalAssemblyCache> API를 사용하면 안 됩니다. 이 API는 .NET Core 및 .NET 5+에서 항상 `false`를 반환하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="26da6-108">Libraries and apps should not use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> API to make determinations about run-time behavior, as it always returns `false` in .NET Core and .NET 5+.</span></span>

## <a name="workarounds"></a><span data-ttu-id="26da6-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="26da6-109">Workarounds</span></span>

<span data-ttu-id="26da6-110">애플리케이션이 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 속성을 쿼리하는 경우 호출을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26da6-110">If your application queries the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property, consider removing the call.</span></span> <span data-ttu-id="26da6-111"><xref:System.Reflection.Assembly.GlobalAssemblyCache> 값을 사용하여 런타임에 “GAC의 어셈블리” 흐름과 “GAC에 없는 어셈블리” 흐름을 선택하는 경우 이 흐름이 .NET 5+ 애플리케이션에 적합한지 여부를 재고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26da6-111">If you use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> value to choose between an "assembly in the GAC"-flow vs. an "assembly not in the GAC"-flow at run time, reconsider whether the flow still makes sense for a .NET 5+ application.</span></span>

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="26da6-112">참조</span><span class="sxs-lookup"><span data-stu-id="26da6-112">See also</span></span>

- [<span data-ttu-id="26da6-113">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="26da6-113">Global assembly cache</span></span>](../../../framework/app-domains/gac.md)
