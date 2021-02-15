---
description: '자세한 정보: 연산자 오버로드'
title: 연산자 오버로드
ms.date: 10/22/2008
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: e6552f35081afa542e4dc14239206a63c7c1bd59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713327"
---
# <a name="operator-overloads"></a><span data-ttu-id="5ab73-103">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="5ab73-103">Operator Overloads</span></span>

<span data-ttu-id="5ab73-104">연산자 오버로드를 사용하면 프레임워크 형식이 기본 제공 언어 기본 형식인 것처럼 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-104">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="5ab73-105">연산자 오버로드는 상황에 따라 허용되고 유용하지만 주의해서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-105">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="5ab73-106">프레임워크 디자이너에서 간단한 메서드가 되어야 하는 작업에 연산자를 사용하기 시작하는 경우처럼 연산자 오버로드가 남용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-106">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="5ab73-107">다음 지침은 연산자 오버로드를 사용할 시기 및 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-107">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="5ab73-108">❌ 기본(기본 제공) 형식처럼 보여야 하는 형식을 제외하고는 연산자 오버로드를 정의하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-108">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="5ab73-109">✔️ 기본 형식처럼 보여야 하는 형식에서는 연산자 오버로드를 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-109">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="5ab73-110">예를 들어 <xref:System.String?displayProperty=nameWithType>에는 `operator==` 및 `operator!=`가 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-110">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="5ab73-111">✔️ 숫자를 나타내는 구조체에는 연산자 오버로드를 정의하세요(예: <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="5ab73-111">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="5ab73-112">❌ 연산자 오버로드를 정의할 때는 잔꾀를 부리지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5ab73-112">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="5ab73-113">연산자 오버로드는 작업의 결과가 즉시 명확하게 나타나는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-113">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="5ab73-114">예를 들어 다른 `DateTime`에서 하나의 <xref:System.DateTime>을 빼고 <xref:System.TimeSpan>을 가져오는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-114">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="5ab73-115">그러나 논리 공용 구조체 연산자를 사용하여 두 데이터베이스 쿼리를 통합하거나 시프트 연산자를 사용하여 스트림에 쓰는 것은 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-115">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="5ab73-116">❌ 피연산자 중 하나 이상이 오버로드를 정의하는 형식이 아닐 경우 연산자 오버로드를 제공하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5ab73-116">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="5ab73-117">✔ 대칭 방식으로 연산자를 오버로드하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab73-117">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="5ab73-118">예를 들어 `operator==`를 오버로드하는 경우 `operator!=`도 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-118">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="5ab73-119">마찬가지로 `operator<`를 오버로드하는 경우 `operator>`도 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-119">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="5ab73-120">✔️ 오버로드된 각 연산자에 해당하는 식별 이름과 함께 메서드를 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-120">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="5ab73-121">많은 언어에서 연산자 오버로드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-121">Many languages do not support operator overloading.</span></span> <span data-ttu-id="5ab73-122">따라서 연산자를 오버로드하는 형식에는 동일한 기능을 제공하는 적절한 도메인 특정 이름과 함께 보조 메서드를 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-122">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="5ab73-123">다음 표에는 연산자 목록과 해당하는 메서드 식별 이름이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-123">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="5ab73-124">C# 연산자 기호</span><span class="sxs-lookup"><span data-stu-id="5ab73-124">C# Operator Symbol</span></span>|<span data-ttu-id="5ab73-125">메타데이터 이름</span><span class="sxs-lookup"><span data-stu-id="5ab73-125">Metadata Name</span></span>|<span data-ttu-id="5ab73-126">친숙한 이름</span><span class="sxs-lookup"><span data-stu-id="5ab73-126">Friendly Name</span></span>|
|-------------------------|-------------------|-------------------|
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|
|`+ (binary)`|`op_Addition`|`Add`|
|`- (binary)`|`op_Subtraction`|`Subtract`|
|`* (binary)`|`op_Multiply`|`Multiply`|
|`/`|`op_Division`|`Divide`|
|`%`|`op_Modulus`|`Mod or Remainder`|
|`^`|`op_ExclusiveOr`|`Xor`|
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|
|`&&`|`op_LogicalAnd`|`And`|
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|
|`=`|`op_Assign`|`Assign`|
|`<<`|`op_LeftShift`|`LeftShift`|
|`>>`|`op_RightShift`|`RightShift`|
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|
|`==`|`op_Equality`|`Equals`|
|`!=`|`op_Inequality`|`Equals`|
|`>`|`op_GreaterThan`|`CompareTo`|
|`<`|`op_LessThan`|`CompareTo`|
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|
|`<=`|`op_LessThanOrEqual`|`CompareTo`|
|`*=`|`op_MultiplicationAssignment`|`Multiply`|
|`-=`|`op_SubtractionAssignment`|`Subtract`|
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|
|`%=`|`op_ModulusAssignment`|`Mod`|
|`+=`|`op_AdditionAssignment`|`Add`|
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|
|`,`|`op_Comma`|`Comma`|
|`/=`|`op_DivisionAssignment`|`Divide`|
|`--`|`op_Decrement`|`Decrement`|
|`++`|`op_Increment`|`Increment`|
|`- (unary)`|`op_UnaryNegation`|`Negate`|
|`+ (unary)`|`op_UnaryPlus`|`Plus`|
|`~`|`op_OnesComplement`|`OnesComplement`|

### <a name="overloading-operator-"></a><span data-ttu-id="5ab73-127">Operator == 오버로드</span><span class="sxs-lookup"><span data-stu-id="5ab73-127">Overloading Operator ==</span></span>

 <span data-ttu-id="5ab73-128">`operator ==` 오버로드는 매우 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-128">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="5ab73-129">연산자의 의미 체계는 <xref:System.Object.Equals%2A?displayProperty=nameWithType>과 같은 여러 다른 멤버와 호환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-129">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="5ab73-130">변환 연산자</span><span class="sxs-lookup"><span data-stu-id="5ab73-130">Conversion Operators</span></span>

 <span data-ttu-id="5ab73-131">변환 연산자는 형식 간의 변환을 허용하는 단항 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-131">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="5ab73-132">연산자는 피연산자 또는 반환 형식에서 정적 멤버로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-132">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="5ab73-133">변환 연산자에는 암시적과 명시적이라는 두 가지 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-133">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="5ab73-134">❌ 최종 사용자가 이러한 변환을 명확하게 예상하지 못하는 경우 변환 연산자를 제공하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5ab73-134">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="5ab73-135">❌ 형식의 도메인 외부에서 변환 연산자를 정의하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5ab73-135">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="5ab73-136">예를 들어 <xref:System.Int32>, <xref:System.Double>, <xref:System.Decimal>은 모두 숫자 형식이지만 <xref:System.DateTime>은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-136">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="5ab73-137">따라서 `Double(long)`을 `DateTime`으로 변환하는 변환 연산자가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-137">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="5ab73-138">이런 경우에는 생성자를 사용하는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-138">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="5ab73-139">❌ 변환이 잠재적으로 손실될 수 있는 경우 암시적 변환 연산자를 제공하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5ab73-139">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="5ab73-140">예를 들어 `Double`은 `Int32`보다 범위가 더 넓기 때문에 `Double`에서 `Int32`로 암시적 변환이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-140">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="5ab73-141">명시적 변환 연산자는 변환이 잠재적으로 손실될 수 있는 경우에도 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-141">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="5ab73-142">❌ 암시적 캐스트에서 예외를 throw하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5ab73-142">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="5ab73-143">최종 사용자는 변환이 수행되고 있다는 사실을 알 수 없기 때문에 발생하고 있는 상황을 이해하기가 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab73-143">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="5ab73-144">✔️ 캐스트 연산자 호출로 변환이 손실되고 연산자 계약에서는 손실된 변환을 허용하지 않는 경우 <xref:System.InvalidCastException?displayProperty=nameWithType>을 throw하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab73-144">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="5ab73-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="5ab73-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="5ab73-146">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5ab73-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="5ab73-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ab73-147">See also</span></span>

- [<span data-ttu-id="5ab73-148">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="5ab73-148">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="5ab73-149">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="5ab73-149">Framework Design Guidelines</span></span>](index.md)
