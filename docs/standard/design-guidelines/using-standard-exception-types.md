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
ms.openlocfilehash: b8e05f22a66fabeab28cc83a074471df29aae218
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291359"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="4b459-102">표준 예외 형식 사용</span><span class="sxs-lookup"><span data-stu-id="4b459-102">Using Standard Exception Types</span></span>
<span data-ttu-id="4b459-103">이 섹션에서는 프레임 워크에서 제공 하는 표준 예외 및 사용에 대 한 세부 정보를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="4b459-104">이 목록은 완전 한 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="4b459-105">다른 프레임 워크 예외 형식의 사용에 대 한 .NET Framework 참조 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b459-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>

## <a name="exception-and-systemexception"></a><span data-ttu-id="4b459-106">예외 및 SystemException</span><span class="sxs-lookup"><span data-stu-id="4b459-106">Exception and SystemException</span></span>
 <span data-ttu-id="4b459-107">❌또는를 throw 하지 않습니다 <xref:System.Exception?displayProperty=nameWithType> <xref:System.SystemException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4b459-107">❌ DO NOT throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="4b459-108">❌`System.Exception`를 다시 throw 하지 `System.SystemException` 않는 한, 프레임 워크 코드에서 또는를 catch 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-108">❌ DO NOT catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>

 <span data-ttu-id="4b459-109">❌`System.Exception` `System.SystemException` 최상위 예외 처리기를 제외 하 고 또는를 CATCH 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-109">❌ AVOID catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>

## <a name="applicationexception"></a><span data-ttu-id="4b459-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="4b459-110">ApplicationException</span></span>
 <span data-ttu-id="4b459-111">❌에서 throw 하거나 파생 하지 않습니다 <xref:System.ApplicationException> .</span><span class="sxs-lookup"><span data-stu-id="4b459-111">❌ DO NOT throw or derive from <xref:System.ApplicationException>.</span></span>

## <a name="invalidoperationexception"></a><span data-ttu-id="4b459-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="4b459-112">InvalidOperationException</span></span>
 <span data-ttu-id="4b459-113">개체가 적절 하지 않은 <xref:System.InvalidOperationException> 상태인 경우 ✔️를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-113">✔️ DO throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="4b459-114">ArgumentException, ArgumentNullException 및 ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="4b459-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>
 <span data-ttu-id="4b459-115"><xref:System.ArgumentException>잘못 된 인수가 멤버로 전달 되는 경우이를 throw 하거나 하위 형식 중 하나를 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-115">✔️ DO throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="4b459-116">해당 하는 경우 가장 많이 파생 된 예외 형식을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-116">Prefer the most derived exception type, if applicable.</span></span>

 <span data-ttu-id="4b459-117">✔️는 `ParamName` 의 서브 클래스 중 하나를 throw 할 때 속성을 설정 합니다 `ArgumentException` .</span><span class="sxs-lookup"><span data-stu-id="4b459-117">✔️ DO set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>

 <span data-ttu-id="4b459-118">이 속성은 예외를 throw 한 매개 변수의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="4b459-119">생성자 오버 로드 중 하나를 사용 하 여 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-119">Note that the property can be set using one of the constructor overloads.</span></span>

 <span data-ttu-id="4b459-120">✔️ `value` 는 속성 setter의 암시적 값 매개 변수 이름으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-120">✔️ DO use `value` for the name of the implicit value parameter of property setters.</span></span>

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="4b459-121">NullReferenceException, IndexOutOfRangeException 및 AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="4b459-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>
 <span data-ttu-id="4b459-122">❌공개적으로 호출할 수 있는 Api가, 또는를 명시적으로 또는 암시적으로 throw 하지 않도록 <xref:System.NullReferenceException> <xref:System.AccessViolationException> <xref:System.IndexOutOfRangeException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-122">❌ DO NOT allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="4b459-123">이러한 예외는 실행 엔진에서 예약 및 throw 되며 대부분의 경우에는 버그를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>

 <span data-ttu-id="4b459-124">이러한 예외가 발생 하지 않도록 인수 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="4b459-125">이러한 예외를 throw 하면 시간이 지남에 따라 변경 될 수 있는 메서드의 구현 세부 정보가 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>

## <a name="stackoverflowexception"></a><span data-ttu-id="4b459-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="4b459-126">StackOverflowException</span></span>
 <span data-ttu-id="4b459-127">❌명시적으로 throw 하지 않습니다 <xref:System.StackOverflowException> .</span><span class="sxs-lookup"><span data-stu-id="4b459-127">❌ DO NOT explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="4b459-128">예외는 CLR 에서만 명시적으로 throw 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-128">The exception should be explicitly thrown only by the CLR.</span></span>

 <span data-ttu-id="4b459-129">❌Catch 하지 않습니다 `StackOverflowException` .</span><span class="sxs-lookup"><span data-stu-id="4b459-129">❌ DO NOT catch `StackOverflowException`.</span></span>

 <span data-ttu-id="4b459-130">임의 스택 오버플로가 있는 상태에서 일관성을 유지 하는 관리 코드를 작성 하는 것은 거의 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="4b459-131">CLR의 관리 되지 않는 부분은 프로브를 사용 하 여 스택 오버플로를 임의 스택 오버플로 로부터 백업 하지 않고 잘 정의 된 위치로 이동 하 여 일관성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>

## <a name="outofmemoryexception"></a><span data-ttu-id="4b459-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="4b459-132">OutOfMemoryException</span></span>
 <span data-ttu-id="4b459-133">❌명시적으로 throw 하지 않습니다 <xref:System.OutOfMemoryException> .</span><span class="sxs-lookup"><span data-stu-id="4b459-133">❌ DO NOT explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="4b459-134">이 예외는 CLR 인프라 에서만 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-134">This exception is to be thrown only by the CLR infrastructure.</span></span>

## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="4b459-135">ComException, SEHException 및 ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="4b459-135">ComException, SEHException, and ExecutionEngineException</span></span>
 <span data-ttu-id="4b459-136">❌, 및을 명시적으로 throw 하지 마십시오 <xref:System.Runtime.InteropServices.COMException> <xref:System.ExecutionEngineException> <xref:System.Runtime.InteropServices.SEHException> .</span><span class="sxs-lookup"><span data-stu-id="4b459-136">❌ DO NOT explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="4b459-137">이러한 예외는 CLR 인프라에 의해서만 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b459-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>

 <span data-ttu-id="4b459-138">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="4b459-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4b459-139">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4b459-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4b459-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b459-140">See also</span></span>

- [<span data-ttu-id="4b459-141">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4b459-141">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="4b459-142">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4b459-142">Design Guidelines for Exceptions</span></span>](exceptions.md)
