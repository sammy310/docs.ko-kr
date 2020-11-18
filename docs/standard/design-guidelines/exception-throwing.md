---
title: 예외 Throw
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 6f22878a9ddfb394f6705a335930ef2cc270895f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821270"
---
# <a name="exception-throwing"></a><span data-ttu-id="4025e-102">예외 Throw</span><span class="sxs-lookup"><span data-stu-id="4025e-102">Exception Throwing</span></span>
<span data-ttu-id="4025e-103">이 섹션에서 설명 하는 예외를 throw 하는 지침에는 실행 실패의 의미를 올바르게 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="4025e-104">멤버가 수행 하도록 디자인 된 작업 (멤버 이름에서 의미 함)을 수행할 수 없을 때마다 실행 실패가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="4025e-105">예를 들어 `OpenFile` 메서드가 열린 파일 핸들을 호출자에 게 반환할 수 없는 경우 실행 실패로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>

 <span data-ttu-id="4025e-106">대부분의 개발자는 0 또는 null 참조로 나누기와 같은 사용 오류에 대 한 예외를 사용 하는 데 익숙해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="4025e-107">프레임 워크에서 예외는 실행 오류를 포함 하 여 모든 오류 조건에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>

 <span data-ttu-id="4025e-108">❌ 오류 코드를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-108">❌ DO NOT return error codes.</span></span>

 <span data-ttu-id="4025e-109">예외는 프레임 워크에서 오류를 보고 하는 기본 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>

 <span data-ttu-id="4025e-110">예외를 throw 하 여 실행 오류를 보고 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-110">✔️ DO report execution failures by throwing exceptions.</span></span>

 <span data-ttu-id="4025e-111">`System.Environment.FailFast`코드에서 추가 실행에 안전 하지 않은 상황이 발생할 경우 예외를 throw 하는 대신 (.NET Framework 2.0 기능)를 호출 하 여 프로세스를 종료 하는 것이 좋습니다. ✔️</span><span class="sxs-lookup"><span data-stu-id="4025e-111">✔️ CONSIDER terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>

 <span data-ttu-id="4025e-112">❌ 가능 하면 일반적인 제어 흐름에는 예외를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="4025e-112">❌ DO NOT use exceptions for the normal flow of control, if possible.</span></span>

 <span data-ttu-id="4025e-113">시스템 오류와 경합 상태가 발생할 수 있는 작업을 제외 하 고, 프레임 워크 디자이너는 사용자가 예외를 throw 하지 않는 코드를 작성할 수 있도록 Api를 디자인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="4025e-114">예를 들어 사용자가 예외를 throw 하지 않는 코드를 작성할 수 있도록 멤버를 호출 하기 전에 사전 조건을 확인 하는 방법을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>

 <span data-ttu-id="4025e-115">다른 멤버의 사전 조건을 확인 하는 데 사용 되는 멤버를 테스터 라고 하며 실제로 작업을 수행 하는 멤버를 doer 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>

 <span data-ttu-id="4025e-116">Tester-Doer 패턴에 허용 되지 않는 성능 오버 헤드가 있을 수 있는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="4025e-117">이러한 경우에는 Try-Parse 패턴을 고려해 야 합니다. 자세한 내용은 [예외 및 성능](exceptions-and-performance.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4025e-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](exceptions-and-performance.md) for more information).</span></span>

 <span data-ttu-id="4025e-118">✔️ 예외 throw의 성능 영향을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-118">✔️ CONSIDER the performance implications of throwing exceptions.</span></span> <span data-ttu-id="4025e-119">초당 100를 초과 하는 Throw 요금은 대부분의 응용 프로그램 성능에 큰 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>

 <span data-ttu-id="4025e-120">✔️는 시스템 오류가 아닌 멤버 계약 위반으로 인해 공개적으로 호출할 수 있는 멤버에서 throw 된 모든 예외를 문서화 하 고 계약의 일부로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-120">✔️ DO document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>

 <span data-ttu-id="4025e-121">계약의 일부인 예외는 한 버전에서 다음 버전으로 변경 되어서는 안 됩니다. 즉, 예외 형식은 변경 되지 않아야 하 고 새 예외는 추가 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>

 <span data-ttu-id="4025e-122">❌ 일부 옵션을 기반으로 throw 또는 사용 하지 않을 수 있는 public 멤버가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-122">❌ DO NOT have public members that can either throw or not based on some option.</span></span>

 <span data-ttu-id="4025e-123">❌ 예외를 반환 값 또는 매개 변수로 반환 하는 public 멤버가 없습니다 `out` .</span><span class="sxs-lookup"><span data-stu-id="4025e-123">❌ DO NOT have public members that return exceptions as the return value or an `out` parameter.</span></span>

 <span data-ttu-id="4025e-124">공용 Api에서 예외를 throw 하는 대신 예외를 반환 하면 예외 기반 오류 보고의 많은 이점이 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>

 <span data-ttu-id="4025e-125">✔️ 예외 작성기 메서드를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-125">✔️ CONSIDER using exception builder methods.</span></span>

 <span data-ttu-id="4025e-126">일반적으로 다른 위치에서 동일한 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="4025e-127">코드의 팽창을 방지 하려면 예외를 만들고 해당 속성을 초기화 하는 도우미 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>

 <span data-ttu-id="4025e-128">또한 예외를 throw 하는 멤버도 인라인 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="4025e-129">작성기 내에서 throw 문을 이동 하면 멤버가 인라인 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>

 <span data-ttu-id="4025e-130">❌ 예외 필터 블록에서 예외를 throw 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-130">❌ DO NOT throw exceptions from exception filter blocks.</span></span>

 <span data-ttu-id="4025e-131">예외 필터에서 예외가 발생 하면 CLR에서 예외를 catch 하 고 필터가 false를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="4025e-132">이 동작은 실행 중인 필터와는 구분 되지 않으며 false를 명시적으로 반환 하므로 디버그 하기가 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>

 <span data-ttu-id="4025e-133">❌ Finally 블록에서 예외를 명시적으로 throw 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-133">❌ AVOID explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="4025e-134">Throw 되는 메서드를 호출 하 여 발생 하는 예외를 암시적으로 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="4025e-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>

 <span data-ttu-id="4025e-135">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="4025e-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4025e-136">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4025e-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4025e-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4025e-137">See also</span></span>

- [<span data-ttu-id="4025e-138">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4025e-138">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="4025e-139">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4025e-139">Design Guidelines for Exceptions</span></span>](exceptions.md)
