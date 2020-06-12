---
title: 정규식의 컴파일 및 다시 사용
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing text with regular expressions, compilation
- searching with regular expressions, compilation
- .NET Framework regular expressions, engines
- .NET Framework regular expressions, compilation
- regular expressions, compilation
- compilation, regular expressions
- pattern-matching with regular expressions, compilation
- regular expressions, engines
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
ms.openlocfilehash: 54f14a4f31bef00dd222686cc523935b2d9dd5fa
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279040"
---
# <a name="compilation-and-reuse-in-regular-expressions"></a><span data-ttu-id="4ee9a-102">정규식의 컴파일 및 다시 사용</span><span class="sxs-lookup"><span data-stu-id="4ee9a-102">Compilation and Reuse in Regular Expressions</span></span>
<span data-ttu-id="4ee9a-103">정규식 엔진이 식을 컴파일하는 방법과 정규식이 캐시되는 방식을 이해하면 정규식을 광범위하게 사용하는 애플리케이션의 성능을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-103">You can optimize the performance of applications that make extensive use of regular expressions by understanding how the regular expression engine compiles expressions and by understanding how regular expressions are cached.</span></span> <span data-ttu-id="4ee9a-104">이 항목에서는 컴파일과 캐시 둘 다에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-104">This topic discusses both compilation and caching.</span></span>  
  
## <a name="compiled-regular-expressions"></a><span data-ttu-id="4ee9a-105">컴파일된 정규식</span><span class="sxs-lookup"><span data-stu-id="4ee9a-105">Compiled Regular Expressions</span></span>  
 <span data-ttu-id="4ee9a-106">기본적으로 정규식 엔진은 정규식을 내부 명령 시퀀스(Microsoft 중간 언어, 즉 MSIL과 다른 고급 코드)로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-106">By default, the regular expression engine compiles a regular expression to a sequence of internal instructions (these are high-level codes that are different from Microsoft intermediate language, or MSIL).</span></span> <span data-ttu-id="4ee9a-107">엔진은 정규식을 실행할 때 내부 코드를 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-107">When the engine executes a regular expression, it interprets the internal codes.</span></span>  
  
 <span data-ttu-id="4ee9a-108"><xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> 옵션으로 <xref:System.Text.RegularExpressions.Regex> 개체를 생성하는 경우 정규식이 고급 정규식 내부 명령 대신 명시적 MSIL 코드로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-108">If a <xref:System.Text.RegularExpressions.Regex> object is constructed with the <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> option, it compiles the regular expression to explicit MSIL code instead of high-level regular expression internal instructions.</span></span> <span data-ttu-id="4ee9a-109">이렇게 하면 .NET의 JIT(Just-In-Time) 컴파일러가 성능 향상을 위해 식을 네이티브 기계어 코드로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-109">This allows .NET's just-in-time (JIT) compiler to convert the expression to native machine code for higher performance.</span></span>  <span data-ttu-id="4ee9a-110"><xref:System.Text.RegularExpressions.Regex> 개체를 구성하는 비용이 더 높을 수 있지만, 이를 사용하여 일치를 수행하는 비용이 훨씬 더 적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-110">The cost of constructing the <xref:System.Text.RegularExpressions.Regex> object may be higher, but the cost of performing matches with it is likely to be much smaller.</span></span>

 <span data-ttu-id="4ee9a-111">한 가지 대안은 미리 컴파일된 정규식을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-111">An alternative is to use precompiled regular expressions.</span></span> <span data-ttu-id="4ee9a-112"><xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A> 메서드를 사용하여 모든 식을 재사용 가능한 DLL로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-112">You can compile all of your expressions into a reusable DLL by using the <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A> method.</span></span> <span data-ttu-id="4ee9a-113">이렇게 하면 컴파일된 정규식의 속도에 따른 이점은 계속 활용하면서 런타임 시 컴파일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-113">This avoids the need to compile at run time while still benefiting from the speed of compiled regular expressions.</span></span>  
  
## <a name="the-regular-expressions-cache"></a><span data-ttu-id="4ee9a-114">정규식 캐시</span><span class="sxs-lookup"><span data-stu-id="4ee9a-114">The Regular Expressions Cache</span></span>  
 <span data-ttu-id="4ee9a-115">성능 향상을 위해 정규식 엔진은 애플리케이션 수준의 컴파일된 정규식 캐시를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-115">To improve performance, the regular expression engine maintains an application-wide cache of compiled regular expressions.</span></span> <span data-ttu-id="4ee9a-116">캐시는 정적 메서드 호출에만 사용되는 정규식 패턴을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-116">The cache stores regular expression patterns that are used only in static method calls.</span></span> <span data-ttu-id="4ee9a-117">인스턴스 메서드에 제공된 정규식 패턴은 캐시되지 않습니다. 따라서 사용할 때마다 식을 고급 바이트 코드로 다시 구문 분석할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-117">(Regular expression patterns supplied to instance methods are not cached.) This avoids the need to reparse an expression into high-level byte code each time it is used.</span></span>  
  
 <span data-ttu-id="4ee9a-118">캐시된 정규식의 최대 개수는 `static`(Visual Basic의 경우 `Shared`) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType> 속성 값에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-118">The maximum number of cached regular expressions is determined by the value of the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="4ee9a-119">기본적으로 정규식 엔진은 최대 15개의 컴파일된 정규식을 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-119">By default, the regular expression engine caches up to 15 compiled regular expressions.</span></span> <span data-ttu-id="4ee9a-120">컴파일된 정규식 개수가 캐시 크기를 초과하면 가장 오래 전에 사용한 정규식이 삭제되고 새 정규식이 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-120">If the number of compiled regular expressions exceeds the cache size, the least recently used regular expression is discarded and the new regular expression is cached.</span></span>  
  
 <span data-ttu-id="4ee9a-121">애플리케이션은 다음 두 가지 방법 중 하나를 사용하여 정규식을 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-121">Your application can reuse regular expressions in one of the following two ways:</span></span>  
  
- <span data-ttu-id="4ee9a-122"><xref:System.Text.RegularExpressions.Regex> 개체의 정적 메서드를 사용하여 정규식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-122">By using a static method of the <xref:System.Text.RegularExpressions.Regex> object to define the regular expression.</span></span> <span data-ttu-id="4ee9a-123">다른 정적 메서드 호출에서 이미 정의된 정규식 패턴을 사용하는 경우 정규식 엔진이 캐시에서 이를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-123">If you're using a regular expression pattern that has already been defined by another static method call, the regular expression engine will try to retrieve it from the cache.</span></span> <span data-ttu-id="4ee9a-124">캐시에 없으면 엔진이 정규식을 컴파일하고 캐시에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-124">If it's not available in the cache, the engine will compile the regular expression and add it to the cache.</span></span>
  
- <span data-ttu-id="4ee9a-125">해당 정규식 패턴이 필요할 때까지 기존 <xref:System.Text.RegularExpressions.Regex> 개체를 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-125">By reusing an existing <xref:System.Text.RegularExpressions.Regex> object as long as its regular expression pattern is needed.</span></span>  
  
 <span data-ttu-id="4ee9a-126">개체 인스턴스화 및 정규식 컴파일의 오버헤드 때문에 수많은 <xref:System.Text.RegularExpressions.Regex> 개체를 만들고 금세 삭제할 경우 매우 큰 비용이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-126">Because of the overhead of object instantiation and regular expression compilation, creating and rapidly destroying numerous <xref:System.Text.RegularExpressions.Regex> objects is a very expensive process.</span></span> <span data-ttu-id="4ee9a-127">다수의 정규식을 사용하는 애플리케이션의 경우 정적 `Regex` 메서드 호출을 사용하고 정규식 캐시의 크기를 늘려 성능을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ee9a-127">For applications that use a large number of different regular expressions, you can optimize performance by using calls to static `Regex` methods and possibly by increasing the size of the regular expression cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee9a-128">참조</span><span class="sxs-lookup"><span data-stu-id="4ee9a-128">See also</span></span>

- [<span data-ttu-id="4ee9a-129">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="4ee9a-129">.NET Regular Expressions</span></span>](regular-expressions.md)
