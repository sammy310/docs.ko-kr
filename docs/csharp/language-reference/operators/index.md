---
title: C# 연산자 - C# 참조
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 13ad16ab768cdaee96cab29811e2ed058dee977a
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512246"
---
# <a name="c-operators-c-reference"></a><span data-ttu-id="6fb8c-102">C# 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6fb8c-102">C# operators (C# reference)</span></span>

<span data-ttu-id="6fb8c-103">C#은 기본 제공 형식에서 지원되는 미리 정의된 여러 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-103">C# provides a number of predefined operators supported by the built-in types.</span></span> <span data-ttu-id="6fb8c-104">예를 들어 [산술 연산자](arithmetic-operators.md)는 기본 제공 숫자 형식의 피연산자를 사용하여 산술 연산을 수행하고 [부울 논리 연산자](boolean-logical-operators.md)는 [bool](../keywords/bool.md) 피연산자를 사용하여 논리 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-104">For example, [arithmetic operators](arithmetic-operators.md) perform arithmetic operations with operands of built-in numeric types and [Boolean logical operators](boolean-logical-operators.md) perform logical operations with the [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="6fb8c-105">사용자 정의 형식은 특정 연산자를 오버로드하여 해당 형식의 피연산자에 대한 해당 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-105">A user-defined type can overload certain operators to define the corresponding behavior for the operands of that type.</span></span> <span data-ttu-id="6fb8c-106">자세한 내용은 [연산자 오버로드](operator-overloading.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-106">For more information, see [Operator overloading](operator-overloading.md).</span></span>

<span data-ttu-id="6fb8c-107">다음 섹션에서는 우선순위가 가장 높은 것부터 시작하여 순서대로 C# 연산자를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-107">The following sections list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="6fb8c-108">각 섹션 내의 연산자는 동일한 우선 순위 수준을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-108">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="6fb8c-109">기본 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-109">Primary operators</span></span>

<span data-ttu-id="6fb8c-110">우선 순위가 가장 높은 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-110">These are the highest precedence operators.</span></span>

<span data-ttu-id="6fb8c-111">[x.y](member-access-operators.md#member-access-operator-) – 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="6fb8c-111">[x.y](member-access-operators.md#member-access-operator-) – member access.</span></span>

<span data-ttu-id="6fb8c-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – null 조건부 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="6fb8c-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – null conditional member access.</span></span> <span data-ttu-id="6fb8c-113">왼쪽 피연산자가 `null`로 확인되면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-113">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="6fb8c-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null 조건부 배열 요소 또는 형식 인덱서 액세스.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null conditional array element or type indexer access.</span></span> <span data-ttu-id="6fb8c-115">왼쪽 피연산자가 `null`로 확인되면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-115">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="6fb8c-116">[f (x)](member-access-operators.md#invocation-operator-) - 메서드 호출 또는 대리자 호출.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-116">[f(x)](member-access-operators.md#invocation-operator-) – method call or delegate invocation.</span></span>

<span data-ttu-id="6fb8c-117">[&#91;x&#93;](member-access-operators.md#indexer-operator-) – 배열 요소 또는 형식 인덱서 액세스.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – array element or type indexer access.</span></span>

<span data-ttu-id="6fb8c-118">[x++](arithmetic-operators.md#increment-operator-) – 후위 증가.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-118">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="6fb8c-119">x의 값을 반환하고 1보다 큰 x 값(일반적으로 정수 1을 더함)으로 스토리지 위치를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-119">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="6fb8c-120">[x--](arithmetic-operators.md#decrement-operator---) –  후위 감소.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-120">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="6fb8c-121">x의 값을 반환하고 1보다 작은 x 값(일반적으로 정수 1을 뺌)으로 스토리지 위치를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-121">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="6fb8c-122">[new](new-operator.md) – 형식 인스턴스화.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-122">[new](new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="6fb8c-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator) – 피연산자를 나타내는 <xref:System.Type> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-123">[typeof](type-testing-and-conversion-operators.md#typeof-operator) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="6fb8c-124">[checked](../keywords/checked.md) – 정수 연산에 오버플로 검사를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-124">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="6fb8c-125">[unchecked](../keywords/unchecked.md) – 정수 연산에 오버플로 검사를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-125">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="6fb8c-126">이것은 기본 컴파일러 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-126">This is the default compiler behavior.</span></span>

<span data-ttu-id="6fb8c-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – T 형식의 기본값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="6fb8c-128">[nameof](nameof.md) - 변수, 형식 또는 멤버의 단순(정규화되지 않은) 이름을 상수 문자열로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-128">[nameof](nameof.md) - obtains the simple (unqualified) name of a variable, type, or member as a constant string.</span></span>

<span data-ttu-id="6fb8c-129">[delegate](delegate-operator.md) – 대리자 인스턴스를 선언하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-129">[delegate](delegate-operator.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="6fb8c-130">[sizeof](sizeof.md) – 형식 피연산자의 크기(바이트)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-130">[sizeof](sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="6fb8c-131">[stackalloc](stackalloc.md) - 스택의 메모리 블록을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-131">[stackalloc](stackalloc.md) - allocates a block of memory on the stack.</span></span>

<span data-ttu-id="6fb8c-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – 멤버 액세스와 결합된 포인터 간접 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – pointer indirection combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="6fb8c-133">단항 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-133">Unary operators</span></span>

<span data-ttu-id="6fb8c-134">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-134">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-135">[+x](addition-operator.md) – x의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-135">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="6fb8c-136">[-x](subtraction-operator.md) – 숫자 부정</span><span class="sxs-lookup"><span data-stu-id="6fb8c-136">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="6fb8c-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – 논리 부정</span><span class="sxs-lookup"><span data-stu-id="6fb8c-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="6fb8c-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – 비트 보수</span><span class="sxs-lookup"><span data-stu-id="6fb8c-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="6fb8c-139">[++x](arithmetic-operators.md#increment-operator-) – 전위 증가</span><span class="sxs-lookup"><span data-stu-id="6fb8c-139">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="6fb8c-140">1보다 큰 x 값(일반적으로 정수 1을 더함)으로 스토리지 위치를 업데이트한 후 x의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-140">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="6fb8c-141">[--x](arithmetic-operators.md#decrement-operator---) – 전위 감소</span><span class="sxs-lookup"><span data-stu-id="6fb8c-141">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="6fb8c-142">1보다 작은 x 값(일반적으로 정수 1을 뺌)으로 스토리지 위치를 업데이트한 후 x의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-142">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="6fb8c-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-) – 형식 캐스팅</span><span class="sxs-lookup"><span data-stu-id="6fb8c-143">[(T)x](type-testing-and-conversion-operators.md#cast-operator-) – type casting.</span></span>

<span data-ttu-id="6fb8c-144">[await](../keywords/await.md) – `Task`를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-144">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="6fb8c-145">[&x](pointer-related-operators.md#address-of-operator-) – 변수의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-145">[&x](pointer-related-operators.md#address-of-operator-) – address of a variable.</span></span>

<span data-ttu-id="6fb8c-146">[\* x](pointer-related-operators.md#pointer-indirection-operator-) – 포인터 간접 참조 또는 역참조입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-) – pointer indirection, or dereference.</span></span>

<span data-ttu-id="6fb8c-147">[true 연산자](true-false-operators.md) - [bool](../keywords/bool.md) 값 `true`를 반환하여 피연산자가 확실히 true임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-147">[true operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="6fb8c-148">[false 연산자](true-false-operators.md) - [bool](../keywords/bool.md) 값 `true`를 반환하여 피연산자가 확실히 false임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-148">[false operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="6fb8c-149">곱하기 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-149">Multiplicative operators</span></span>

<span data-ttu-id="6fb8c-150">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-150">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – 곱하기</span><span class="sxs-lookup"><span data-stu-id="6fb8c-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="6fb8c-152">[x / y](arithmetic-operators.md#division-operator-) – 나누기</span><span class="sxs-lookup"><span data-stu-id="6fb8c-152">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="6fb8c-153">피연산자가 정수인 경우 결과는 0으로 잘린 정수입니다(예: `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="6fb8c-153">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="6fb8c-154">[x % y](arithmetic-operators.md#remainder-operator-) - 나머지.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-154">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="6fb8c-155">피연산자가 정수인 경우 x를 y로 나눈 나머지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-155">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="6fb8c-156">`q = x / y`이고 `r = x % y`인 경우 `x = q * y + r`입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-156">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="6fb8c-157">더하기 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-157">Additive operators</span></span>

<span data-ttu-id="6fb8c-158">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-158">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-159">[x + y](arithmetic-operators.md#addition-operator-) – 더하기</span><span class="sxs-lookup"><span data-stu-id="6fb8c-159">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="6fb8c-160">[x – y](arithmetic-operators.md#subtraction-operator--) – 빼기</span><span class="sxs-lookup"><span data-stu-id="6fb8c-160">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="6fb8c-161">시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-161">Shift operators</span></span>

<span data-ttu-id="6fb8c-162">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-162">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – 왼쪽 비트를 시프트하고 오른쪽을 0으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="6fb8c-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – 오른쪽 비트를 시프트합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="6fb8c-165">왼쪽 피연산자가 `int` 또는 `long`이면 왼쪽 비트는 부호 비트로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-165">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="6fb8c-166">왼쪽 피연산자가 `uint` 또는 `ulong`이면 왼쪽 비트는 0으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-166">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="6fb8c-167">관계형 및 형식 테스트 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-167">Relational and type-testing operators</span></span>

<span data-ttu-id="6fb8c-168">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-168">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-169">[x \< y](comparison-operators.md#less-than-operator-) –보다 작음(x가 y보다 작은 경우 true)</span><span class="sxs-lookup"><span data-stu-id="6fb8c-169">[x \< y](comparison-operators.md#less-than-operator-) – less than (true if x is less than y).</span></span>

<span data-ttu-id="6fb8c-170">[x > y](comparison-operators.md#greater-than-operator-) – 보다 큼(x가 y보다 큰 경우 true)</span><span class="sxs-lookup"><span data-stu-id="6fb8c-170">[x > y](comparison-operators.md#greater-than-operator-) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="6fb8c-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – 크거나 같음</span><span class="sxs-lookup"><span data-stu-id="6fb8c-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – less than or equal to.</span></span>

<span data-ttu-id="6fb8c-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – 보다 크거나 같음</span><span class="sxs-lookup"><span data-stu-id="6fb8c-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – greater than or equal to.</span></span>

<span data-ttu-id="6fb8c-173">[is](type-testing-and-conversion-operators.md#is-operator) – 형식 호환성.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-173">[is](type-testing-and-conversion-operators.md#is-operator) – type compatibility.</span></span> <span data-ttu-id="6fb8c-174">계산된 왼쪽 피연산자를 오른쪽 피연산자에 지정된 형식으로 캐스팅할 수 있는 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-174">Returns `true` if the evaluated left operand can be cast to the type specified by the right operand.</span></span>

<span data-ttu-id="6fb8c-175">[as](type-testing-and-conversion-operators.md#as-operator) – 형식 변환.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-175">[as](type-testing-and-conversion-operators.md#as-operator) – type conversion.</span></span> <span data-ttu-id="6fb8c-176">오른쪽 피연산자에 지정된 형식으로 캐스팅된 왼쪽 피연산자를 반환하지만 `(T)x`가 예외를 throw하는 경우 `as`는 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-176">Returns the left operand cast to the type specified by the right operand, but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="6fb8c-177">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-177">Equality operators</span></span>

<span data-ttu-id="6fb8c-178">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-178">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-179">[x == y](equality-operators.md#equality-operator-) – 같음.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-179">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="6fb8c-180">기본적으로 `string`이 아닌 참조 형식에 대해 참조 같음(ID 테스트)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-180">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="6fb8c-181">그러나 형식이 `==`를 오버로드할 수 있으므로 ID를 테스트하려는 경우에는 `object`에서 `ReferenceEquals` 메서드를 사용하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-181">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="6fb8c-182">[x != y](equality-operators.md#inequality-operator-) – 같지 않음.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-182">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="6fb8c-183">`==`에 대한 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-183">See comment for `==`.</span></span> <span data-ttu-id="6fb8c-184">형식이 `==`를 오버로드하는 경우 `!=`를 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-184">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="6fb8c-185">논리곱 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-185">Logical AND operator</span></span>

<span data-ttu-id="6fb8c-186">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-187">`x & y` – `bool` 피연산자의 경우 [논리 AND](boolean-logical-operators.md#logical-and-operator-)이고, 정수 형식 피연산자의 경우 [비트 논리 AND](bitwise-and-shift-operators.md#logical-and-operator-)입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-187">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="6fb8c-188">논리적 XOR 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-188">Logical XOR operator</span></span>

<span data-ttu-id="6fb8c-189">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-190">`x ^ y` – `bool` 피연산자의 경우 [논리 XOR](boolean-logical-operators.md#logical-exclusive-or-operator-)이고, 정수 형식 피연산자의 경우 [비트 논리 XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-190">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="6fb8c-191">이는 논리 OR 연산자입니다</span><span class="sxs-lookup"><span data-stu-id="6fb8c-191">Logical OR operator</span></span>

<span data-ttu-id="6fb8c-192">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-193">`x | y` – `bool` 피연산자의 경우 [논리 OR](boolean-logical-operators.md#logical-or-operator-)이고, 정수 형식 피연산자의 경우 [비트 논리 OR](bitwise-and-shift-operators.md#logical-or-operator-)입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-193">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="6fb8c-194">조건부 AND 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-194">Conditional AND operator</span></span>

<span data-ttu-id="6fb8c-195">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-195">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – 논리적 AND.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="6fb8c-197">`x`가 `false`이면 `y`는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-197">If `x` evaluates to `false`, then `y` is not evaluated.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="6fb8c-198">조건부 OR 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-198">Conditional OR operator</span></span>

<span data-ttu-id="6fb8c-199">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-199">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – 논리적 OR.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="6fb8c-201">`x`가 `true`이면 `y`는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-201">If `x` evaluates to `true`, then `y` is not evaluated.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="6fb8c-202">Null 병합 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-202">Null-coalescing operator</span></span>

<span data-ttu-id="6fb8c-203">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-204">[x ?? y](null-coalescing-operator.md) – `null`이 아닌 경우 `x`를 반환하고, 그렇지 않은 경우 `y`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-204">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="6fb8c-205">조건 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-205">Conditional operator</span></span>

<span data-ttu-id="6fb8c-206">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-206">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-207">[t ? x : y](conditional-operator.md) - 테스트 `t`가 true로 확인되면 `x`를 계산하여 반환하고, 그렇지 않은 경우 `y`를 계산하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-207">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="6fb8c-208">할당 및 람다 연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-208">Assignment and lambda operators</span></span>

<span data-ttu-id="6fb8c-209">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-209">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="6fb8c-210">[x = y](assignment-operator.md) – 할당</span><span class="sxs-lookup"><span data-stu-id="6fb8c-210">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="6fb8c-211">[x += y](arithmetic-operators.md#compound-assignment) – 증가.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-211">[x += y](arithmetic-operators.md#compound-assignment) – increment.</span></span> <span data-ttu-id="6fb8c-212">`y`의 값을 `x` 값에 더하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-212">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="6fb8c-213">`x`가 [이벤트](../keywords/event.md)를 지정하는 경우 `y`는 C#에서 이벤트 처리기로 추가하는 적절한 방법이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-213">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# adds as an event handler.</span></span>

<span data-ttu-id="6fb8c-214">[x -= y](arithmetic-operators.md#compound-assignment) – 감소.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-214">[x -= y](arithmetic-operators.md#compound-assignment) – decrement.</span></span> <span data-ttu-id="6fb8c-215">`x`의 값에서 `y`의 값을 빼고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-215">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="6fb8c-216">`x`가 [이벤트](../keywords/event.md)를 지정하는 경우 `y`는 C#에서 이벤트 처리기로 제거하는 적절한 방법이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-216">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# removes as an event handler.</span></span>

<span data-ttu-id="6fb8c-217">[x \*= y](arithmetic-operators.md#compound-assignment) – 곱하기 대입.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-217">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="6fb8c-218">`y`의 값을 `x`의 값에 곱하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-218">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="6fb8c-219">[x /= y](arithmetic-operators.md#compound-assignment) – 나누기 대입.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-219">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="6fb8c-220">`x`의 값을 `y`의 값으로 나누고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-220">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="6fb8c-221">[x %= y](arithmetic-operators.md#compound-assignment) – 나머지 할당.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-221">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="6fb8c-222">`x`의 값을 `y`의 값으로 나누고 나머지를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-222">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="6fb8c-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND 대입.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="6fb8c-224">`y`의 값을 `x`의 값과 AND하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-224">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="6fb8c-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR 대입.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="6fb8c-226">`y`의 값을 `x`의 값과 OR하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-226">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="6fb8c-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR 대입.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="6fb8c-228">`y`의 값을 `x`의 값과 XOR하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-228">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="6fb8c-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – 왼쪽 시프트 대입.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="6fb8c-230">`x`의 값을 왼쪽으로 `y` 위치만큼 시프트하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-230">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="6fb8c-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – 오른쪽 시프트 대입.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="6fb8c-232">`x`의 값을 오른쪽으로 `y` 위치만큼 시프트하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-232">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="6fb8c-233">[=>](lambda-operator.md) – 람다 선언.</span><span class="sxs-lookup"><span data-stu-id="6fb8c-233">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fb8c-234">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fb8c-234">See also</span></span>

- [<span data-ttu-id="6fb8c-235">C# 참조</span><span class="sxs-lookup"><span data-stu-id="6fb8c-235">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6fb8c-236">연산자</span><span class="sxs-lookup"><span data-stu-id="6fb8c-236">Operators</span></span>](../../programming-guide/statements-expressions-operators/operators.md)
