---
title: 표준 예외 형식 사용
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: 6b202d618d9d2216c8998181303250081de6781c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708986"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="df7ae-102">표준 예외 형식 사용</span><span class="sxs-lookup"><span data-stu-id="df7ae-102">Using Standard Exception Types</span></span>
<span data-ttu-id="df7ae-103">이 섹션에서는 프레임 워크에서 제공 하는 표준 예외 및 사용에 대 한 세부 정보를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="df7ae-104">이 목록은 완전 한 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="df7ae-105">다른 프레임 워크 예외 형식의 사용에 대 한 .NET Framework 참조 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df7ae-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>  
  
## <a name="exception-and-systemexception"></a><span data-ttu-id="df7ae-106">예외 및 SystemException</span><span class="sxs-lookup"><span data-stu-id="df7ae-106">Exception and SystemException</span></span>  
 <span data-ttu-id="df7ae-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> 또는 <xref:System.SystemException?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="df7ae-108">**X DO NOT** catch `System.Exception` 또는 `System.SystemException` 프레임 워크 코드에 다시 throw 하려는 경우가 아니면 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-108">**X DO NOT** catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>  
  
 <span data-ttu-id="df7ae-109">**X AVOID** 위해서 `System.Exception` 또는 `System.SystemException`, 최상위 예외 처리기에서를 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-109">**X AVOID** catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>  
  
## <a name="applicationexception"></a><span data-ttu-id="df7ae-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="df7ae-110">ApplicationException</span></span>  
 <span data-ttu-id="df7ae-111">**X DO NOT** throw 하거나이 로부터 파생할 <xref:System.ApplicationException>합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-111">**X DO NOT** throw or derive from <xref:System.ApplicationException>.</span></span>  
  
## <a name="invalidoperationexception"></a><span data-ttu-id="df7ae-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="df7ae-112">InvalidOperationException</span></span>  
 <span data-ttu-id="df7ae-113">**✓ DO** throw 한 <xref:System.InvalidOperationException> 부적절 한 상태에 개체가 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-113">**✓ DO** throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="df7ae-114">ArgumentException, ArgumentNullException 및 ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="df7ae-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>  
 <span data-ttu-id="df7ae-115">**✓ DO** throw <xref:System.ArgumentException> 또는 멤버에 잘못 된 인수가 전달 되 면 그 하위 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-115">**✓ DO** throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="df7ae-116">해당 하는 경우 가장 많이 파생 된 예외 형식을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-116">Prefer the most derived exception type, if applicable.</span></span>  
  
 <span data-ttu-id="df7ae-117">**✓ DO** 설정는 `ParamName` 속성의 서브 클래스 중 하나를 throw 할 때 `ArgumentException`합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-117">**✓ DO** set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>  
  
 <span data-ttu-id="df7ae-118">이 속성은 예외를 throw 한 매개 변수의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="df7ae-119">생성자 오버 로드 중 하나를 사용 하 여 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-119">Note that the property can be set using one of the constructor overloads.</span></span>  
  
 <span data-ttu-id="df7ae-120">**✓ DO** 사용 `value` 속성 setter의 암시적 값 매개 변수 이름에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-120">**✓ DO** use `value` for the name of the implicit value parameter of property setters.</span></span>  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="df7ae-121">NullReferenceException, IndexOutOfRangeException 및 AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="df7ae-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>  
 <span data-ttu-id="df7ae-122">**X DO NOT** 공개적으로 호출할 수 Api 명시적 또는 암시적으로 throw 할 수 있도록 <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, 또는 <xref:System.IndexOutOfRangeException>합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-122">**X DO NOT** allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="df7ae-123">이러한 예외는 실행 엔진에서 예약 및 throw 되며 대부분의 경우에는 버그를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>  
  
 <span data-ttu-id="df7ae-124">이러한 예외가 발생 하지 않도록 인수 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="df7ae-125">이러한 예외를 throw 하면 시간이 지남에 따라 변경 될 수 있는 메서드의 구현 세부 정보가 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>  
  
## <a name="stackoverflowexception"></a><span data-ttu-id="df7ae-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="df7ae-126">StackOverflowException</span></span>  
 <span data-ttu-id="df7ae-127">**X DO NOT** 명시적으로 throw <xref:System.StackOverflowException>합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-127">**X DO NOT** explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="df7ae-128">예외는 CLR 에서만 명시적으로 throw 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-128">The exception should be explicitly thrown only by the CLR.</span></span>  
  
 <span data-ttu-id="df7ae-129">**X DO NOT** catch `StackOverflowException`합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-129">**X DO NOT** catch `StackOverflowException`.</span></span>  
  
 <span data-ttu-id="df7ae-130">임의 스택 오버플로가 있는 상태에서 일관성을 유지 하는 관리 코드를 작성 하는 것은 거의 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="df7ae-131">CLR의 관리 되지 않는 부분은 프로브를 사용 하 여 스택 오버플로를 임의 스택 오버플로 로부터 백업 하지 않고 잘 정의 된 위치로 이동 하 여 일관성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>  
  
## <a name="outofmemoryexception"></a><span data-ttu-id="df7ae-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="df7ae-132">OutOfMemoryException</span></span>  
 <span data-ttu-id="df7ae-133">**X DO NOT** 명시적으로 throw <xref:System.OutOfMemoryException>합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-133">**X DO NOT** explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="df7ae-134">이 예외는 CLR 인프라 에서만 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-134">This exception is to be thrown only by the CLR infrastructure.</span></span>  
  
## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="df7ae-135">ComException, SEHException 및 ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="df7ae-135">ComException, SEHException, and ExecutionEngineException</span></span>  
 <span data-ttu-id="df7ae-136">**X DO NOT** 명시적으로 throw <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, 및 <xref:System.Runtime.InteropServices.SEHException>합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-136">**X DO NOT** explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="df7ae-137">이러한 예외는 CLR 인프라에 의해서만 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ae-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>  
  
 <span data-ttu-id="df7ae-138">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="df7ae-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="df7ae-139">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="df7ae-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7ae-140">참조</span><span class="sxs-lookup"><span data-stu-id="df7ae-140">See also</span></span>

- [<span data-ttu-id="df7ae-141">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="df7ae-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="df7ae-142">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="df7ae-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
