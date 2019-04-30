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
author: KrzysztofCwalina
ms.openlocfilehash: b947c7cce057c060b1ab5054d1227f5703ccbf89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026343"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="01a5f-102">표준 예외 형식 사용</span><span class="sxs-lookup"><span data-stu-id="01a5f-102">Using Standard Exception Types</span></span>
<span data-ttu-id="01a5f-103">이 섹션에서는 프레임 워크 및 사용량의 세부 정보에서 제공 하는 표준 예외를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="01a5f-104">이 목록은 철저 한 있지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="01a5f-105">다른 프레임 워크 예외 형식 사용에 대 한.NET Framework 참조 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="01a5f-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>  
  
## <a name="exception-and-systemexception"></a><span data-ttu-id="01a5f-106">예외 및 SystemException</span><span class="sxs-lookup"><span data-stu-id="01a5f-106">Exception and SystemException</span></span>  
 <span data-ttu-id="01a5f-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> 또는 <xref:System.SystemException?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="01a5f-108">**X DO NOT** catch `System.Exception` 또는 `System.SystemException` 프레임 워크 코드에 다시 throw 하려는 경우가 아니면 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-108">**X DO NOT** catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>  
  
 <span data-ttu-id="01a5f-109">**X AVOID** 위해서 `System.Exception` 또는 `System.SystemException`, 최상위 예외 처리기에서를 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-109">**X AVOID** catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>  
  
## <a name="applicationexception"></a><span data-ttu-id="01a5f-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="01a5f-110">ApplicationException</span></span>  
 <span data-ttu-id="01a5f-111">**X DO NOT** throw 하거나이 로부터 파생할 <xref:System.ApplicationException>합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-111">**X DO NOT** throw or derive from <xref:System.ApplicationException>.</span></span>  
  
## <a name="invalidoperationexception"></a><span data-ttu-id="01a5f-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="01a5f-112">InvalidOperationException</span></span>  
 <span data-ttu-id="01a5f-113">**✓ DO** throw 한 <xref:System.InvalidOperationException> 부적절 한 상태에 개체가 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-113">**✓ DO** throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="01a5f-114">ArgumentException, ArgumentNullException을 및 ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="01a5f-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>  
 <span data-ttu-id="01a5f-115">**✓ DO** throw <xref:System.ArgumentException> 또는 멤버에 잘못 된 인수가 전달 되 면 그 하위 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-115">**✓ DO** throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="01a5f-116">가장 많이 파생 된 예외 형식에 해당 하는 경우에 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-116">Prefer the most derived exception type, if applicable.</span></span>  
  
 <span data-ttu-id="01a5f-117">**✓ DO** 설정는 `ParamName` 속성의 서브 클래스 중 하나를 throw 할 때 `ArgumentException`합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-117">**✓ DO** set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>  
  
 <span data-ttu-id="01a5f-118">이 속성에는 예외를 throw 시킨 매개 변수의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="01a5f-119">생성자 오버 로드 중 하나를 사용 하 여 속성을 설정할 수 있는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-119">Note that the property can be set using one of the constructor overloads.</span></span>  
  
 <span data-ttu-id="01a5f-120">**✓ DO** 사용 `value` 속성 setter의 암시적 값 매개 변수 이름에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-120">**✓ DO** use `value` for the name of the implicit value parameter of property setters.</span></span>  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="01a5f-121">Nullreferenceexception이 고, IndexOutOfRangeException AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="01a5f-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>  
 <span data-ttu-id="01a5f-122">**X DO NOT** 공개적으로 호출할 수 Api 명시적 또는 암시적으로 throw 할 수 있도록 <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, 또는 <xref:System.IndexOutOfRangeException>합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-122">**X DO NOT** allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="01a5f-123">이러한 예외는 예약 및 실행 엔진에서 throw 되 고 대부분의 경우 버그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>  
  
 <span data-ttu-id="01a5f-124">이러한 예외가 throw 되지 않도록 확인 하는 인수를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="01a5f-125">시간이 지남에 따라 변경 될 수 있는 메서드의 구현 세부 정보를 노출 이러한 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>  
  
## <a name="stackoverflowexception"></a><span data-ttu-id="01a5f-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="01a5f-126">StackOverflowException</span></span>  
 <span data-ttu-id="01a5f-127">**X DO NOT** 명시적으로 throw <xref:System.StackOverflowException>합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-127">**X DO NOT** explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="01a5f-128">CLR에서만 예외를 명시적으로 throw 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-128">The exception should be explicitly thrown only by the CLR.</span></span>  
  
 <span data-ttu-id="01a5f-129">**X DO NOT** catch `StackOverflowException`합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-129">**X DO NOT** catch `StackOverflowException`.</span></span>  
  
 <span data-ttu-id="01a5f-130">임의의 스택 오버플로 시 일관성을 유지 하는 관리 되는 코드를 쓸 거의 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="01a5f-131">CLR의 관리 되지 않는 일부 임의 스택 오버플로를 철회 하는 대신 스택 오버플로 잘 정의 된 위치로 이동 하려면 프로브를 사용 하 여 일관성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>  
  
## <a name="outofmemoryexception"></a><span data-ttu-id="01a5f-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="01a5f-132">OutOfMemoryException</span></span>  
 <span data-ttu-id="01a5f-133">**X DO NOT** 명시적으로 throw <xref:System.OutOfMemoryException>합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-133">**X DO NOT** explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="01a5f-134">만 CLR 인프라에서 발생 하 여이 예외가입니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-134">This exception is to be thrown only by the CLR infrastructure.</span></span>  
  
## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="01a5f-135">ComException 고 SEHException, ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="01a5f-135">ComException, SEHException, and ExecutionEngineException</span></span>  
 <span data-ttu-id="01a5f-136">**X DO NOT** 명시적으로 throw <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, 및 <xref:System.Runtime.InteropServices.SEHException>합니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-136">**X DO NOT** explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="01a5f-137">이러한 예외만 CLR 인프라에서 발생 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="01a5f-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>  
  
 <span data-ttu-id="01a5f-138">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="01a5f-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="01a5f-139">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="01a5f-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a5f-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="01a5f-140">See also</span></span>

- [<span data-ttu-id="01a5f-141">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="01a5f-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="01a5f-142">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="01a5f-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
